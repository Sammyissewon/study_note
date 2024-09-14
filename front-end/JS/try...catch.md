# **try...catch**
: 에러가 발생해도 스크립트가 죽지 않고, 에러를 출력해 내는 문법

```javascript
try {
  // 코드...
} catch (err) {
  // 에러 핸들링
}
```
1. 먼저, `try {...}` 안의 코드가 실행
2. 에러가 없다면, `try` 안의 마지막 줄까지 실행되고, `catch` 블록은 건너뜀
3. 에러가 있다면, `try` 안 코드의 실행이 중단되고, `catch(err)` 블록으로 제어 흐름이 넘어감
4. 변수 `err`(아무 이름이나 사용 가능)는 무슨 일이 일어났는지에 대한 설명이 담긴 에러 객체를 포함함

```javascript
// 비동기 함수 예시
async function fetchData() {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/todos/1');
    const data = await response.json();
    console.log('Fetched Data:', data);
  } catch (error) {
    console.log('Error occurred:', error);
  }
}

fetchData();
