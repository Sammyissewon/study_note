# filter() 
: find()는 단 1개의 true 값을 찾는 메서드라면, filter()는 조건에 맞는 요소 전체를 담은 배열을 반환. 

```javascript
let results = arr.filter(function(item, index, array) {
  // 조건을 충족하는 요소는 results에 순차적으로 더해집니다.
  // 조건을 충족하는 요소가 하나도 없으면 빈 배열이 반환됩니다.
});
```
```javascript
let users = [
  {id: 1, name: "John"},
  {id: 2, name: "Pete"},
  {id: 3, name: "Mary"}
];

// 앞쪽 사용자 두 명을 반환합니다.
let someUsers = users.filter(item => item.id < 3);

alert(someUsers.length); // 2
```

- filter(Boolean): 배열의 각 요소를 Boolean으로 변환 후, true인 값만 남겨두고, false인 값은 제거.
```javascript
const array = [0, 1, false, 2, '', 3, null, 'hello', undefined, NaN];

// `filter(Boolean)` 적용
const filteredArray = array.filter(Boolean);

console.log(filteredArray); 
// 출력: [1, 2, 3, 'hello']
```
