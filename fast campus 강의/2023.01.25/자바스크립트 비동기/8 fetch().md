# 8. fetch()

# ðÂ fetch?

ë¤í¸ìí¬ë¥¼ íµí´ ë¦¬ìì¤ì **ìì²­(request)** ë° **ìëµ(response)** ì²ë¦¬íë í¨ì

<aside>
ð¡ `fetch(ì£¼ì, ìµì)`

</aside>

Promise ì¸ì¤í´ì¤ ë°í

```jsx
fetch('ì£¼ì', {
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
	const res = await fetch('ì£¼ì');
	const json = await res.json();
	console.log(json);
};
```

`body` ìµì â ìë²ë¡ ë³´ë¼ ë í­ì `string` íìì¼ë¡ ë³´ë´ì¼ í¨. 

`JSON.stringify` â ì§ì ë ê°ì²´ë¥¼ json string íìì¼ë¡ ìì 