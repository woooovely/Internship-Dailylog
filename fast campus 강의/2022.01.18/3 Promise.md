# 3. Promise

# 📌 Promise

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

Promise는 콜백 패턴에서 생긴 콜백 지옥 문제를 해결하기 위해 해결책으로 나온 클래스다. 기존에 파라미터로 인한 콜백 지옥을 `resolve` 라는 키워드를 파라미터로 받아서 실행 위치를 정하고, 가독성을 높이면서 코드의 품을 더 높일 수 있다.