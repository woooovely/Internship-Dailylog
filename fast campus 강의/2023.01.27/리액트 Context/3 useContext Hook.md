# 3. useContext Hook

# 📌 함수형 컴포넌트의 context value?

## 클래스형 Component

contextType Property로 contex**t** value 사용

## 함수형 Component

```jsx
const themes = {
	light: {
		foreground: 'white';,
		background: 'white'
	},
	dark: {
		foreground: 'black',
		background: 'black'
	}
}

const ThemeContext = React.createContext(themes.light);

function ThemeButton() {
	const theme = useContext(ThemeContext);
	return (
		<button style={{ background: theme.background, color: theme.foreground }}>
			button
		</button>
	);
}

function Toolbar(props) {
	return (
		<div>
			<ThemeButton />
		</div>
	);
}

export default function App() {
	return (
		<ThemeContext.Provider value={themes.dark}>
			<Toolbar />
		<ThemeContext.Provider />
	);
}
```

`createContext` 의 defaultValue에 `themes.light` 값이 들어감.

하지만 value property엔 `themes.dark` 값이 들어가서 그 값이 적용됨