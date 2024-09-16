## Optional Chaining ( .? )
- ?.는 왼쪽 평가대상에 값이 없으면(`undefined`나 `null`) 즉시 평가를 멈춘다.
- 참고로 이런 평가 방법을 **단락 평가(short-circuit)** 라고 부른다.
- 그렇기 때문에 함수 호출을 비롯한 ?. 오른쪽에 있는 부가 동작은 ?.의 평가가 멈췄을 때 더는 일어나지 않는다. 

```javascript
let user = {}; // 주소 정보가 없는 사용자
alert( user?.address?.street ); // undefined
```
다만, 옵셔널 체이닝을 남용하지 않도록 주의할 것. 
누가봐도 user는 반드시 있는데, address가 있는지 없는지만 불문명하다면, 

```javascript
alert( user.address?.street ); // undefined
```
로 쓰는 것이 바람직하다. 

```javascript
 const renderReviewImages = (images) =>
    images?.length > 0 ? (
      images
        .slice(0, 4)
        .map((image, index) => (
          <img
            key={index}
            className="detail-review-img"
            src={image}
            onClick={() => modalOpenHandle(image)}
            alt={`리뷰 이미지 ${index + 1}`}
          />
        ))
    ) : (
      <div className="detail-no-review-img">리뷰 사진이 없습니다</div>
    );
```
- `images`가 존재하면 길이를 체크하고, 존재하지 않으면 대체문구를 출력. 
