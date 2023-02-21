# Context로 데이터 제공하기

# 📌 해야 할 일?

<aside>
💡 *Context로 어떠한 컴포넌트에서 총 합계를 Update 및 보여주기*

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
        return [{ ...orderCounts }]
    }, [orderCounts])

  return <OrderContext.Provider value={value} {...props} /> 
}
```

## src/index.js

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import "./index.css";
import App from "./App";
import { OrderContextProvider } from "./context/OrderContext";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <React.StrictMode>
    <OrderContextProvider>
      <App />
    </OrderContextProvider>
  </React.StrictMode>
);
```