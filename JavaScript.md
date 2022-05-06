## 변수의 선언 방식
***
**let:** 변수를 선언하고 재할당도 가능 언제든 값을 바꿀 수 있음   
**const:** 변수에 한번 값을 할당하면 다시 값을 바꿀 수 없음   
**var:** let의 옛날버전(let과 작동원리는 같으나 호이스팅과 같은 문제가 있음)

## 자료형과 연산자
***
**자료형**🔍
* string- 문자열 타입이라고도 한다. ""큰따옴표나 ''작은따옴표 안에 들어가 있는 값을 string타입이라고함
* 숫자- 숫자타입, 양수, 음수, 소수, 다 숫자타입   
* boolean- 논리연산에 많이 쓰이는 타입으로 true, false 단 두개의 값만 있다   
* 그외...배열,객체 등

**연산자**➕➖✖➗
* 기본연산자(- + * / % ++ --)
* 관계연산자(== === != > < >= <=)
* 논리연산자(&& || !)

## 배열
***
**배열은** -여러개의 데이터를 하나의 변수에 담고 싶을때 사용한다   

**인덱스** -배열에 들어가있는 아이템에는 모두 인덱스 번호가 부여된다.   
시작점은 0부터 부여가 된다   
인덱스 번호로 배열에 있는 아이템들을 접근할 수 있다


```js
let array = ["apple","banana","mango"] // 인덱스번호 0,1,2
console.log(array[0]) // apple 프린트
array[1]="grape"
console.log(array)// ["apple","grape","mango"] 가 나옴
```

* pop(): 배열끝에 있는 아이템을 제거, 그 아이템값을 리턴
* push('아이템'): 배열끝에 아이템 추가,배열의 최종 길이 리턴
* includes('아이템'): 배열에 아이템이 포함되어 있으면 true리턴 아니면 false리턴
* indexOf('아이템'): 아이템의 인덱스 번호를 리턴
* slice(시작점,끝점):    
1)시작점으로 부터 몇개의 아이템을 제거하고 싶은지   
 2)시작점~끝점(미포함)까지 배열을 복사해서 리턴   
  3)기존의 배열을 건들이지 않음
* splice(시작점,개수):   
1)시작점부터 개수만큼 실제 배열에서 아이템 제거   
3)기존의 배열이 잘림
* length: 배열 함수는 아니지만 배열의 크기를 리턴해주는 속성

```js
let fruit=["banana","apple","grape","mango"]
console.log(fruit[3])//인덱스3번째(mango)리턴
fruit[2]= "tomato"
console.log(fruit)//인덱스2번째자리에 tomato변경

console.log(fruit.includes("apple"))//true
// console.log(fruit.indexOf("apple"))//1

console.log(fruit.slice(2))//grape,mango
console.log(fruit.slice(1,3))//apple,grape

fruit.splice(2,1)
console.log(fruit)//banana,apple,mango
```
```js
let array = ["apple","banana","mango"]
console.log(array.length) // 3이 나옴, 배열에 아이템이 총 3개라서
```

## 객체
***
관련있는 정보를 묶어서 하나의 데이터를 표현하기 위해 나옴

>arry는 [] ->사용   
 객체는 {} ->사용

예시1)
```js
let patient ={
  name:"jimin",
  age:17,
  disease:"cold"
}
console.log(patient)
console.log(patient.age)//변수이름.키값
console.log(patient["age"])//위랑 같은말
patient.name ="jk"
patient["age"]="25"
console.log(patient)
```
예시2)
```js
let patientlist =[{name:"jimin",age:13},{name:"jk",age:25},{name:"jhope",age:40}]

console.log(patientlist)
console.log("첫번째 환자는:",patientlist[0])
console.log("첫번째 환자의 나이는?",patientlist[0].age)
console.log("두번째 환자의 이름은?",patientlist[1].name)
```

