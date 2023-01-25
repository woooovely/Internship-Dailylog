# 3. Any 타입부터 Void까지

# 📌 Any

```tsx
let hello: any = 'Hello world'
hello = 123
hello = false
hello = null
hello = {}
hello = []
hello = fuction () {}
```

무슨 타입인지 유추할 수 없어 **용이하지 않음**

# 📌 Unknown

무슨 타입인지 명시할 수 없을 때 정의하는 타입

```tsx
const a: any = 123
const u: unknown = 123

const any: any = a
const boo: boolean = a
```

# 📌 Tuple

배열 타입의 정확한 요소의 갯수와 타입을 명시하는 타입

```tsx
const tuple: [string, number, boolean] = ['a', 1, false];
```

# 📌 Void

```tsx
function Hello(msg: string): void {
	console.log(`Hello ${msg});
}
const hi: void = Hello('world');
```