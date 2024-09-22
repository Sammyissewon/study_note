# File
- `File` 객체는 웹 애플리케이션에서 사용자가 업로드한 파일을 다루기 위해 제공되는 표준 객체.
- **`<input type="file">`** 요소를 통해 파일을 선택하거나, 드래그 앤 드롭으로 파일을 업로드할 때 생성.
- `File` 객체의 특징
  - `name`: 파일의 이름을 나타낸다. 예를 들어 `"image1.jpg"`.
  - `size`: 파일의 크기(바이트)를 나타낸다.
  - `type`: 파일의 MIME 타입을 나타낸다. 예를 들어 `"image/jpeg"`.
  - `lastModified`: 파일의 마지막 수정 시간을 타임스탬프로 나타낸다.

 ``` jsx
  const imageChangeHandle = (e) => {
  const files = Array.from(e.target.files); // 선택한 파일들을 배열로 변환
  const newImages = files.map((file) => ({
    url: URL.createObjectURL(file), // File 객체를 사용하여 미리보기 URL 생성
    file, // 원본 File 객체 저장
  }));

  const updatedImages = [...selectedImgs, ...newImages].slice(0, maxImages);
  setSelectedImgs(updatedImages);
  setReviewImages(updatedImages.map((img) => img.file));
};
```
``` jsx
  <input
    type="file"
    accept="image/*"
    onChange={imageChangeHandle}
    multiple
  />
```
``` jsx
console.log(files);

 [
  File { name: "image1.jpg", size: 204800, type: "image/jpeg", lastModified: 1633036800000 },
  File { name: "image2.png", size: 102400, type: "image/png", lastModified: 1633036850000 }
 ]
```
``` jsx
console.log(newImages);

[
  {
    url: "blob:http://example.com/abc123", // URL.createObjectURL(file)로 생성된 임시 URL
    file: File { name: "image1.jpg", size: 204800, type: "image/jpeg", lastModified: 1633036800000 }
  },
  {
    url: "blob:http://example.com/def456", // URL.createObjectURL(file)로 생성된 임시 URL
    file: File { name: "image2.png", size: 102400, type: "image/png", lastModified: 1633036850000 }
  }
]
```
