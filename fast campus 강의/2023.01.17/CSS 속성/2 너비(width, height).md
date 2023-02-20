# 2. 너비(width, height)

# 📌 width, height

요소의 가로(width) 세로(height)의 너비를 지정할 수 있다.

`auto` : 기본값으로 브라우저가 너비를 계산

단위 : `px`, `em`, `vw`, 등 단위로 지정

```html
<span>Hello</span>
<span>World</span>
```

`<span></span>` 은 대표적인 인라인 요소다. 본래 아무것도 나타내지 않고 콘텐츠 영역을 설정하는 용도.

```css
span {
		width: auto; 
		height: auto;
}
```

포함한 콘텐츠 크기만큼 자동으로 줄어듬

# 📌 max-width, max-height

요소가 커질 수 있는 최대 가로/세로 너비

`none` : 최대 너비 제한 없음

단위 : `px`, `em`, `vw` 등 단위로 지정

# 📌 min-width, min-height

요소가 작아질 수 있는 최소 가로/세로 너비

`0` : 최소 너비 제한 없음

단위: `px`, `em`, `vw` 등 단위로 지정