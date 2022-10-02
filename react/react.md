# React

## basic of react

🐝 **JSX** -javascript를 확장한 문법

- jsx문법  
  -JSX는 class,for과 같이 javascript에서 섬점된 문법 용어를 사용 못한다  
  class는 className으로 for은 htmlFor로 바꿔서 쓴다  
  -변수를 넣을 땐 { } ->데이타바인딩  
  -style 넣을 땐 style={{스타일명:"값"}}
  > `<h4 style={{color:"red",fontSize="16px"}}></h4>`  
  >  기존의 css는 font-size로 표기하지만 js파일이기 때문에 -로 인식한다
  > 따라서 카멜문법을 사용하여 스타일 부여

## STATE

state 언제 싸야함? 변동시 자동으로 html에 반영되게 하고 싶은면 사용  
🐝 **useState()**  
useState()는 array를 제공한다  
배열의 첫번째 값은 초기값이고 두번째 요는 그 값을 바꾸는 함수

🐝 **state를 세팅하는 2가지 방법**

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

## Component

어떤걸 컨포넌트로 만들면 좋은가?  
1.반복적인 html을 축약할 때  
2.큰페이지들  
3.자주변경되는 것들

## props

프롭스는 객체다  
부모 컴포넌트로부터 자식 컴포넌트에게 데이터를 전송하는 방식  
부모에 props를 사용하면 자식 컴포넌트(함수)의 인자로 객체가 들어가게된다  
prop에 function도 보낼 수 있다  
`<Btn onClick={changeValue}/>` 는 이벤트 리스너를 붙인것이 아닌 , 컨포넌트에 onClick이라는 프롭을 전달한것(여기서 onClick은 단순히 props의 이름이다)  
결론은 **컴포넌트에는 HTML element처럼 속성을 지정해줄 수 없다.
컴포넌트에 그러한 행위를 하는 것은 그저 props를 전달해 주는 것 뿐이다**

```js
// 일반적인 프롭스 사용방법
function Btn(props) {
  return <button style={{ backgroundColor: 'tomato' }}> {props.text} </button>;
}
//위에서도 언급했듯이 프롭스는 객체이다
//props.property는 그냥 {property}처럼 사용할 수 있다

function Btn({ text }) {
  return <button style={{ backgroundColor: 'tomato' }}> {text} </button>;
}
```

- **React.momo()** => 불필요한 re-render를 관리  
  고차 컴포넌트(higher order component)  
  컴포넌트가 동일한 pros로 동일한 결과를 렌더링 해낸다면 React.momo를 호츨하고 결과를 메모이징(memoizing)하도록 래핑하여  
  경우에 따라 성능 향상을 누릴 수 있다
  즉, React는 컴포넌트를 렌더링하지 않고 마지막으로 렌더링된 결과를 재사용

/_eslint-disable_/ lint(warning message)끄는 말(맨위에 포스트)
