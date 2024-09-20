# FormData
- 파일 여부나 추가 필드 여부 등과 상관없이 폼을 쉽게 보내도록 도와주는 객체
- FormData 메서드
  - `formData.append(name, value)` – `name`과 `value`를 가진 폼 필드를 추가
  - `formData.set(name, value)` - name과 value를 가진 폼 필드를 추가. 단, 동일한 name 불가.
  - `formData.delete(name)` – `name`에 해당하는 필드를 삭제
  - `formData.get(name)` – `name`에 해당하는 필드의 값을 가져옴
- FormData 전송 시, HTTP의 Content-Type 속성은 항상 `multipart/form-data`

```javascript
import { put } from "./api";

const updateMyReview = async (
  userId,
  accessToken,
  reviewId,
  content,
  imageUrls
) => {
  const customHeaders = {
    Authorization: `${accessToken}`,
    "Content-Type": "multipart/form-data",
  };

  const reviewRequest = JSON.stringify({
    content: content,
    imageUrls: imageUrls,
  });

  const formData = new FormData();
  formData.append("reviewRequest", reviewRequest);

  const params = {
    userId: userId,
  };

  const queryString = new URLSearchParams(params).toString();

  try {
    const response = await put(
      `reviews/${reviewId}?${queryString}`,
      formData,
      customHeaders
    );

    console.log("리뷰 업데이트 성공!😃", response);
    console.log("전송한 데이터:", {
      reviewRequest: reviewRequest,
    });
    return response;
  } catch (error) {
    console.error("리뷰 업데이트에 실패했습니다🥲", error);
    throw error;
  }
};

export default updateMyReview;
```
