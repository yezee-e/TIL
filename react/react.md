# React

## install react

npx create-react-app my-app로 react app설치(my-app 폴더에 개발환경을 세팅하겠다는 뜻)  
npm start :html에서 open with live server와 같이 미리보기같은 기능  
npm i prop-types :prop-type변경에 warning을 주는 기능(이때 i는 install의 약자

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

## RPOPS

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

## EFFECTS

- **useEffect** => 코드가 딱 한번만 실행될 수 있도록 보호
  코드의 실행 시점을 관리할 수 있는 선택권을 얻는 방어막 같은 존재, 디펜던시가 없을 경우 최초 1회 실행,  
  디펜던시가 있을경우 해당값이 변할 경우 실행한다. 이때 디펜던시는 여러개 입력이 가능
  대표적인 사용법은 API를 딱 한번만 호출하고 그 뒤로는 다시 호출하기 싫은 경우

  cleanup function: 컴포넌트가 destroy될 때도 코드를 실행할 수 있다(return으로 함수를 만들어준다)  
  useEffect의 subscription을 종료할 때 즉, 컴포넌트가 unmount될 때 실행할 로직은 useEffect의 EffectCallback에서 반환되는 함수로 구현한다  
  여기서 반환되는 함수를 cleanup function이라고 부르고 메모리 누수를 방지하기 위해 사용

  useeffect는 화면이 다 그려지고 나서 실행된다.

  ```js
  useEffect(() => {
    console.log("i run when 'keyword and counter' changes.");
    return () => console.log('destroyed:('); //Cleanup(컴포넌트가 정리 될 때도 코드를 실행)
  }, [keyword, counter]);
  //[]자리에 특정한 코드만 변화했을 때 원하는 코드들을 실행할 수 있는 방법(즉, []변화할 때 코드를 실행할 거라고 react.js에게 알려주는 것)
  // 빈 array를 써주었을 때는 react가 지켜볼게 아무것도 없으니 처음 한번만 실행되는 것
  //[]안에 여러 디팬던시 입력가능
  ```

- **React.momo()** => 불필요한 re-render를 관리  
  고차 컴포넌트(higher order component)  
  컴포넌트가 동일한 pros로 동일한 결과를 렌더링 해낸다면 React.momo를 호츨하고 결과를 메모이징(memoizing)하도록 래핑하여  
  경우에 따라 성능 향상을 누릴 수 있다
  즉, React는 컴포넌트를 렌더링하지 않고 마지막으로 렌더링된 결과를 재사용

  => Memo stops the component from re-rendering if the props haven't changed  
   useEffect runs a function when the props change, or only at the start or end of the component's lifecycle

## css

react에서 css를 사용하는 방법은 다양하다  
1.style.css폴더를 만들어서 import하여 모든 css를 관리하는방법 간편하지만 단점으로 여러 컴포넌트에서 사용한 Class Name에 중복발생 가능성이 높다  
2.html 태그 안에 직접 입력하는 방법. style={{}} 형식으로 입력  
3.React에서 제공하는 CSS module 이용

- 클래스명이 충돌하는 단점을 해결
- 컴포넌트 단위로 스타일을 적용할 수 있다

  <br/>

## aid

/_eslint-disable_/ lint(warning message)끄는 말(맨위에 포스트)
