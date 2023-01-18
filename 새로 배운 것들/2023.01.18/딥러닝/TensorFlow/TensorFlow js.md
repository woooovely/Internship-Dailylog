# TensorFlow.js

# 📌 기계 학습으로 할 수 있는 여러가지 일들

- 맞추려는 정보가 숫자일 때 : **회귀 (regression)**
- 맞추려는 정보가 범주일 때 : **분류 (classification)**

![Untitled](TensorFlow%20js%2062a719e720394bff8205db49a7dc02a8/Untitled.png)

# ✅ Machine learning Algorithm

분류와 회귀 문제를 풀기 위해서 사용하는 방법들은 매우 다양

![Untitled](TensorFlow%20js%2062a719e720394bff8205db49a7dc02a8/Untitled%201.png)

머신러닝 알고리즘 중 Neural Network는 **사람의 두뇌가 동작하는 방법을 모방**해서 기계가 사람처럼 학습을 할 수 있도록 고안된 알고리즘 방법이다.

![Untitled](TensorFlow%20js%2062a719e720394bff8205db49a7dc02a8/Untitled%202.png)

<aside>
💡 **Neural Network = 인공 신경망 = Deep Learning**

</aside>

최근에 딥러닝이 많은 문제를 해결하고 있어서 딥러닝, 머신러닝, 인공지능을 같이 부르지만 **엄연히 다른 표현이다.**

# 🔧 Deep learning 라이브러리

구체적인 딥러닝의 원리를 몰라도 코드만 작성하면 딥러닝 문제를 해결할 수 있는 라이브러리

![Untitled](TensorFlow%20js%2062a719e720394bff8205db49a7dc02a8/Untitled%203.png)

# 🛠️ TensorFlow.js 라이브러리

- TensorFlow 라이브러리
    - TensorFlow : Python으로 사용하는 라이브러리
    - TensorFlow.js : JavaScript로 사용하는 라이브러리

**TensorFlow.js는 자바스크립트가 동작하는 환경에서 공통으로 작동한다.**

# 🪙 지도학습의 작업 순서

1. 과거의 데이터 준비
2. 모델의 모양을 제작
3. 데이터로 모델을 학습(FIT)한다.
4. 모델을 이용

![Untitled](TensorFlow%20js%2062a719e720394bff8205db49a7dc02a8/Untitled%204.png)

# 🪛 모델을 이용하는 3가지 방법

1. 기존 모델 실행
2. 기존 모델 다시 학습
3. 자바스크립트로 ML 개발

![Untitled](TensorFlow%20js%2062a719e720394bff8205db49a7dc02a8/Untitled%205.png)

# 🔮 기존 모델 실행

이미지 분류 : ImageNet 데이터베이스의 라벨로 이미지 분류

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

# 🪚 TensorFlow.js 기본적인 골격 구조

![Untitled](TensorFlow%20js%2062a719e720394bff8205db49a7dc02a8/Untitled%206.png)

![Untitled](TensorFlow%20js%2062a719e720394bff8205db49a7dc02a8/Untitled%207.png)

# 🧭 라이브러리 설치

- 스크립트 태그를 이용한 설치
    - `<script src="[https://cdn.jsdelivr.net/npm/@tensorflow/tfjs@2.0.0/dist/tf.min.js](https://cdn.jsdelivr.net/npm/@tensorflow/tfjs@2.0.0/dist/tf.min.js)"></script>`
- Npm, Yarn 설치
    - `npm install @tensorflow/tfjs`
    - `yarn add @tensorflow/tfjs`