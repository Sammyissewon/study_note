# `URL.createObjectURL()`
- 주어진 객체를 가리키는 URL을 `DOMString`으로 반환.
- 이 URL은 브라우저 내에서만 유효하며, 파일을 서버에 업로드하지 않아도 내용을 미리볼 수 있게 해준다.
- 구문
```jsx
const objectURL = URL.createObjectURL(object);
```
- object: 객체 URL을 생성할 File, Blob, MediaSource 객체.
- 반환 값(objectURL): 지정한 object의 참조 URL을 담은 DOMString.

``` jsx
import React, { useState } from "react";

const ImagePreviewer = () => {
  const [imageURL, setImageURL] = useState(null);

  const handleImageChange = (e) => {
    const file = e.target.files[0]; // 사용자가 업로드한 첫 번째 파일
    if (file) {
      const previewURL = URL.createObjectURL(file); // 임시 URL 생성
      setImageURL(previewURL); // 상태에 URL 저장
    }
  };

  return (
    <div>
      <input type="file" accept="image/*" onChange={handleImageChange} />
      {imageURL && (
        <div>
          <img src={imageURL} alt="Preview" style={{ width: "300px", marginTop: "10px" }} />
        </div>
      )}
    </div>
  );
};

export default ImagePreviewer;
```
