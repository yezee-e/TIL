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
  setToDos(todo.filter((item,todoIndex)=>index!==todoIndex))
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
