# 3. Promise

# ๐ย Promise

```jsx
const a = () => {
	return new Promise(resolve => {
		setTimeout(() => {
			console.log(1);
			resolve();
		}, 1000)
	})
}
const b = () => {
	return new Promise(resolve => {
		setTimeout(() => {
			console.log(2);
			resolve();
		}, 1000)
	})
}
const c = () => console.log(3);

a.
	then(() => b())
	then(() => c())
});
```

Promise๋ ์ฝ๋ฐฑ ํจํด์์ ์๊ธด ์ฝ๋ฐฑ ์ง์ฅ ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ๊ธฐ ์ํด ํด๊ฒฐ์ฑ์ผ๋ก ๋์จ ํด๋์ค๋ค. ๊ธฐ์กด์ ํ๋ผ๋ฏธํฐ๋ก ์ธํ ์ฝ๋ฐฑ ์ง์ฅ์ `resolve` ๋ผ๋ ํค์๋๋ฅผ ํ๋ผ๋ฏธํฐ๋ก ๋ฐ์์ ์คํ ์์น๋ฅผ ์ ํ๊ณ , ๊ฐ๋์ฑ์ ๋์ด๋ฉด์ ์ฝ๋์ ํ์ ๋ ๋์ผ ์ ์๋ค.