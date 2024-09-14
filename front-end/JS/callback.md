**Callback function (콜백 함수)**
: A함수가 B함수를 인자로 받고, A함수 작업 완료 후 B함수를 실행. 이때 B함수가 콜백함수. 

```javascript
function fetchData(callback) {
  setTimeout(() => {
    const data = { id: 1, name: "John Doe" };
    callback(data); 
  }, 2000);
}

function displayData(data) {
  console.log("Received Data:", data);
}

fetchData(displayData);
```

**setTimeout**
:일정 시간이 지난 후에 콜백 함수를 실행
- 첫 번째 인자로 콜백 함수
- 두 번째 인자로 지연 시간(밀리초 단위)
- 세 번째 이후 인자로 콜백 함수에 전달될 인자

```javascript
function sayHi(who, phrase) {
  alert( who + ' 님, ' + phrase );
}

setTimeout(sayHi, 1000, "홍길동", "안녕하세요.");

