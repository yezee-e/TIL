# React

## install react

`npx create-react-app my-app` react app설치(my-app 폴더에 개발환경을 세팅하겠다는 뜻)  
`npm start` html에서 open with live server와 같이 미리보기같은 기능  
`npm i prop-types` prop-type변경에 warning을 주는 기능(이때 i는 install의 약자  
`npm install react-router-dom` React Router을 사용  
`npm i gh-pages` 결과물은 github pages에 업로드할 수 있게 해주는 패키지

## why react?

바닐라 자바스크립트를 쓴 브라우저는 노드정보가 바뀔때마다 노드트리를 처음부터 다시 생성(5단계에 걸쳐)  
리액트는 가상돔을 사용해서 우리 시아에 보이는 부분만 수정하고 몯ㄴ 업데이트가 끝나면 일괄로 합쳐서 실제 돔에 던져준다

## basic of react

🐝 **JSX** -javascript를 확장한 문법

- jsx문법  
  -컴포넌트의 첫글자는 반드시 대문자여야한다
  -JSX는 class,for과 같이 javascript에서 섬점된 문법 용어를 사용 못한다  
  class는 className으로 for은 htmlFor로 바꿔서 쓴다  
  -변수를 넣을 땐 { } ->데이타바인딩  
  -style 넣을 땐 style={{스타일명:"값"}}

  > `<h4 style={{color:"red",fontSize="16px"}}></h4>`  
  >  기존의 css는 font-size로 표기하지만 js파일이기 때문에 -로 인식한다  
  > 따라서 카멜문법을 사용하여 스타일 부여

  -jsx closing `<div/>`와 같이 닫는 태그를 부여해줘야한다, 셀프 클로징도 가능 -모든 JSX tag는 하나의 부모 tag로 감싸져있어야 한다  
  -React.Fragment tag(실제 dom에는 추가되지 않으면서 jsx들을 그룹화 하기 위해서만 사용)  
  같은 효과를 위해 빈꺽쇠가 열리고 닫히는 형태로 표현 `<></>`

## STATE

state 언제 싸야함? 변동시 자동으로 html에 반영되게 하고 싶은면 사용  
🐝 **`useState()`**  
useState()는 array를 제공한다  
배열의 첫번째 값은 초기값이고 두번째 요는 그 값을 바꾸는 함수

🐝 **state를 세팅하는 2가지 방법**

1. 직접할당: setCounter(counter + 1)
2. 함수를 할당: setCounter((current) => current + 1)

> 현재 state랑 관계없는 값을 새로운 state로 하고 싶은 경우에는 (1)

> 현재 state에 조금의 변화를 주어 새로운 state를 주고 싶은 경우에는 (2)  
> 함수를 보낼 때 react.js는 함수의 첫번째 argument로 현재 state를 보내어 현재 state를 계산하거나 새로운 state를 만드는데 사용할 수 있게 된다

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

**결론은 컴포넌트에는 HTML element처럼 속성을 지정해줄 수 없다.
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

- **`Prop Types`**  
  install: `npm i prop-types`  
   리액트는 파라미터를 잘못넘겨도 확인할 수 없다는 문제점이 존재한다  
   이런 실수를 줄이기 위해서 PropTypes라는 모듈이 도움을 받을 수 있다  
   (type과 다를경우 warning을 뜨게할 수 있고 prameter에 값을 넣지 않은 경우에도 경고 메시지를 띄울 수 있다)

  ```js
  import PropTypes form "prop-types"

  함수명.propTypes={
    id:PropTypes.number.isRequired, //타입설정과 필수값지정할수있다
    img:PropTypes.string.isRequired,
    genres:PropTypes.arrayOf(PropTypes.string),
  }
  ```

## EFFECTS

- **`useEffect`** => 코드가 딱 한번만 실행될 수 있도록 보호
  코드의 실행 시점을 관리할 수 있는 선택권을 얻는 방어막 같은 존재, 디펜던시가 없을 경우 최초 1회 실행,  
  디펜던시가 있을경우 해당값이 변할 경우 실행한다. 이때 디펜던시는 여러개 입력이 가능
  대표적인 사용법은 API를 딱 한번만 호출하고 그 뒤로는 다시 호출하기 싫은 경우

  cleanup function: 컴포넌트가 destroy될 때도 코드를 실행할 수 있다(return으로 함수를 만들어준다)  
  useEffect의 subscription을 종료할 때 즉, 컴포넌트가 unmount될 때 실행할 로직은 useEffect의 EffectCallback에서 반환되는 함수로 구현한다  
  여기서 반환되는 함수를 cleanup function이라고 부르고 메모리 누수를 방지하기 위해 사용

  useeffect는 화면이 다 그려지고 나서 실행된다.

  clean-up이 필요한 effect->react는 컴포넌트가 마운트 해제되는 때에 정리를 실행한다  
  즉, 컴포넌트가 unmout될 때 실행할 로직은 useEffect의 effectCallback에서 반환되는 함수로 구현한다. 여기서 반환되는 함수를  
  cleanup function이라고 부르고 메모리 누수를 방지하기 위해 사용된다

  ```js
  useEffect(() => {
    console.log("i run when 'keyword and counter' changes.");
    return () => console.log('destroyed:('); //Cleanup(컴포넌트가 정리 될 때도 코드를 실행)
  }, [keyword, counter]);
  //[]자리에 특정한 코드만 변화했을 때 원하는 코드들을 실행할 수 있는 방법(즉, []변화할 때 코드를 실행할 거라고 react.js에게 알려주는 것)
  // 빈 array를 써주었을 때는 react가 지켜볼게 아무것도 없으니 처음 한번만 실행되는 것
  //[]안에 여러 디팬던시 입력가능
  ```

- **`React.memo()`** => 불필요한 re-render를 관리  
  부모 컴포넌트의 state를 변경하면 그 자식 컴포넌트들도 re-render가 일어남  
  불필요한 렌더링이 발생할수도 있는데 이 경우에 react.memo()로 prop의 변경이 일어난 부분만 렌더링시킬 수 있다(이즈믾은 자식 컴포넌트를 가지고 있는 부모컨포넌트일 때 사용)  
  고차 컴포넌트(higher order component)  
  컴포넌트가 동일한 pros로 동일한 결과를 렌더링 해낸다면 React.memo를 호츨하고 결과를 메모이징(memoizing)하도록 래핑하여  
  경우에 따라 성능 향상을 누릴 수 있다
  즉, React는 컴포넌트를 렌더링하지 않고 마지막으로 렌더링된 결과를 재사용

  ```js
  const memorizedBtn = React.memo(btn);
  function app() {
    const [value, setvalue] = React.useState('');
    return (
      <div>
        <memorizeBtn text={value} />
        //원래 컴포넌트이름이 btn이였지만react.memo()로 컴포넌트사용
      </div>
    );
  }
  ```

  => Memo stops the component from re-rendering if the props haven't changed  
   useEffect runs a function when the props change, or only at the start or end of the component's lifecycle

## css

react에서 css를 사용하는 방법은 다양하다  
1.style.css폴더를 만들어서 import하여 모든 css를 관리하는방법 간편하지만 단점으로 여러 컴포넌트에서 사용한 Class Name에 중복발생 가능성이 높다  
2.html 태그 안에 직접 입력하는 방법. style={{}} 형식으로 입력  
3.React에서 제공하는 CSS module 이용

- 클래스명이 충돌하는 단점을 해결(같은 클래스의 이름이라도 클래스이름을 램덤방식으로 생성해줘서 겹치지 않는다)
- 컴포넌트 단위로 스타일을 적용할 수 있다

```js
import styles from './App.module.css'; //기존 css와 다르게 파일명에 module을 넣는다

function App() {
  return (
    <div>
      <h1 className={style.title}>welcome!</h1>
    </div>
  );
}
```

```css
.title {
  color: tomato;
}
```

  <br/>

## react router

> **라우팅이란?🧐**
> 사용자가 요청한 URL에 따라 해앋 URL에 맞는 페이지를 보여주는 것
> URL및 특정한 HTTP요청메소드(GET,POST...)인 특정 엔드포인트에 대한 클라이언트 요청에 어플리케이션이 응답하는 방법을 결정한다

- 종류:가장 많이 사용하는 라우터 컴포넌트는
  1.BrowserRouter:HTML5를 지원하는 브라우저의 주소를 감지
  2.HashRouter:해시주소를 감지,뒤에 #을 붙인다(예를 들어 localhost:3001/#/movie)
- 설치
  `npm install react-router-dom`

![](https://velog.velcdn.com/images/yezee/post/b4f3dc8e-afb7-4c29-b74c-5d345d44919b/image.png)

라우터(브라우저 라우터)를 import한다
`import { BrowserRouter as Router, Routes, Route } from 'react-router-dom';`

Router>Routes>Route 순으로 컴포넌트가 구성되어 있다

- `Router`:path에 따라 랜더링해주는 역할
- `Routes`:한번에 하나의 Route만 렌더링 하기 위해서
- `Route`: 경로(=path)와 보여줄 컴포넌트(=element)를 명시한다

## parameters

Routes의 path 뒤에 `:변수명`는 파라미터를 사용하기 위해 쓰이는 변수다

```js
<Route path='/movie/:id' element={<Detail />} />
```

` const { 변수명 } = useParams();` 로 파라미터를 import한다
fetch를 통해 받아온 URL에 변수를 같이 넣어 사용하면 원하는 URL을 정확히 가져올 수 있다

```js
import { useParams } from 'react-router-dom';

const { id } = useParams();
const getMovie = async () => {
  const json = await (
    await fetch(`https://yts.mx/api/v2/movie_details.json?movie_id=${id}`)
  ).json();
  console.log(json);
};
```

## `<Link></Link>`컴포넌트

HTML에서는 원래 링크를 만들 때 a태그를 사용한다. 하지만 a태그는 클릭시 페이지를 새로 불러오기 때문에 React에서는 Link를 사용

**단순 경로로 이동**

```js
import { Link } from 'react-router-dom'; //Link컴포넌트사용
<Link to='/경로'>{링크명}</Link>;
```

**변수가 있는 경로로 이동**

```js
import { Link } from 'react-router-dom'; //Link컴포넌트사용
<Link to={`경로${변수명}`}>{링크명}</Link>;
```

이동할 변수의 id(값)를 받아와야한다
`import {useParams} from "react-router-dom"` 을 해당 변수를 가진 컴포넌트 페이지에 install

```js
import { useParams } from 'react-router-dom';

