# node

## 노드란? 비동기 이벤트 기반 javascript런타임환경이다

- 비동기: 프로그램의 다른 부분들이 서로 방해하지 않고 동시에 일어날수있다
- 이벤틔: 요청, 백엔드입장에서는 프론트앤드(클라이언트)에서 받은 요청

즉, 노드가 비동기적으로 이벤트를 처리한다는 것은 앞선 클라이언트의 요청이 끝나기 전에 다음 클라이언트의 요청을 받는다는 의미이며
js런타임환경은 js가 브라우저 없이 동작할 수 있도록 만든 환경을 뜻한다

## EXPRESS로 노드서버 띄우고 라우팅하기

express는 노드개발자들이 많이 채택하는 프레임워크로 **라우팅**과 **로직의 모듈화**를 위해 사용
설치:`npm install express`
장점:json으로 if-return없이 로직을 만들 수 있기 때문에 코드를 간결화할 수 있다

```js
const express = require('express');
const app = express();
app.use(express.json());

app.get('/', (req, res) => {
  res.json({ 내용 });
});
app.get('/', (req, res) => {
  res.json({ 내용 });
});
app.get('/', (req, res) => {
  res.json({ 내용 });
});
```
