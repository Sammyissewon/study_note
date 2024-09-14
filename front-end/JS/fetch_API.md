# **Fetch()** 
- 비동기적으로 네트워크 요청을 처리할 수 있는 모던 자바스크립트 인터페이스. 주로 서버에서 데이터를 가져오거나, 
파일을 업로드하거나, API와 통신할 때 사용. AJAX(Asynchronous JavaScript and XML)의 대체로 볼 수 있으며, 
Promise 기반으로 더 간단하고 직관적인 구문을 제공.

- fetch()는 Promise를 반환하며, then()과 catch()를 사용하여 요청의 성공과 실패를 처리한다. async/await 구문과 함께 사용하면 더 가독성 높은 코드를 작성할 수 있다.

```javascript
let promise = fetch(url, {options})
```

- `url` 접근하고자 하는 URL
- `options` 선택 매개변수, method나 headers 등을 지정할 수 있음.
  `options`에 아무것도 넘기지 않으면 요청은 `GET` 메서드로 진행되어 `url`로부터 콘텐츠가 다운로드 된다.

```javascript
fetch('https://api.example.com/data')
  .then(response => response.json()) // 응답을 JSON으로 변환
  .then(data => console.log(data))   // 데이터 출력
  .catch(error => console.error('Error:', error)); // 에러 처리
```
```javascript
fetch('https://jsonplaceholder.typicode.com/todos/1')
  .then(response => {
    if (!response.ok) {
      throw new Error('네트워크 응답에 문제가 있습니다.');
    }
    return response.json(); // 응답 데이터를 JSON으로 변환
  })
  .then(data => {
    console.log('받은 데이터:', data);
  })
  .catch(error => {
    console.error('Fetch 에러:', error);
  });
```
