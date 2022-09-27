# React

## basic of react

🐝**JSX**  
 -javascript를 확장한 문법  
 -JSX는 class,for과 같이 javascript에서 섬점된 문법 용어를 사용 못한다  
 class는 className으로 for은 htmlFor로 바꿔서 쓴다

## STATE

🐝**useState()**  
useState()는 array를 제공한다  
배열의 첫번째 값은 초기값이고 두번째 요는 그 값을 바꾸는 함수

🐝**state를 세팅하는 2가지 방법**

1. 직접할당: setCounter(counter + 1)
2. 함수를 할당: setCounter((current) => current + 1)

> 현재 state랑 관계없는 값을 새로운 state로 하고 싶은 경우에는 (1)
> 현재 state에 조금의 변화를 주어 새로운 state를 주고 싶은 경우에는 (2)

```js
function App() {
  const [counter, setCounter] = React.useState(0); //useState() 배열의 첫번째 값은 초기값이고 두번째 요소는 그 값을 바꾸는 함수
  const onClick = () => {
    setCounter((current) => current + 1); // setCounter(counter + 1); 와 같다 , 현재 state를 바탕으로 다음 state를 계산해내고 싶다면 current함수를 사용
  };
  return (
    <div>
      <h3>Total click:{counter}</h3>
      <button onClick={onClick}>Click me</button>
    </div>
  );
}
```