## IF문
* 범위를 작은 것 부터 큰거 순으로 두는 것이 좋음
* If 문의 생김새
if(조건){   
    조건이 true일 경우 들어옴   
}else if(또 다른 조건){   
    조건이 true일 경우 들어옴   
}else if(또 다른 조건){   
    조건이 true일 경우 들어옴    
}else {   
    모든 조건이 false인 경우 들어옴    
}   
if문에 if 는 필수 else if는 추가 조건으로 조건이 여러개 일때 넣어줄 수 있다.   
 else 도 필수로 들어가진 않으나 모든조건이 충족하지 않을시에 실행하는 코드에 대해서 넣어준다



예시1)
```js
let age =21

if(18<=age || age<20){
  console.log("오토바이 운전만 가능합니다")  
}else if(age>20) {
  console.log("운전이 가능합니다")
}
else{
  console.log("운전 불가능합니다")
}
```

예시2)
```js
let age =21
let licence =true

if(age>20){
  if(licence !=true){
    console.log("운전이 가능 합니다")
  } else {
    console.log("면허를 따세용")
  }
} else{
  console.log("운전 불가능합니다")
}
```

* ==과 ===의 차이   
자바스크립트코드를 보다보면 어떤이는 ==만 쓰고 어떤이는 ===를 쓴걸 볼 수 있다.   
둘의 차이는 자료형까지 일치해야하는가? 이다.   
**a==b 의 경우** 둘의 값만 같으면 장땡   
**a===b의 경우** 둘의 값 + 자료형까지 같아야함 (좀더 엄격한 비교)

```js
let a = 1 
let b ="1"
console.log(a==b) //true
console.log(a===b) //false
```

## switch문과 삼항 연산식
***
**switch**   
* 조금 더 간결하고 의미가 명확해 보인다는 장점이 있음
* case가 값으로 딱 정해진 경우에만 사용가능
* 조건이 비교식일 경우 사용 불가
예시)
```js
let food = '햄버거'
switch(food){
    case '피자':
        console.log("피자를 주세요")
        break;
    case '햄버거':
        console.log("햄버거를 주세요")
        break;
    default:
        console.log("메뉴에 없는 음식입니다")
}
```

**삼항연산자**
* if문을 간단하게 표현할 수 있다.
* 조건에 따라 실행하는 내용이 한가지 일때 쓰기 좋다
* 조건에따라 실행하는 내용이 다르다
* 조건식? 참일때 : 거짓일때


if-else 예시)
```js
let menu =2

if(menu <=3){
  console.log("범위 안에 숫자입니다")
}else{
  console.log("범위 밖의 숫자입니다")
}
//범위 안에 숫자입니다
```
삼항연산자 예시)
```js
let answer = menu <= 3? "범위 안에 숫자입니다":"범위 밖의 숫자입니다"

console.log(answer)
//범위 안에 숫자입니다
```

예시3)   
>레포트 점수에따라 등급을 매기는 프로그램을 만드시오
90~100 : A   
80~89 : B   
70~79 : C   
60~69 : D   
less than 59 : F

```js
//내가 만든것
let score=70
if(score>=90){
  console.log("A")
}else if(80<=score && score<=89){
  console.log("B")
}else if(70<=score && score<=79){
  console.log("C")
}else if(60<=score && score<=69){
  console.log("D")
}else{
  console.log("F")
}
```

```js
//정답
let score =  100
let grade
if(90<=score && score<=100){
  grade = "A"
}else if(80<=score && score<=89){
  grade = "B"
}else if(70<=score && score<=79){
  grade ="C"
}else if(60<=score && score<=69){
  grade="D"
}else if(0<=score && score<=59){
  grade="F"
}else {
  console.log("잘못된 범위의 점수입니다")
}
console.log(grade)
```

### HTML in javascript
***
* **getElementsByClassName( )**은 많은 element를 한번에 가지고 와야하는 경우에 사용(arry 반환)   
* **getElementsByTagName( )**  태그이름을 통해 element를 가져옴(arry 반환)
* **querySelector( )** element를 css방식으로 검색 

### events
***
>* title.onclick = handleMouseEnter;
>* title.addEventListener(“mouseenter” , handleMouseEnter);

