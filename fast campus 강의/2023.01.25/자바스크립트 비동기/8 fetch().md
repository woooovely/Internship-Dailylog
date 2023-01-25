# 8. fetch()

# 📌 fetch?

네트워크를 통해 리소스의 **요청(request)** 및 **응답(response)** 처리하는 함수

<aside>
💡 `fetch(주소, 옵션)`

</aside>

Promise 인스턴스 반환

```jsx
fetch('주소', {
	method: 'GET',
	body: JSON.stringify({
		name: 'HEROPY',
		age: 85,
		email: 'aaa@gmail.com'
	})
})
	.then(res => res.json());
	.tehn(json => console.log(json));

const wrap = async () => {
	const res = await fetch('주소');
	const json = await res.json();
	console.log(json);
};
```

`body` 옵션 → 서버로 보낼 떄 항상 `string` 타입으로 보내야 함. 

`JSON.stringify` → 지정된 객체를 json string 형식으로 수정