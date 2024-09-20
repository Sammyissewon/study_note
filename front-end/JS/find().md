# `find()`
- 객체로 이루어진 배열에서 반환 값이 `true`인 단 하나의 요소(객체)를 찾아주는 메서드.
- 함수가 `true`을 반환하면 탐색은 중단되고 해당 요소가 반환된다. 원하는 요소를 찾지 못했으면 `undefined`가 반환된다.
    
    ```jsx
    let result = arr.find(function(item, index, array) {
      // true가 반환되면 반복이 멈추고 해당 요소를 반환.
      // 조건에 해당하는 요소가 없으면 undefined를 반환.
    });
    ```
    
    - `item` – 함수를 호출할 요소
    - `index` – 요소의 인덱스
    - `array` – 배열 자기 자신

    
    ```jsx
    let users = [
      {id: 1, name: "John"},
      {id: 2, name: "Pete"},
      {id: 3, name: "Mary"}
    ];
    
    let user = users.find(item => item.id == 1);
    
    alert(user.name); // John
    ```