위에 두 코드는 동일하나 addEventListener를 선호하는 이유는
removeEventListener을 통해서 event listener을 제거할수있기 때문이다.

onClick="함수( )"
js에서 바로 사용할수있는 eventListener

### css in javascrpit(1)
***
**classList** 우리가 class들의 목록으로 작업할수 있게끔 허용해준다.   

**className**은 이전 calss를 상관하지않고 모든걸 교체해 버린다.   
-> js에서 classList를 사용하는거는 HTML element가 가지고있는 또하나의 요소 사용하는 것이다.   
-> element의 class내용물을 조작하는 것을 허용한다는 뜻

<br/>

**contains**은 우리가 명시한 class가 HTML element의 class에 포함되어 있는지 말해준다

**remove**라는 function은 명시한 class name을 제거하고    

**add**라는 function은 명시한 class name을 추가   

**toggle**은 토큰이 존재하면 토큰제거,토큰존재 하지않으면 토큰 추가

### css in javascrpit(2)
***

* isNaNnumber -구별을 판별

* visibility:hidden - 공간은 그대로 두고 보이지만 않는것   
   display:none - 잡아둔 공간도 사라짐

### local storage
***
* localStorage.setItem( "key" ,"value"  ) //setltem을 활용하면 local storage에 정보를 저장
* localStorage.getItem( "key" ) //getltem을 활용하면 local storage에 저장된 정보를 불러냄
* localStorage.removeItem("key") // removeItem을 활용하면 loacal storage에 저장된 정보를 삭제
* Date.now( ) 밀리초(1000분의 1초)를 주는 함수-->랜덤숫자가 필요할때 사용


### time founction
***
* setInterval(함수,시간) funtion을 정한 시간마다 실행시키는 방법(시간단위는 ms단위)//계속반복   
* setTimeout(함수, 시간) funtion을 정한 시간에 실행//한번만실행

ex)    
**setInterval(sayHello, 1000);** sayHello() 라는 펑션을 1초마다 반복한다는 의미.
단 바로 실행되지 않고 1초 후 첫 시작이 되고 계속 1초마다 반복된다.   
 **setTimeout(sayHello, 1000);** 1초 기다렸다가 한번만 실행.


### date object
***
 //호출하는 당시의 현재 날짜와 시간을 알려줌
setInterval(getClock,1000)
```js
function getClock() {
  const date =new Date()
  clock.innerText=`${date.getHours()}:${date.getMinutes()}:${date.getSeconds()}`;
 }
```
----->Date().toLocaleTimeString( ) //현시각나타내는함수

### padStart, padEnd함수
***
-> string에 쓸수있으며 string을 보다 길게 만들어야 할때 사용    
   padStart(maxlength, fillstring)앞쪽에 문자를 추가   
   padEnd(maxlength, fillstring) 뒤쪽에 문자를 추가

ex) "Hello".padStart(10,"x")  // xxxxxHello

### type change
***
* **string( )**   
숫자를 문자로 바꾸는 방법    
string constructor로 주위 감싸기   
new Date( ),getHours( )  // 19   
String(new Date( ).getHours( )) // "19"

* **parseInt**   
문자을 숫자로 바꾸는 방법

### Math 객체기능
***
   * Math.round( ) 소수점 반올림
   * Math.ceil( ) 숫자를 천장(ceil)까지 높여주는 것. 즉, 소수점이있으면 무조건 올림하여 값이 정수로 나옴
   * Math.floor( ) 숫자를 바닥(floor)까지 낮여주는 것. 즉, 소수점이 있으면 무조건 없애서 값이 정수로 나옴
```js
const todayQuote=quotes[Math.floor(Math.random()*quotes.length)] 
```
### js에서 html 요소를 생성
***
```js
  document.creatElement("")
  ```
   예를 들어, document.creatElement("img")일 경우 html내에 img태그를 생성

### more founction
***
**appendChild( )** //함수 안의 경로에 정의한 값을 가장 뒤에 기입함(객체만 추가)   
**prependChild( )**//반대로 앞에 기입   
**insertBefore( )** //참조된 노드 앞에 특정 부모 노드의 자식 노드를 삽입   

