# 실전형 리액트 Hook

- [ ] useTitle :react document의 title을 몇개의 hooks와 함께 바꾸는것
- [ ] useInput :input의 역활
- [ ] usePageLeave :유저가 page를 벗어나는 시점을 발견하고 함수를 실행
- [ ] useClick :element를 클릭하는 시점을 발견
- [ ] useFadeIn :어떤 element든 상관없이 애니메이션을 element안으로 서서히 사라지게 만듬
- [ ] useFullscreen :어떤 element든 풀스크린으로 만들거나 일반 화면으로 돌아가게 만듬
- [ ] useHover :마우스가 올라감을 감지
- [ ] useNetwork :online또는 offline상태인지를 감지
- [ ] useNotification :notification API를 사용할 때 유저에게 알림
- [ ] useScroll :스크롤을 감지
- [ ] useTabs :tab을 이요하기 쉽게 만들어주는 것
- [ ] usePreventLeave :유저가 변경사항이나 무엇이든간에 저장하지 않고 페이지를 벗어나길 원할 때 확인
- [ ] useConfirm :기능존재의 확인
- [ ] useAxios : HTTP request client axios을 위한 wrapper같은 것

## useState

state-컴포넌트의 상태  
`const[state,setState]=useState(초기값)`
초기값으로 무거운 작업을 불러와야한다면 useState의 초기값을 콜백함수로 불러주는 것이 좋다(첫 한번만 랜더링할 수 있도록)

```js
useState(() => {
  return heavyWork();
});
```

## useEffect

> Mount - 화면에 첫 렌더링  
> Update- 다시 렌더링  
> Unmout- 화면에서 사라질 때

cleanup

```js
const Timer = (props) => {
  useEffect(() => {
    const timer = setInterval(() => {
      console.log('타이머돌아가는중...');
    }, 1000);

    return () => {
      clearInterval(timer);
      consoel.log('타이머가 종료.');
    };
  }, []);
};
```

## useRef

함수형 컴포넌트에서 useRef를 부르면 ref object를 반환해준다  
`const ref=useRef(value)`  
console.log(ref)는 `{current:value}` 이렇게 생겼다

반환된 ref는 컴포넌트의 전생애주기를 통해 유지된다(즉, 컴포넌트가 계속해서 랜더링 되어도 Unmout되기 전에는 값을 유지)

언제사용할까?

- 저장공간으로 사용(변경시, 렌더링을 발생시키지 말아야하는 값을 다룰때)  
  state의 변화->렌더링->컴포넌트내부변수들초기화  
  ref의 변화->no랜더링->변수들의 값이 유지됨
- DOM요소에 접근  
  바닐라자바스크립트의 Document.querySelector()과 같은 역할  
  `ref={ref}`로 쉽게 해당요소에 접근가능

번외) useRef를 사용하면 input의 value를 얻을 때 e.target.value 뿐 아니라 Ref.current.value로 얻을 수 있다

**특정값을 기억하고 싶을 때 useMemo와 useRef중에 무엇을 사용할까???👀❓**  
-`useMemo`는 변수의 값을 메모이제이션 기법을 이용해서 의존성 배열 내부 값이 바뀔때만 초기화(더이상 렌더링때마다 항상 초기화 되지 않는다)  
-`useRef`는 ref렌더링과 관계없이 컴포넌트의 전 생애주기를(마운트 된 이후부터 마운트 해제될때까지)통해 유지된다(렌더링과 관계없이 항상 같은 ref객체를 반환)  
※ 기억하고 싶은 값이 렌더링과 관련이 있다면 useMemo, 그렇지 않다면 useRef를 사용

## useContext + contextAPI

context는 앱 안에서 전역적으로 사용되는 데이터를 여러 컴포넌트끼리 쉽게 공유할수있는 방법을 제공

그럼 프롭스를 왜 사용하지🤔?  
Context를 사용하면 컴포넌트를 재사용하기 어려워질 수 있다  
따라서 컴포넌트합성을 먼저 고려한 후에 useContext를 사용하자

사용방법은요?  
1.전역으로 사용할 데이터 파일을 생성한다

```js
//ThemeContext.js
import { createContext } from 'react';
export const ThemContext = createContext(null); //null이 들어간 자리는 초기값자리
```

2.context를 불러와서 전역으로 줄수있도록 하위 컴포넌트를 감싸주고 value로 전달할 값을 넣어준다 (이러면 props가 필요가 없어진다)

```js
//parent.js에 위 파일을 import해서 사용
import {ThemContext} form "./context/ThemContext"
import {useState} from  "react"

function Parent(){
    const [isDark,setIsDark]=useState(false)
    return(
        <ThemeContext.provider value={{isDark,setIsDark}}>
            <children/>
        </ThemeContext.provider>

    )
}
```

3.children컴포넌트는 값이 전혀 필요없기 때문에 정보를 받아오지 않음(불필요한 props가 사라짐)

```js
//자식컴포넌트(children.js)
const Children = () => {
  return (
    <div>
      <Header />
      <Context />
      <Footer />
    </div>
  );
};
```

4. useContext를 사용해서 받아온다

