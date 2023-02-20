# 주문 페이지 UI 생성하기

# 📌 해야 할 일?

<aside>
💡 *전체적인 틀 제작*

</aside>

# 🛠️ 코드 작성

## src/pages/OrderPage/index.js

```jsx
import React from "react";
import Type from "../../components/Type";

const OrderPage = () => {
    return (
        <div>
            <h1>Travel Products</h1>
            <div>
                <Type orderType="products" />
            </div>
            <div style={{ display: 'flex', marginTop: 20 }}>
                <div style={{ width: '50%' }}>
                    <Type orderType="options" />
                </div>
                <div style={{ width: '50%' }}>
                    <h2>Total Price: </h2>
                    <button>주문</button>
                </div>
            </div>
        </div>
    )
}

export default OrderPage;
```

## src/components/Type.js

```jsx
import React from "react";

const Type = ({ orderType }) => {
  console.log("order-type", orderType);

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
        Items
      </div>
    </div>
  );
};

export default Type;
```