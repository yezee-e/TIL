# React 활용편

자주쓰이고 다양한 활용예제를 통해 react를 정리

<br/>

## 토글만들기

event로 토글함수를 주면 event가 발생할 때마다 current값에 대한 반대값을 받는다

```js
const [inverted, setInverted] = React.useState(false);
const onInvert = () => {
  setInverted((current) => !current);
};
```
