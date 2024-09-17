# map 함수

: 배열 내의 모든 요소 각각에 대하여 주어진 함수를 호출한 결과를 모아 새로운 배열을 반환.

- 구문
    
    ```jsx
     arr.map(callback(currentValue[, index[, array]]))
    ```
    
    - [`callback`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/map#callback) : 새로운 배열 요소를 생성하는 함수.  
    - [`currentValue`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/map#currentvalue) (옵션): 처리할 현재 요소.
    - [`index`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/map#index) (옵션): 처리할 현재 요소의 인덱스.
    - [`array`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/map#array) (옵션): `map()`을 호출한 배열.
    
- 반환 값: 배열의 각 요소에 대해 실행한 `callback`의 결과를 모은 새로운 배열.
- 기능
    
  1. **array ‘요소 갯수 만큼’ 함수 안의 코드 실행해 줌**
    
    ```jsx
    [1,2,3].map(() => {
    console.log(1)
    }   
    
    // 1(3번 호출)
    ```
    
  2. **array 요소가 함수의 인자로 쓰임**
    
    ```jsx
    [1,2,3].map((a) => {
    console.log(a)
    }  
    
    // 1 2 3
    ```
    
  3. **return에 뭐 적으면 요소 갯수만큼 새로운 array로 담아줌** 
    
    ```jsx
    [1,2,3].map(() => {
    	return '가나다라'
    }  
    
    // ['가나다라', '가나다라', '가나다라']
    ```
    
  4. **배열의 모든 요소를 순회하면서, 각각 콜백함수를 실행하고 그 결과값들을 모아서 새로운 배열을 반환**
    
    ```
    let arr = [1, 2, 3];
    
    const mapResult = arr.map((item, index, array) => {
      return item * 2;
    });
    
    console.log(mapResult); 
    
    // [2, 4, 6]
    ```
    
    ```jsx
    const movements = [200, 450, -400, 3000, -650, -130, 70, 1300];
    
    const euroToUsd = 1.1;
    const movementUSD = movements.map((movement) {
      return movement * euroToUsd;
    });
    
    console.log(movements);
    console.log(movementUSD);
    
    [
        200,
        450,
        -400,
        3000,
        -650,
        -130,
        70,
        1300
    ]
    [
        220.00000000000003,
        495.00000000000006,
        -440.00000000000006,
        3300.0000000000005,
        -715.0000000000001,
        -143,
        77,
        1430.0000000000002
    ]
    /////// 화살표 함수로 간략하게
    const movementUSD = movements.map(movement => movement * euroToUsd);
    
    //////// for-of 활용
    const movementsUSDfor = [];
    for (const movement of movements) movementsUSDfor.push(movement * euroToUsd);
    console.log(movementsUSDfor);
    
    // 결과: 동일
    ```
    
-
