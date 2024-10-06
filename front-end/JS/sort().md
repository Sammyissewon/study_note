# sort()
- 배열의 요소를 적절한 위치에 정렬한 후 그 **배열**을 반환.
- 정렬된 배열은 원 배열에서 정렬되는 것이며, 복사본이 만들어지는 것이 아님.
- 기본 정렬 순서는 문자열의 유니코드 코드 포인트를 따른다.

## CompareFunction

```jsx
const fruits = ["grape", "apple", "banana", "orange"];
fruits.sort();
console.log(fruits);
//['apple', 'banana', 'grape', 'orange']



const numbers1 = [15, 3, 9, 1, 20];
numbers1.sort((a, b) => a - b);
console.log(numbers1);
//[1, 3, 9, 15, 20]



const numbers2 = [42, 7, 13, 98, 55];
numbers2.sort((a, b) => b - a);
console.log(numbers2);
//[98, 55, 42, 13, 7]



const people = [
  { name: "John", age: 25 },
  { name: "Jane", age: 22 },
  { name: "Mike", age: 30 },
];
people.sort((a, b) => a.age - b.age);
console.log(people);
// [{name: 'Jane', age: 22},
// {name: 'John', age: 25},
// {name: 'Mike', age: 30}]



const animals = ["elephant", "cat", "giraffe", "dog", "hippopotamus"];
animals.sort((a, b) => a.length - b.length);
console.log(animals);
//['cat', 'dog', 'giraffe', 'elephant', 'hippopotamus']



const products = [
  { name: "Laptop", price: 1000 },
  { name: "Phone", price: 800 },
  { name: "Tablet", price: 600 },
  { name: "Monitor", price: 600 },
];

products.sort((a, b) => {
  if (a.price === b.price) {
    return a.name.localeCompare(b.name);
  }
  return a.price - b.price;
});

console.log(products);
// [{name: 'Monitor', price: 600},
// {name: 'Tablet', price: 600},
// {name: 'Phone', price: 800},
// {name: 'Laptop', price: 1000}]



const dates = ["2023-05-15", "2021-08-02", "2022-12-25", "2020-01-01"];
dates.sort((a, b) => {
  return new Date(a) - new Date(b);
});
console.log(dates);
//['2020-01-01', '2021-08-02', '2022-12-25', '2023-05-15']



const str = "The quick brown fox jumps over the lazy dog.";
const words = str.split();
console.log(words);
//['The quick brown fox jumps over the lazy dog.']

```
