# Array.from()
- 순회 가능 또는 유사 배열 객체에서 얕게 복사된 새로운 `Array` 인스턴스를 생성
- 구문
    
```jsx
Array.from(arrayLike) // 배열로 변환할 순회 가능 또는 유사 배열 객체
Array.from(arrayLike, mapFn) // 배열의 모든 요소에 대해 호출할 함수
```
    
```jsx
console.log(Array.from('foo'));
// Expected output: Array ["f", "o", "o"]

console.log(Array.from([1, 2, 3], (x) => x + x));
// Expected output: Array [2, 4, 6]
```
