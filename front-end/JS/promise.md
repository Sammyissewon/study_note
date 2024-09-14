# **Promise**
: 비동기 작업을 처리하기 위한 객체. 서버에 데이터 요청을 보낸 후, 처리까지 시간이 걸리는 작업을 할 때 사용. 비동기 작업의 성공 또는 실패를 처리하고, 그 결과를 ‘나중에’ 사용하게 함.

## **Executor 함수**
- resolve:  비동기 작업(Promise)이 성공했을 때 실행되는 함수 
- reject: 비동기 작업(Promise)을 실패했을 때 실행되는 함수

## **Promise의 상태**
- Pending (대기 중): Promise가 시작되었지만 완료되지 않은 상태.
- Fulfilled (이행됨): Promise가 성공적으로 완료되어 결과 값을 반환한 상태.
- Rejected (거부됨): Promise가 실패하여 에러를 반환한 상태.

## **Promise의 메서드**
- then(): Promise가 이행되었을 때 실행되는 콜백 함수를 정의.
- catch(): Promise가 거부되었을 때 실행되는 콜백 함수를 정의.
- finally(): Promise의 성공 여부와 상관없이 항상 실행되는 콜백 함수를 정의.

```javascript
const promise = new Promise((resolve, reject) => {
  // 비동기 작업 실행하는 함수
  // executor

  setTimeout(() => {
    const num = null;
    if (typeof num === "number") {
      resolve(num + 10);
    } else {
      reject("num이 숫자가 아닙니다.");
    }
  }, 2000);
});

// value = 위 resolve 함수의 결과값
promise.then((value) => {
  console.log(value); //  20
});

// error = 위 reject 함수의 결과값
promise.catch((error) => {
  console.log(error); // num이 숫자가 아닙니다.
});
```

```javascript
const fetchData = () => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const success = true;
      if (success) {
        resolve({ id: 1, name: "John Doe" });
      } else {
        reject("데이터를 가져오는데 실패했습니다.");
      }
    }, 2000);
  });
};

// Promise 사용
fetchData()
  .then((data) => {
    console.log("데이터:", data); // 성공 시 resolve()가 호출되고, then() 내부의 콜백이 실행되어 result를 호출
  })
  .catch((error) => {
    console.error(error); // 실패 시 reject()가 호출되고, catch() 내부의 콜백이 실행되어 error를 출력
  });
