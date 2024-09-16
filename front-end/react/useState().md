# useState() - 상태 관리하기

: 임시로 현재 데이터 저장하는 함수
- `useState()`는 두개의 값을 반환하는데,  `const [현재값, 상태변화 '함수'] = useState(””)`
- 수시로 바뀌는 데이터들은 변수말고 `state`를 사용
    - 새로고침 없이 재렌더링할 수 있기 때문
 
```javascript
function App() {
  const [count, setCount] = useState(0);
  const [light, setLight] = useState("Off");

  return (
    <>
      <div>
        <h1>{light}</h1>
        <button
          onClick={() => {
            setLight(light === "On" ? "Off" : "On");
          }}
        >
          {light === "On" ? "Off" : "On"}
        </button>
      </div>

      <div>
        <h1>{count}</h1>
        <button
          onClick={() => {
            setCount(count + 1);
          }}
        >
          +
        </button>
      </div>
    </>
  );
}
```

## set 함수 안에서의 함수 지정: `setNum(num + 1)` vs `setNum((prev) => prev + 1)`
- `setNum(num + 1)`
  - 동작 방식: num 값이 변경될 때마다 새로운 값이 바로 num + 1로 업데이트됩니다.
  - 문제점: 상태 업데이트가 비동기적으로 처리되기 때문에, 이전 값이 즉시 반영되지 않을 수 있습니다. 연속해서 상태를 업데이트할 경우, num 값이 최신 상태가 아닐 수도 있기 때문에 의도한 대로 작동하지 않을 수 있습니다.

- `setNum((prev) => prev + 1)`
  - 이 방식은 함수형 업데이트로, 이전 상태를 인자로 받아서 그 값을 기반으로 상태를 업데이트합니다.
  - 동작 방식: prev는 항상 최신 상태 값을 참조합니다. 이는 React가 비동기적으로 상태 업데이트를 처리할 때도 정확하게 이전 값을 기반으로 상태를 업데이트할 수 있도록 해줍니다.