```js
const h2 = document.querySelector("#clock")
const bgImage = document.createElement("img")
document.body.insertBefore(bgImage, h2);

//두개의 인자중에 앞의 bgImage는 새로운 노드  즉 추가하고 싶은 노드이고 h2는 참조할 노드입니다.   
// 즉 이렇게 코드를 짜시면 h2요소 앞에 bgImage가 추가되게 됩니다.
```
```js
const li =document.createElement("li")
const span=document.creatElement("span")
li.appenChild(span)
// li안에 span태그
```

### deleting todo
***
````js
button.addEventListener("click", deleteToDo)

function deleteToDo(event){
    const li=event.target.parentElement;
    li.remove()
 }
````
1)click 시, event로 부터 정보를 받아와서 어떤 버튼을 눌렸는지에 대한 정보를 받는다   
2)event안의 target안의 parentElement를 이용하여 버튼을 눌려진 li에 대한 정보를 받는다   
3)지정된 버튼을 누르면 remove( ) 함수를 이용하여 제거

### localstorage
***
localstorage는 안타깝게도 배열 저장 못함 오직 "텍스트"만 저장가능   
* JSON.STRINGIFY( ) = 변수 등을 문자열로 바꿈, 
* JSON.PARSE( )= 문자열을 JSON으로 바꿈
* .forEach( )는 arry에 있는 각각의 item에 대해서 function을 실행하게 해줌 

//결론은 parse로 배열을 만든다음 forEach를 사용하여 각각의 배열item에 대해 function을 실행시킴   

// local storage에 array로 저장이 안되기 때문에 JSON.stringify로 array처럼 생긴 string으로 저장한 후 다시 JSON.parse 이용해 array로 꺼내는 방법   

array.foreach는 받아온 array를 for 반복문 없이 item 하나씩 function에 넣을 수 있는 신기한 녀석

### arrow function
***
->기본 function
```js
function sayHello( item ){
   console.log("lala",item)
   }

const arryToDos = localstorage.getItem(TODOS_KEY)

if(arryToDos !== null){
    const paredToDos = JASON.parse(arryToDos)
    parsedToDos.forEeach(item)
   }
```

->arrow function
```js
const arryToDos = localstorage.getItem(TODOS_KEY)

if(arryToDos !== null){
    const paredToDos = JASON.parse(arryToDos)
    parsedToDos.forEeach((item) => console.log("lala", item))
   }
```
### fliter
***
"배열"에서 지우고 싶은 것이 있을때 사용(지우고 싶은것을 지우는 것이 아닌 필요없는 것을 배제하고 들고옴으로서 새 배열을 만듬. 즉, filter function은 새 배열을 만듬)    

forEach와 비슷하게 모든 배열을 거친다 다만 반드시 return해야함    

arry의 item을 유지하고 싶으면 true를 리턴해야함
```js
const arr =[1223, 5443, 100, 345, 1200]
function sexyfliter(num){ return num<=1000}
arr.fliter(sexyfliter)  // [100, 345]
```

### navigator function
***
```js
const weather=document.querySelector("#weather span:first-child")
const city =document.querySelector("#weather span:last-child")

const API_KEY="abcf19118a589b2cbbbf87bf809fa89d"

function onGeoOk(position){
    const lat = position.coords.latitude
    const lon = position.coords.longitude
    console.log(lat,lon);
    const url =`https://api.openweathermap.org/data/2.5/weather?lat=${lat}&lon=${lon}=${API_KEY}`
   fetch(url)
  .then(response => response.json( ))
  .then(data => {
   city.innerText =data.name
   weather.innerText =data.weather[0].main})
}

function onGeoError(){ }
navigator.geolocation.getCurrentPosition(onGeoOk,onGeoError)

```

 api 만들기 https://openweathermap.org/       
세 변수는 반드시 필요:api key, lon, lat
fetch로 url부르기(실제로 url에 갈 필요없이 js가 대신 url을 부르는것)

