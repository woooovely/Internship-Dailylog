# 6. νμ κ°λ(Guards)

# πΒ νμ κ°λ

```tsx
function logText(el: Element) {
  console.log(el.textContent)
}

const h1El = document.querySelector('h1');
logText(h1El) // μλ¬, h1Elμ νμμ΄ nullμΌ μ μλ€.
```

μ‘°κ±΄μ ν λΉν΄ μλ¬κ° λμ§ μκ² λ§λ(guard) μ­ν μ μ€λ€.

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