# 6. 타입 가드(Guards)

# 📌 타입 가드

```tsx
function logText(el: Element) {
  console.log(el.textContent)
}

const h1El = document.querySelector('h1');
logText(h1El) // 에러, h1El의 타입이 null일 수 있다.
```

조건을 할당해 에러가 나지 않게 막는(guard) 역할을 준다.

```tsx
function logText(el: Element) {
  console.log(el.textContent);
}

const h1El = document.querySelector("h1");
if (h1El) {
  logText(h1El);
}
```

```tsx
function add(val: string | number) {
	let res = 'Result => ';
	if (typeof val === 'number') {
		res += val.toFixed(2)
	} else {
			res += toUpperCase();
		}
	console.log(res);
}

add(3.141592);
add('hello world');
```