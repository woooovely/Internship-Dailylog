# State를 업데이트하는 함수

# 📌 해야 할 일?

<aside>
💡 *불변성을 유지하며 데이터를 업데이트*

</aside>

# 🛠️ 코드 작성

## src/context/OrderContext.js

```jsx
import { createContext, useMemo, useState } from "react";

const OrderContext = createContext();

export function OrderContextProvider(props) {
    const [orderCounts, setOrderCounts] = useState({
        products: new Map(),
        options: new Map()
    })

    const value = useMemo(() => {
        function updateItemCount(itemName, newItemCount, orderType) {
            const newOrderCounts = {...orderCounts}

            const orderCountsMap = orderCounts[orderType];
            orderCountsMap.set(itemName, parseInt(newItemCount));

            setOrderCounts(newOrderCounts);
        }

        return [{ ...orderCounts }, updateItemCount]
    }, [orderCounts])

  return <OrderContext.Provider value={value} {...props} /> 
}
```