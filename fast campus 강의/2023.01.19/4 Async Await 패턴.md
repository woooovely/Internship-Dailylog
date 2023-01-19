# 4. Async Await 패턴

# 📌 Await, Async

```jsx
const a = () => {
	return new Promise(resolve => {
		setTimeout(() => {
			console.log(1);
			resolve();
		}, 1000)
	})
}
const b = () => console.log(2);

await a();
b();
```

`a()` 함수 → Promise 생성자 함수 `return` 및 비동기 함수

## `await` 키워드

- `awiat` 키워드 후면 비동기 함수 대기 기능
- `return Promise()` 있어야 사용 가능
- `async` 함수 내부에 선언되어야 함