# 4. Async Await ํจํด

# ๐ย Await, Async

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

`a()` ํจ์ โ Promise ์์ฑ์ ํจ์ `return` ๋ฐ ๋น๋๊ธฐ ํจ์

## `await` ํค์๋

- `awiat` ํค์๋ ํ๋ฉด ๋น๋๊ธฐ ํจ์ ๋๊ธฐ ๊ธฐ๋ฅ
- `return Promise()` ์์ด์ผ ์ฌ์ฉ ๊ฐ๋ฅ
- `async` ํจ์ ๋ด๋ถ์ ์ ์ธ๋์ด์ผ ํจ