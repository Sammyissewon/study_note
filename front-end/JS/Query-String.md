# Query string(쿼리 문자열)
: 클라이언트(브라우저나 애플리케이션)가 서버에 요청할 때, URL 경로만으로는 충분하지 않은 **추가적인 정보**나 **조건**을 서버에 전달하는 용도
    
### 주요 목적
1. 데이터 필터링 및 검색      
```jsx
https://example.com/products?category=shoes&sortBy=latest
```
            
2. 페이지네이션
3. 정렬 및 정제: 데이터 정렬 기준이나 순서를 서버에 전달할 때
```jsx
https://example.com/products?sort=price&order=asc
``` 
4. 인증 및 접근 권한: 서버에 인증 토큰이나 유저 ID를 전달할 때
```jsx
https://api.example.com/data?apiKey=123456789
```
            
### URL과 쿼리 문자열의 기본 형식
```jsx
http://example.com/path?key=value
```
        
- `http://example.com/path`: 기본 URL(경로)
- `?key=value`: 쿼리 문자열
- `?`: 쿼리 파라미터의 시작을 나타냅니다.
- `key=value`: 전달할 값 (`key`는 파라미터 이름, `value`는 그 값)

### 사용예시
1. `params` 객체
    - **객체**로 정의된 변수
    - URL의 쿼리 문자열로 변환할 데이터를 담고 있음
2. `URLSearchParams` 생성자
    - 웹 API의 생성자
    - 쿼리 문자열을 쉽게 생성하거나 조작하도록 함
    - 객체를 전달하면, 각 키-값 쌍이 `key=value` 형식의 쿼리 파라미터로 전환됨
3. .`toString()`: `URLSearchParams` 객체를 문자열로 변환
        
```jsx
const params = {
  reviewId: 456,
  userId: 123,
};
        
const queryString = new URLSearchParams(params).toString(); // "reviewId=456&userId=123"        
const apiUrl = const apiUrl = `reviews?${queryString}`;
        
최종 URL: reviews?reviewId=456&userId=123
```