```js
//자식컴포넌트 (header.js)
import React,{useContex} from "react"
import {themeContext} from
const Header=()=>{
    const {isDark} =useContext(ThemeContext)
    return(
        <header>
            style={{
                backroundColor:isDark? "black":"yellow",
                color: isDark? "white":"black"
            }}
        </header>
    )
}

```

즉, value로 넣어준 값을 프롭스 없이도 사용할 수 있게된다

## useMemo

컴포넌트 최적화하는 방법
자주쓰이는 값을 캐싱해서 memoize한다(하지만 이 과정에 메모리를 사용하여 저장하기 때문에 필요없는 값을 넣어 기억시킬 필용는 없다)  
렌더링 -> component함수 호출,Memoization -> 렌더링 -> component함수호출,Memoize된 값을 제사용

```js
const value = useMemo(() => {
  return 함수();
}, [item]);
```

## react.Memo

props.check!! 오직 Props변화에만 의존하는 최적화방법

```js
import React,{memo} from "react"

const Child=({name,age})=>{
    return(
        <div>
            <h3>자녀</h3>
            <p>name:{name}<p/>
            <p>age:{age}</p>
        </div>
    )
}

    export default memo(child)  //child컴포넌트가 prop인 name이나 age에 변화가 없다면 렌더링되지 않는다
```

문제점은 props를 객체로 넘겨주면 값이 바뀐걸로 인식하여 리렌더링이 발생한다  
이때 해결방법으로 useMeMo와 useCallback을 함께 써주면 해결할수있다

## useCallback

컴포넌트 최적화하는 방법  
렌더링 -> component함수호출 ->memoize된 함수를 재사용

함수컴포넌트는 함수다. 함수컴포넌트는 상태 변화시 다시 랜더링된다  
렌더링시, 함수 내부 변수는 초기화가 된다(함수는 객체이다)  
초기화가 된다는건 새로운 객체가 다시 만들어지고, 메모리 주소도 새로 생성된다  
그 말은 렌더링 전 변수와, 렌더링 후 변수가 다르다 {A}==={B}//false  
이렇게되면 useEffect에서 의존성 배열은, 객체 구분을 하지 못하고 레더링이 계속 일어난다

👍 이것이 핵심!

- `문제점`- useEffect,react.Memo는 객체 초기화를 멈추지 않으면 , 랜더링이 계속 발생한다
- `해결책`-useMemo,useCallback => 객체(함수)자체를 Memoization해준다(값과 콜백을 메모리 어딘가에 저장해두고 필요할 때 가져다 쓴다)
- `아직 헷갈려??`  
  useMemo는 어떠한 "값"을 메모이징하기 위한것
  useCallback은 어떠한 "함수"를 메모이징하기 위한 것

```js
const calculate = useCallback(
  (num) => {
    return num + 1;
  },
  [item]
);
//calulate()함수자체를 callback
```

## useReducer

여러개의 하위값을 포함하는 복잡한 state를 다루어야할 때 useReducer을 사용
<img src="/Users/blair/Desktop/C/GitHub/TIL/react/usereducer.png"/>

- reducer - state를 업데이트 하는 역할(ex.은행)
- dispatch -state 업데이트를 위한 요구
- action -요구의 내용

`Dispatch(Action)--->Reducer(State,Action)--undate-->State`

```js
import React,{useState, useReducer} from "react"

const reducer=(state,action)=>{
    switch(action.type){
        case "deposit":
            return state+action.payload //입금
        case "withdraw":
            return state-action.payload //출금
        default:
            return state
    }
}

function App(){
    const [number,setNumber]=useState(0);
    const [money,dispatch]=useReducer(reducer,0)

    return(
        <div>
        <P>잔고:?원</p>
        <input
            type="number"
            value={number}
            onChange={(e)=>setNumber(parseInt(e.target.value))}
            step="1000" //1000단위로 변경
        />
        <button onClick={()=>{dispatch({type:"deposit",payload:number})}}>예금</button>
        <button onClick={()=>{dispatch({type:"withdraw",payload:number})}>출금</button>

        </div>
    )
}
```

## custom Hooks

필요한 기능들을 담은 새로운 함수를 만드는것  
return값으로 배열을 받는다

예를들어 input과 관련된 새로운 훅을 생성한다고 가정

```js
//새로운 파일로 커스텀훅을 생성한다
//useState,handleChange,handlesubmit을 가진 훅을 생성
import { useState } from 'react';

export function useInput(initialValue, submitAction) {
  const [inputValue, setInputValue] = useState(initialValue);

  const handleChange = (e) => {
    setInputValue(e.target.value);
  };

  const handleSubmit = () => {
    setInputvalue('');
    submitAction(inputValue);
  };

  return [inputValue, handleChange, handleSubmit];
}
```

```js
import { useInput } from './useInput'; //만든 훅을 import해준다

function displayMessage(message) {
  alert(message);
}

function App() {
  const [inputValue, handleChange, handleSubmit] = useInput('', displayMessage); //커스텀훅을 사용

  return (
    <div>
      <input value={inputValue} onChange={handleChange} />
      <button onClick={handleSubmit}>확인</button>
    </div>
  );
}
export default App;
```
