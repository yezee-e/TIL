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

## input으로 리스트만들기

```js
function Todo(){
  const [todo,setTodo]=useState("") //input에 입력하는값
const [toDos,setToDos]=useState([]) //input에 입력한 값의 배열
const onChange=(e)=>setTodo(e.target.value)
const onSubmit=(e)=>{
  e.preventDefault()
  setToDos((currentArray)=>[todo,...currentArray]) //기존의값을 가진 배열에 새로운 값을 추가
}
const deleteBtn=(index)=>{
  setToDos(todo.filter((item,todoIndex)=>index!==todoIndex)) //리스트제거버튼
}
  return(
  <div>
    <form onSubmit={onSubmit}>
    <input onChange={onChange} value={todo}/>
    <button>Add ToDo</button>
    </form>
    <ul>
    {toDos.map((item,index)=><li key={index}>
    {item}
    <button onClick={()=>deleteBtn(index)}>❌</button>
    <li>)}
    </ul>
</div>
  )
}

```

`onClick={deleteBtn}`이 아닌 `onClick={()=>deleteBtn(index)}`이렇게 쓰는 이유는 "바로실행"되지 않고 클릭을 기다리는 함수로 쓰기위해

## fetch

**fetch-then**

```js
const [coins, setCoins] = useState([]);

function App() {
  useEffect(() => {
    fetch('<url>')
      .then((res) => res.json())
      .then((json) => setCoins(json));
  }, []);

  return (
    <select>
      {coins.map((coin) => (
        <option>{coin.name}</option>
      ))}
    </select>
  );
}
```

**async-await(1)**
await는 async 함수 내부에 있지 않으면 사용할 수 없다

```js
const [coins, setCoins] = useState([]);

function App() {
  const getCoins = async () => {
    const response = await fetch('<url>');
    const json = await response.json();
    setCoins(json);
  };

  useEffect(() => {
    getCoins();
  }, []);

  return (
    <select>
      {coins.map((coin) => (
        <option>{coin.name}</option>
      ))}
    </select>
  );
}
```

**async-await(2)**

```js
const [coins, setCoins] = useState([]);

function App() {
  const getCoins = async () => {
    const json = await (await fetch('<url>')).json();
    setCoins(json);
  };

  useEffect(() => {
    getCoins();
  }, []);

  return (
    <select>
      {coins.map((coin) => (
        <option>{coin.name}</option>
      ))}
    </select>
  );
}
```

## map과 props

key는 map안에서 component들을 render할 때 사용

```js
<div>
  {movies.map((movie) => (
    <Movie key={movie.id} id={movie.id} />
  ))}
</div>
```
