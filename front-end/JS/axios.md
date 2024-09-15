# **Axios**
- **Promise 기반의 HTTP 클라이언트**로, 브라우저와 Node.js 환경에서 사용
- 이를 통해 쉽게 **비동기적으로** HTTP 요청을 보내고, 서버로부터 데이터를 받아올 수 있다
- Axios는 `XMLHttpRequest`를 기반으로 하고 있으며, 주로 **API 통신**에서 데이터를 주고받는 데 사용

## then()...catch() 방식
: Promise의 기본 문법 방식이다. 단순한 비동기 작업에서는 충분히 유용하지만, 복잡한 로직에서는 콜백지옥 등 가독성이 떨어질 수 있다.
```javascript
import axios from 'axios';

// GET 요청 예시
axios.get('https://api.example.com/data')
  .then((response) => {
    console.log(response.data); 
  })
  .catch((error) => {
    console.error(error); 
  });

// POST 요청 예시
axios.post('https://api.example.com/data', { name: 'John', age: 30 })
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.error(error);
  });
```
## async...await + try...catch 방식
: 코드가 마치 동기적으로 처리되는 것처럼 보여지며, 비동기 로직을 이해하기 쉬워지고, **try/catch**로 오류 처리가 간결해진다.
```javascript
async function fetchData() {
  try {
    const response = await axios.get('https://api.example.com/data');
    console.log('Data:', response.data);
  } catch (error) {
    console.error('Error:', error);
  }
}

fetchData();
```

## ❓(async...await 없이) try...catch만 사용 가능한가? 
- 동기 코드에서 발생하는 에러 처리 -> 가능
- 비동기 코드에서 발생하는 에러 처리 -> 불가능 -> then...catch를 써야함