function Detail() {
  const { id } = useParams();
  const getMovie = async () => {
    const json = await (await fetch(`https://urlulrulr?id=${id}`)).json();
  };
}
export default Detail;
```

Link컴포넌트에서 to={}안에 경로에 변수를 이용해서 브라우저 주소의 경로만 바꿔 보여주는 것이 가능하다

## Publishing

Route컴포넌트의 path경로 앞에 `process.env.PUBLIC_URL`을 추가해서 수정

```js
Route path={process.env.PUBLIC_URL+"/"} element={<Home/>}
또는
Route path={`${process.env.PUBLIC_URL}/`} element={<Home/>}
```

`npm i gh-pages` 결과물은 github pages에 업로드할 수 있게 해주는 패키지설치  
`npm run build` 우리 웹사이트의 production ready code를 생성(코드가 압축되고 모든게 최적화)

build라는 폴더가 생성된다(브라우저가 이해할수있는 코드가 담겨있다)

package.json안에 아래쪽에 homepage를 작성한다  
`"homepage": "https://<username>.github.io/<github repository name>"`

package.json안에있는 "scripts"안에 deploy와 predeploy를 작성한다
`"deploy":"gh-pages -d build"`
`"predeploy":"npm run build"`
(npm run build를 실행하면 Node.js가 predeploy를 먼저 실행시켜준다,즉 build가 없다면 먼저 만들고 deploy를 실행시켜준다)

## 알아두면 짱 유용할껄??

- /_eslint-disable_/ lint(warning message)끄는 말(맨위에 포스트)
- Reactjs code snippets 단축키  
  rsc-화살표 함수형 컴포넌트 생성  
  rsf-함수형 컴포넌트생성  
  ( 뒤에 p를 추가하면 propTypes 구조를 추가해준다!!)

  imr-리액트가져오기(=import React form "react")
