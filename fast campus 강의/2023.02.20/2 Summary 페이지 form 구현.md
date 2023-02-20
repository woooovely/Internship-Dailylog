# Summary 페이지 Form 구현

# 📌 해야 할 일?

<aside>
💡 *주문 확인 체크박스를 눌러야만 주문 확인 버튼을 누를 수 있다.*

</aside>

# 🛠️ 실제 코드 작성

## src/pages/SummaryPage/index.js

```jsx
import React, { useState } from "react";

const SummaryPage = () => {
  const [checked, setChecked] = useState(false);

  return (
    <div>
      <form>
        <input
          type="checkbox"
          checked={checked}
          id="confrim-checkbox"
          onClick={(e) => setChecked(e.target.checked)}
        />{" "}
        <label htmlFor="confirm-checkbox">주문하려는 것을 확인하셨나요?</label>
        <br />
        <button disabled={!checked} type="submit">주문 확인</button>
      </form>
    </div>
  );
};

export default SummaryPage;
```