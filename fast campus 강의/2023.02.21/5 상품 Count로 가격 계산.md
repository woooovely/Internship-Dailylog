# 상품 Count로 가격 계산

# 📌 해야 할 일?

<aside>
💡 *count를 누적 계산하여 저장하기*

</aside>

# 🛠️ 코드 작성

## src/components/Type.js

```jsx
import React, { useContext, useEffect, useState } from "react";
import axios from "axios";
import Products from "./Products";
import Options from "./Options";
import ErrorBanner from "./ErrorBanner";
import { OrderContext } from "../context/OrderContext";

const Type = ({ orderType }) => {
  const [items, setItems] = useState([]);
  const [error, setError] = useState(false);
  const [orderData, updateItemCount] = useContext(OrderContext);

  console.log('orderData, updateItemCount', orderData, updateItemCount)

  useEffect(() => {
    loadItems(orderType);
  }, [orderType]);

  const loadItems = async (orderType) => {
    try {
      const res = await axios.get(`http://localhost:4000/${orderType}`);
      setItems(res.data);
    } catch (error) {
      setError(true);
    }
  };

  const ItemComponent = orderType === "products" ? Products : Options

  const optionItems = items.map((item) => (
    <ItemComponent
      key={item.name}
      name={item.name}
      imagePath={item.imagePath}
    />
  ));

  if (error) {
    return (
      <ErrorBanner message="에러가 발생했습니다." />
    )
  }

  return (
    <div>
      <h2>주문 종류</h2>
      <p>하나의 가격</p>
      <p>총 가격:</p>
      <div
        style={{
          display: "flex",
          flexDirection: orderType === "options" ? "column" : "row",
        }}
      >
        {optionItems}
      </div>
    </div>
  );
};

export default Type;
```

## src/context/OrderContext.js

```jsx
import { createContext, useEffect, useMemo, useState } from "react";

export const OrderContext = createContext();

export function OrderContextProvider(props) {
    const [orderCounts, setOrderCounts] = useState({
        products: new Map(),
        options: new Map()
    })

    const [totals, setTotals] = useState({
        products: 0,
        options: 0,
        total: 0,
    })

    const priceItem = {
        products: 1000,
        options: 500
    }

    const calculateSubtotal = (orderType, orderCounts) => {
        let optionCount = 0;
        for (const count of orderCounts[orderType].values()) {
            optionCount += count;
        } 
        return optionCount * priceItem[orderType]
    }

    useEffect(() => {
        const productsTotal = calculateSubtotal('products', orderCounts);
        const optionsTotal = calculateSubtotal('options', orderCounts);
        const total = productsTotal + optionsTotal;
        setTotals({
            products: productsTotal,
            options: optionsTotal,
            total
        })
    }, [orderCounts])

    const value = useMemo(() => {
        function updateItemCount(itemName, newItemCount, orderType) {
            const newOrderCounts = {...orderCounts}

            const orderCountsMap = orderCounts[orderType];
            orderCountsMap.set(itemName, parseInt(newItemCount));

            setOrderCounts(newOrderCounts);
        }

        return [{ ...orderCounts, totals }, updateItemCount]
    }, [orderCounts])

  return <OrderContext.Provider value={value} {...props} /> 
}
```