# 2. Context API 살펴보기

# 📌 Context API

## createContext

```jsx
const MyContext = createContext(defaultValue);
```

Context 객체를 생성한다. 생성 뒤, Context 값이 바뀌면 **구독하고 있는 구성요소도 바뀐다.**

`defaultValue`  : 기본값

## Context.Proivder

```jsx
<MyContext.Provider value={/* some value */}>
	<AComponent />
	<BComponent />
	<CComponent />
<MyContext.Provider />
```

A, B, C Component 모두 Context를 구독하는 상태

Context value에 변경이 생기면 **컴포넌트를 다시 렌더링**

`defaultValue` 에 `{ userName: "John" }` 을 할당하고 value `props` 에 내용을 바꾸면?

```jsx
const MyContext = createContext({ userName: "John" });

<MyContext.Proivder value={{ userName: "Han" }}
```

바뀐 value 값이 Consumer Components에 전달된다