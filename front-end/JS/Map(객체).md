# Map(객체)
- Map 객체는 키-값 쌍인 집합
- `new Map( )`: 새로운 map을 생성
- `map.set(key, value)`: 키를 이용해 값을 저장
    
    ```jsx
    let map = new Map();
    
    map.set('1', 'str1'); // 문자형 키
    map.set(1, 'num1'); // 숫자형 키. 1째 줄이 이미 추가됨
    map.set(true, 'bool1'); // 불린형 키. 1,2째 줄이 이미 추가됨
    
    console.log(map);
    // Map(3) {'1' => 'str1', 1 => 'num1', true => 'bool1'}
    
    ```
    
    ```jsx
    const rest = new Map();
    
    rest.set('name', 'Classico Italiano');
    rest.set(1, 'Firenze, Italy');
    
    console.log(rest.set(2, 'Lisbon, Portugal'));
    // Map(3) {'name' => 'Classico Italiano', 1 => 'Firenze, Italy', 2 => 'Lisbon, Portugal'}
    ```
    
- `map.get(key)`: key에 해당하는 값을 반환. key가 존재하지 않으면 undefined를 반환.
- `map.has(key)`: key가 존재하면 `true`, 존재하지 않으면 `false`를 반환.
- `map.delete(key)`: key에 해당하는 값을 삭제.
- `map.clear`: 맵 안의 모든 요소를 제거.
- `map.size`: 요소의 개수를 반환.

    ```jsx
    const myMap = new Map();
    
    const keyString = "a string";
    const keyObj = {};
    const keyFunc = function () {};
    
    // 값 설정
    myMap.set(keyString, "value associated with 'a string'");
    myMap.set(keyObj, "value associated with keyObj");
    myMap.set(keyFunc, "value associated with keyFunc");
    
    console.log(myMap.size); // 3
    
    // 값 불러오기
    console.log(myMap.get(keyString)); // "value associated with 'a string'"
    console.log(myMap.get(keyObj)); // "value associated with keyObj"
    console.log(myMap.get(keyFunc)); // "value associated with keyFunc"
    
    console.log(myMap.get("a string")); // "value associated with 'a string'", 왜냐하면 keyString === 'a string'
    console.log(myMap.get({})); // undefined, 왜냐하면 keyObj !== {}
    console.log(myMap.get(function () {})); // undefined, 왜냐하면 keyFunc !== function () {}
