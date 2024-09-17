## Short-Circuit (단락 평가) (&&, ||, ??)

- Short-Circuit(단락 평가): &&, ||  연산 시, 첫 번째 피연산자 값만으로도 연산의 결과를 확정할 수 있다면, 두 번째 피연산자에는 접근조차 하지 않음.
- &&, || 연산자는 Boolean타입 외에 다른 타입들에도 사용될 수 있다
- **|| 은 첫번째 truthy 피연산자(overand)를  반환한다**
    
    ```jsx
    console.log(3 || 'Sammy');
    // 3
    // 첫번째 피연산자(operand)가 truthy일 경우, 두번째 피연산자는 보지도 않는다. 
    
    console.log('' || 'Sammy'); // Sammy
    console.log(true || 0); // true
    console.log(undefined || null); // null. 둘다 falsy라서, 결국 마지막 피연산자를 반환. 
    console.log(undefined || null || 0 || '' || 'Hello'); // Hello. 참이 나오면 그 피연산자를 반환. 
    ```
    
    - ||를 if문 처럼 쓸 수 있다.
        
        ```jsx
        restaurant.numGuest = 23; // 23은 truthy 
        const guest1 = restaurant.numGuest ? restaurant.numGuest : 10;
        console.log(guest1); //23
        
        const guest2 = restaurant.numGuest || 10;
        console.log(guest2); //23
        ```
        
- **&&는 첫번째 falsy 피연산자를 반환한다**
    
    ```jsx
    console.log(0 && 'Sammy'); // 0 -> falsy 
    console.log(7 && 'Sammy'); // Sammy -> 둘다 truthy라서, 결국 마지막 피연산자를 반환. 
    console.log('hello' && 23 && null && 'Sammy'); // null
    ```
- **?? (Nullish) Assignment Operator**
    - ??는 왼쪽 값이 null 또는 undefined면, 오른쪽 값을 반환
    - 그게 아니면, 왼쪽 값 반환
    
    ```jsx
    const rest1 = {
      name: 'Rose',
      numGuest: 0,
    };
    
    const rest2 = {
      name: 'Lisa',
      owner: 'Black Pink',
    };
    
    rest1.numGuest ??= 10;
    rest2.numGuest ??= 10;
    
    console.log(rest1);
    // {name: 'Rose', numGuest: 0}
    // 0이라는 값이 할당되어 있으므로, null 또는 undefined이 아님. 
    
    console.log(rest2);
    // {name: 'Lisa', owner: 'Black Pink', numGuest: 10}
    // numGuest 할당이 없음으로 undefined.
    ```
    
-
