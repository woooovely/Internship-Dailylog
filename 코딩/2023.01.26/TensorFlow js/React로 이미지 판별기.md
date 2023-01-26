# React로 이미지 판별기

```jsx
import * as mobilenet from "@tensorflow-models/mobilenet";
import { models } from "@tensorflow/tfjs";
import { useState, useEffect, useRef } from "react";
import styled from "styled-components";

const App = () => {
  const [isModelLoading, setIsModelLoading] = useState(false);
  const [model, setModel] = useState(null);
  const [imageURL, setImageURL] = useState(null);
  const [results, setResults] = useState([]);

  const imageRef = useRef();

  const loadModel = async () => {
    setIsModelLoading(true);
    try {
      const model = await mobilenet.load();
      setModel(model);
      setIsModelLoading(false);
    } catch (err) {
      console.log(err);
      setIsModelLoading(false);
    }
  };

  const uploadImage = (e) => {
    const { files } = e.target;
    if (files.length > 0) {
      const url = URL.createObjectURL(files[0]);
      setImageURL(url);
    } else {
      setImageURL(null);
    }
  };

  const identify = async () => {
    const results = await model.classify(imageRef.current);
    setResults(results);
  };

  useEffect(() => {
    loadModel();
  }, []);

  if (isModelLoading) {
    return <h2>모델을 불러오는 중...</h2>;
  }

  console.log(results);

  return (
    <div>
      <h1>이미지 판별기</h1>
      <div>
        <input
          type="file"
          accept="image/*"
          capture="camera"
          onChange={uploadImage}
        />
      </div>
      <div>
        <div>
          <div>
            {imageURL && (
              <img
                src={imageURL}
                alt="미리보기"
                crossOrigin="annoymous"
                ref={imageRef}
              />
            )}
          </div>
          {results.length > 0 && (
            <div>
              {results.map((result, index) => {
                return (
                  <div>
                    <div>{result.className}</div>
                    <div>
                      신뢰도: {(result.probability * 100).toFixed(2)}%{" "}
                      {index === 0 && <span>최고 확률</span>}
                    </div>
                  </div>
                );
              })}
            </div>
          )}
        </div>
        {imageURL && <button onClick={identify}>이미지 판별</button>}
      </div>
    </div>
  );
};

export default App;
```