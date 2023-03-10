# TensorFlow.js

# ๐ย ๊ธฐ๊ณ ํ์ต์ผ๋ก ํ  ์ ์๋ ์ฌ๋ฌ๊ฐ์ง ์ผ๋ค

- ๋ง์ถ๋ ค๋ ์ ๋ณด๊ฐ ์ซ์์ผ ๋ : **ํ๊ท (regression)**
- ๋ง์ถ๋ ค๋ ์ ๋ณด๊ฐ ๋ฒ์ฃผ์ผ ๋ : **๋ถ๋ฅ (classification)**

![Untitled](TensorFlow%20js%2062a719e720394bff8205db49a7dc02a8/Untitled.png)

# โย Machine learning Algorithm

๋ถ๋ฅ์ ํ๊ท ๋ฌธ์ ๋ฅผ ํ๊ธฐ ์ํด์ ์ฌ์ฉํ๋ ๋ฐฉ๋ฒ๋ค์ ๋งค์ฐ ๋ค์

![Untitled](TensorFlow%20js%2062a719e720394bff8205db49a7dc02a8/Untitled%201.png)

๋จธ์ ๋ฌ๋ ์๊ณ ๋ฆฌ์ฆ ์ค Neural Network๋ **์ฌ๋์ ๋๋๊ฐ ๋์ํ๋ ๋ฐฉ๋ฒ์ ๋ชจ๋ฐฉ**ํด์ ๊ธฐ๊ณ๊ฐ ์ฌ๋์ฒ๋ผ ํ์ต์ ํ  ์ ์๋๋ก ๊ณ ์๋ ์๊ณ ๋ฆฌ์ฆ ๋ฐฉ๋ฒ์ด๋ค.

![Untitled](TensorFlow%20js%2062a719e720394bff8205db49a7dc02a8/Untitled%202.png)

<aside>
๐ก **Neural Network = ์ธ๊ณต ์ ๊ฒฝ๋ง = Deep Learning**

</aside>

์ต๊ทผ์ ๋ฅ๋ฌ๋์ด ๋ง์ ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ๊ณ  ์์ด์ ๋ฅ๋ฌ๋, ๋จธ์ ๋ฌ๋, ์ธ๊ณต์ง๋ฅ์ ๊ฐ์ด ๋ถ๋ฅด์ง๋ง **์์ฐํ ๋ค๋ฅธ ํํ์ด๋ค.**

# ๐งย Deep learning ๋ผ์ด๋ธ๋ฌ๋ฆฌ

๊ตฌ์ฒด์ ์ธ ๋ฅ๋ฌ๋์ ์๋ฆฌ๋ฅผ ๋ชฐ๋ผ๋ ์ฝ๋๋ง ์์ฑํ๋ฉด ๋ฅ๋ฌ๋ ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ  ์ ์๋ ๋ผ์ด๋ธ๋ฌ๋ฆฌ

![Untitled](TensorFlow%20js%2062a719e720394bff8205db49a7dc02a8/Untitled%203.png)

# ๐ ๏ธย TensorFlow.js ๋ผ์ด๋ธ๋ฌ๋ฆฌ

- TensorFlow ๋ผ์ด๋ธ๋ฌ๋ฆฌ
    - TensorFlow : Python์ผ๋ก ์ฌ์ฉํ๋ ๋ผ์ด๋ธ๋ฌ๋ฆฌ
    - TensorFlow.js : JavaScript๋ก ์ฌ์ฉํ๋ ๋ผ์ด๋ธ๋ฌ๋ฆฌ

**TensorFlow.js๋ ์๋ฐ์คํฌ๋ฆฝํธ๊ฐ ๋์ํ๋ ํ๊ฒฝ์์ ๊ณตํต์ผ๋ก ์๋ํ๋ค.**

# ๐ชย ์ง๋ํ์ต์ ์์ ์์

1. ๊ณผ๊ฑฐ์ ๋ฐ์ดํฐ ์ค๋น
2. ๋ชจ๋ธ์ ๋ชจ์์ ์ ์
3. ๋ฐ์ดํฐ๋ก ๋ชจ๋ธ์ ํ์ต(FIT)ํ๋ค.
4. ๋ชจ๋ธ์ ์ด์ฉ

![Untitled](TensorFlow%20js%2062a719e720394bff8205db49a7dc02a8/Untitled%204.png)

# ๐ชย ๋ชจ๋ธ์ ์ด์ฉํ๋ 3๊ฐ์ง ๋ฐฉ๋ฒ

1. ๊ธฐ์กด ๋ชจ๋ธ ์คํ
2. ๊ธฐ์กด ๋ชจ๋ธ ๋ค์ ํ์ต
3. ์๋ฐ์คํฌ๋ฆฝํธ๋ก ML ๊ฐ๋ฐ

![Untitled](TensorFlow%20js%2062a719e720394bff8205db49a7dc02a8/Untitled%205.png)

# ๐ฎย ๊ธฐ์กด ๋ชจ๋ธ ์คํ

์ด๋ฏธ์ง ๋ถ๋ฅ : ImageNet ๋ฐ์ดํฐ๋ฒ ์ด์ค์ ๋ผ๋ฒจ๋ก ์ด๋ฏธ์ง ๋ถ๋ฅ

```html
<html>
	<body>
		<script src="https://cdn.jsdelivr.net/npm/@tensorflow/tfjs@1.0.1"></script>
		<script src="https://cdn.jsdelivr.net/npm/@tensorflow-models/mobilenet@1.0.0"> </script>
		<img id="img" src="dog.jpg"></img>
		
		<script>
			const img = document.getElementById('img');
			mobilenet.load().then(model => {
				model.classify(img).then(predictions => {
					console.log('Predictions: ');
					console.log(predictions);
				}):
			});
			</script>
		</body>
</html>
```

# ๐ชย TensorFlow.js ๊ธฐ๋ณธ์ ์ธ ๊ณจ๊ฒฉ ๊ตฌ์กฐ

![Untitled](TensorFlow%20js%2062a719e720394bff8205db49a7dc02a8/Untitled%206.png)

![Untitled](TensorFlow%20js%2062a719e720394bff8205db49a7dc02a8/Untitled%207.png)

# ๐งญย ๋ผ์ด๋ธ๋ฌ๋ฆฌ ์ค์น

- ์คํฌ๋ฆฝํธ ํ๊ทธ๋ฅผ ์ด์ฉํ ์ค์น
    - `<script src="[https://cdn.jsdelivr.net/npm/@tensorflow/tfjs@2.0.0/dist/tf.min.js](https://cdn.jsdelivr.net/npm/@tensorflow/tfjs@2.0.0/dist/tf.min.js)"></script>`
- Npm, Yarn ์ค์น
    - `npm install @tensorflow/tfjs`
    - `yarn add @tensorflow/tfjs`