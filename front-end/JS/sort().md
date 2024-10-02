# sort()
- 배열의 요소를 적절한 위치에 정렬한 후 그 **배열**을 반환.
- 정렬된 배열은 원 배열에서 정렬되는 것이며, 복사본이 만들어지는 것이 아님.
- 기본 정렬 순서는 문자열의 유니코드 코드 포인트를 따른다.

## CompareFunction

```jsx
function compareNumbers(a, b) {
  return a - b;
}
```

- `a - b`의 결과가 음수면 `a`가 `b`보다 앞에 배치됩니다. 됐음
- `a - b`의 결과가 양수면 `b`가 `a`보다 앞에 배치됩니다.
- `a - b`가 `0`이면 순서가 변경되지 않습니다.

```jsx
// 1
const fruits = ["grape", "apple", "banana", "orange"];
fruits.sort();
console.log(fruits);

// 2
const numbers1 = [15, 3, 9, 1, 20];
numbers1.sort((a, b) => a - b);
console.log(numbers1);

// 3
const numbers2 = [42, 7, 13, 98, 55];
numbers2.sort((a, b) => b - a);
console.log(numbers2);

// 4
const people = [
  { name: "John", age: 25 },
  { name: "Jane", age: 22 },
  { name: "Mike", age: 30 },
];
people.sort((a, b) => a.age - b.age);
console.log(people);

// 5
const animals = ["elephant", "cat", "giraffe", "dog", "hippopotamus"];
animals.sort((a, b) => a.length - b.length);
console.log(animals);

// 6
const products = [
  { name: "Laptop", price: 1000 },
  { name: "Phone", price: 800 },
  { name: "Tablet", price: 600 },
  { name: "Monitor", price: 600 },
];

// 7
products.sort((a, b) => {
  if (a.price === b.price) {
    return a.name.localeCompare(b.name);
  }
  return a.price - b.price;
});
console.log(products);

// 8
const dates = ["2023-05-15", "2021-08-02", "2022-12-25", "2020-01-01"];
dates.sort((a, b) => {
  return new Date(a) - new Date(b);
});
console.log(dates);

```
