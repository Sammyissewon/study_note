# **async**
: function 앞에 async를 붙이면 해당 함수는 항상 프라미스를 반환

# **await**
- `await` 키워드를 만나면 Promise가 처리될 때까지 대기. Promise가 처리되면 그 결과와 함께 실행 재개.
- Promise 처리 중에 엔진이 다른 일을 하도록 함.

```javascript
const whereAmI = async function (country) {

  const res = await fetch(`https://restcountries.com/v2/name/${country}`);
  const data = await res.json();
  // renderCountry(data[0]);
};

whereAmI('portugal');
console.log('First');
```
```javascript
function timer(time) {
  return new Promise(function (resolve) {
    setTimeout(function () {
      resolve(time);
    }, time);
  });
}
console.log('start');

timer(1000)
  .then(function (time) {
    console.log('time' + time);
    return timer(time + 1000);
  })
  .then(function (time) {
    console.log('time' + time);
    return timer(time + 1000);
  })
  .then(function (time) {
    console.log('time' + time);
    console.log('end');
  });
```
```javascript
const run = async function () {
  console.log('start');
  let time = await timer(1000);
  console.log('time:' + time);

  time = await timer(time + 1000);
  console.log('time:' + time);

  time = await timer(time + 1000);
  console.log('time:' + time);
  console.log('end');
};

run();
```
