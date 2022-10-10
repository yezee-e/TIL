### 변수의 선언 방식(Variables)

---

**let:** 변수를 선언하고 재할당도 가능 언제든 값을 바꿀 수 있음(재선언금지, 재할당가능)  
**const:** 변수에 한번 값을 할당하면 다시 값을 바꿀 수 없음(재선언금지, 재할당 금지)  
**var:** let의 옛날버전(let과 작동원리는 같으나 호이스팅과 같은 문제가 있음)(재선언가능,재할당가능)

 <br/>

### 자료형과 연산자

---

**자료형**🔍

- string- 문자열 타입이라고도 한다. ""큰따옴표나 ''작은따옴표 안에 들어가 있는 값을 string타입이라고함
- 숫자- 숫자타입, 양수, 음수, 소수, 다 숫자타입
- boolean- 논리연산에 많이 쓰이는 타입으로 true, false 단 두개의 값만 있다
- 그외...배열,객체 등

**연산자**➕➖✖➗

- 기본연산자(- + \* / % ++ --)
- 관계연산자(== === != > < >= <=)
- 논리연산자(&& || !)

**그외**

- undefined - 값이 정의되지 않음(변수는 선언했지만 값을 할당하지는 않음)
  > ex-박스만 만들어 놓은 상태
- null - 값이 없음(변수에 null이 할당된다 즉, 정의되었지만 비어있음)
  > ex-박스 만들고 아무것도 안넣고 포장
- NaN -Not a Number(숫자가 아님)
  <br/>

### 배열(Arrays)

---

**배열은[ ]** -여러개의 데이터를 하나의 변수에 담고 싶을때 사용한다

**인덱스** -배열에 들어가있는 아이템에는 모두 인덱스 번호가 부여된다.  
시작점은 0부터 부여가 된다  
인덱스 번호로 배열에 있는 아이템들을 접근할 수 있다

```js
let array = ['apple', 'banana', 'mango']; // 인덱스번호 0,1,2
console.log(array[0]); // apple 프린트
array[1] = 'grape';
console.log(array); // ["apple","grape","mango"] 가 나옴
```

- pop(): 배열끝에 있는 아이템을 제거, 그 아이템값을 리턴
- push('아이템'): 배열끝에 아이템 추가,배열의 최종 길이 리턴, 즉 꼬리에 요소들을 추가
- unshift(): 배열의 맨 앞부분, 즉 머리 부분에 요소를 추가
- includes('아이템'): 배열에 아이템이 포함되어 있으면 true리턴 아니면 false리턴
- indexOf('아이템'): 아이템의 인덱스 번호를 리턴
- slice(시작점,끝점):  
  1)시작점으로 부터 몇개의 아이템을 제거하고 싶은지  
   2)시작점~끝점(미포함)까지 배열을 복사해서 리턴  
   3)기존의 배열을 건들이지 않음
- splice(시작점,개수):  
  1)시작점부터 개수만큼 실제 배열에서 아이템 제거  
  3)기존의 배열이 잘림
- length: 배열 함수는 아니지만 배열의 크기를 리턴해주는 속성

<br/>

예제)

```js
let fruit = ['banana', 'apple', 'grape', 'mango'];
console.log(fruit[3]); //인덱스3번째(mango)리턴
fruit[2] = 'tomato';
console.log(fruit); //인덱스2번째자리에 tomato변경

console.log(fruit.includes('apple')); //true
console.log(fruit.indexOf('apple')); //1

console.log(fruit.slice(2)); //grape,mango
console.log(fruit.slice(1, 3)); //apple,grape

fruit.splice(2, 1);
console.log(fruit); //banana,apple,mango
```

```js
let array = ['apple', 'banana', 'mango'];
console.log(array.length); // 3이 나옴, 배열에 아이템이 총 3개라서
```

 <br/>

### 객체(Object)

---

관련있는 정보를 묶어서 하나의 데이터를 표현하기 위해 나옴

> arry는 [] ->사용  
>  객체는 {} ->사용

> arry는 ->설명이 필요하지 않은 데이터 리스트  
>  object->설명이 필요한 정보가 담긴 데이터 리스트

- 객체 속성 추가  
  객체를 생성한 후, 속성을 지정하고 값을 입력하면, 객체에 속성을 추가할 수 있다

```js
객체.키 = '값';
객체['키'] = '값';
```

- 객체 속성 제거

```js
delete 객체[속성];
delete 객체['속성'];

delete 객체.속성;
```

- 객체 안의 객체 접근

```js
function accessObject() {
  let myStorage = {
    car: {
      inside: {
        'glove box': 'maps',
        'passenger seat': 'crumbs',
      },
      outside: {
        trunk: 'jack',
      },
    },
  };
  gloveBoxContents = myStorage['car']['inside']['glove box'];
  return gloveBoxContents; //map
}
```

- 객체 안의 배열 접근

```js
function accessArray() {
  let myplants = [
    {
      type: 'flowers',
      list: ['rose', 'tulip', 'dandelion'],
    },
    {
      type: 'trees',
      list: ['fir', 'pine', 'birch'],
    },
  ];
  foundValue = myPlants[1]['list'][1];
  return foundValue; //pine
}
```

객체의 다른예시-
예시1)

```js
let patient = {
  name: 'jimin',
  age: 17,
  disease: 'cold',
};
console.log(patient);
console.log(patient.age); //변수이름.키값
console.log(patient['age']); //위랑 같은말
patient.name = 'jk';
patient['age'] = '25';
console.log(patient);
```

예시2)

```js
let patientlist = [
  { name: 'jimin', age: 13 },
  { name: 'jk', age: 25 },
  { name: 'jhope', age: 40 },
];

console.log(patientlist);
console.log('첫번째 환자는:', patientlist[0]);
console.log('첫번째 환자의 나이는?', patientlist[0].age);
console.log('두번째 환자의 이름은?', patientlist[1].name);
```

 <br/>

### 함수(Function)

---

function 선언

```js
function 함수명() {
  실행코드;
}
```

funtion 실행 : 함수명();

argument(인수)를 보내야 하는데 인수란 함수를 실행하는 동안 어떤 정보를 함수에게 보낼 수 있는 방법이다.

<br/>

1)function은 괄호 안의 매개변수에서 argument를 받아들일 수 있다

```js
function sayHello(nameOfPerson) {
console.log("my name is"+nameOfPerson);
}

sayHello("nico") //my name is nico
sayHello("dal") //my name is dal
sayHello("lynn")] //my name is lynn

 // nameOfPerson은 "nico" "dal" "lynn" 을 인수로 받음
```

2)object 안에서 매개변수가 argument를 받는 방식

```js
const player = {
  name: function (Name) {
    console.log('Your Name is ' + Name + ' 입니다.');
  },
  sayHello: function (Age) {
    console.log('Your age is ' + Age + ' 입니다.');
  },
};

player.name('james'); //Your Name is james 입니다.
player.sayHello(14); //Your age is 14 입니다.
```

```js
function add(a, b) {
  console.log(a + b);
}

add(3, 4); //함수부르기

const coculator = {
  add: function (a, b) {
    console.log(a + b);
  },
};

coculator.add(2, 3); //객체에서 함수 부르기
```

- returns

```js
const age = 96;
function calculateKrAge(ageOfForeigner) {
  return ageOfForeigner + 2;
}

const KrAge = calculateKrAge(age);

console.log(KrAge); //98
```

### 조건문(conditionals)

---

#### 📌IF문

- 범위를 작은 것 부터 큰거 순으로 두는 것이 좋음
- If 문의 생김새
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
let age = 21;

if (18 <= age || age < 20) {
  console.log('오토바이 운전만 가능합니다');
} else if (age > 20) {
  console.log('운전이 가능합니다');
} else {
  console.log('운전 불가능합니다');
}
```

예시2)

```js
let age = 21;
let licence = true;

if (age > 20) {
  if (licence != true) {
    console.log('운전이 가능 합니다');
  } else {
    console.log('면허를 따세용');
  }
} else {
  console.log('운전 불가능합니다');
}
```

- ==과 ===의 차이  
  자바스크립트코드를 보다보면 어떤이는 ==만 쓰고 어떤이는 ===를 쓴걸 볼 수 있다.  
  둘의 차이는 자료형까지 일치해야하는가? 이다.  
  **a==b 의 경우** 둘의 값만 같으면 장땡  
  **a===b의 경우** 둘의 값 + 자료형까지 같아야함 (좀더 엄격한 비교)

```js
let a = 1;
let b = '1';
console.log(a == b); //true
console.log(a === b); //false
```

 <br/>

#### 📌switch문과 삼항 연산식

**switch**

- 조금 더 간결하고 의미가 명확해 보인다는 장점이 있음
- case가 값으로 딱 정해진 경우에만 사용가능
- 조건이 비교식일 경우 사용 불가  
  예시)

```js
let food = '햄버거';
switch (food) {
  case '피자':
    console.log('피자를 주세요');
    break;
  case '햄버거':
    console.log('햄버거를 주세요');
    break;
  default:
    console.log('메뉴에 없는 음식입니다');
}
```

 <br/>

**삼항연산자**

- if문을 간단하게 표현할 수 있다.
- 조건에 따라 실행하는 내용이 한가지 일때 쓰기 좋다
- 조건에따라 실행하는 내용이 다르다
- 조건식? 참일때 : 거짓일때

if-else 예시)

```js
let menu = 2;

if (menu <= 3) {
  console.log('범위 안에 숫자입니다');
} else {
  console.log('범위 밖의 숫자입니다');
}
//범위 안에 숫자입니다
```

삼항연산자 예시)

```js
let answer = menu <= 3 ? '범위 안에 숫자입니다' : '범위 밖의 숫자입니다';

console.log(answer);
//범위 안에 숫자입니다
```

예시3)

> 레포트 점수에따라 등급을 매기는 프로그램을 만드시오  
> 90 ~ 100 : A  
> 80 ~ 89 : B  
> 70 ~ 79 : C  
> 60 ~ 69 : D  
> less than 59 : F

```js
//내가 만든것
let score = 70;
if (score >= 90) {
  console.log('A');
} else if (80 <= score && score <= 89) {
  console.log('B');
} else if (70 <= score && score <= 79) {
  console.log('C');
} else if (60 <= score && score <= 69) {
  console.log('D');
} else {
  console.log('F');
}
```

```js
//정답
let score = 100;
let grade;
if (90 <= score && score <= 100) {
  grade = 'A';
} else if (80 <= score && score <= 89) {
  grade = 'B';
} else if (70 <= score && score <= 79) {
  grade = 'C';
} else if (60 <= score && score <= 69) {
  grade = 'D';
} else if (0 <= score && score <= 59) {
  grade = 'F';
} else {
  console.log('잘못된 범위의 점수입니다');
}
console.log(grade);
```

 <br/>

### HTML in javascript

---

**document** 는 HTML과 상호작용을 가능하게 해주는 객체로 js에서 html파일을 불러올 수 있도록 도와준다

아래는 document의 함수들이다

- **document.getElementById( )** html에 있는 id를 불러올 수 있다.

- **document.getElementsByClassName( )** 은 많은 element를 한번에 가지고 와야하는 경우에 사용(arry 반환)
- **document.getElementsByTagName( )** 태그이름을 통해 element를 가져옴(arry 반환)
- **document.querySelector( )** element를 css방식으로 검색(조건에 부합하는 첫번째 것만 반환)
- **document.querySelectorAll( )** element를 css방식으로 검색 (조건에 맞는 모두 반환)
- **document.creatElement("")** javascript에서 html element를 생성(js에서 element를 만들어서 html에 전달)

  예를 들어, document.creatElement("img")일 경우 html내에 img태그를 생성

  ```js
  const images =["0.jep","1.jpeg","2.jpeg"]; // 사진배열
  const chosenImage = images[Math.floor{Math.random()*image.length}] //램덤이미지
  const bgImage =document.createElement("img") //js에 element생성
  bgImage.src =`img/${chosenImage}` //
  document.body.appendChild(bgImage) //body에 html을 추가
  ```

 <br/>

### innerHTML과 textContent차이

---

- **innerHTML** - element의 HTML,XML을 읽어오거나 설정할 수 있다. 태그 안에 있는 HTML전체 내용을 들고옴
- **textContent** - 해상 노드나 가지고 있는 텍스트 값을 그대로 가져옴
- **innerText** - textcontent랑 비슷하지만 textcontent는 모든 요소를 반환하는 반면
  innerText는 사람이 읽을 수 있는 요소만 가져옴(예시로 스페이스바를 한칸만 남기고 가져온다)

```js
<div id='test'>
  <span>Hello world</span>
</div>; //html에 이런 태그가 있다고 가정할때

console.log(document.getElementById('test').innerHTML); //<span>Hello     world</span>
console.log(document.getElementById('test').textContent); //Hello      world
console.log(document.getElementById('test').innerText); //Hello world
```

### Html in javascript

---

- **event**
  > - title.onclick = handleMouseEnter;
  > - title.addEventListener(“mouseenter” , handleMouseEnter);

위에 두 코드는 동일하나 addEventListener를 선호하는 이유는
removeEventListener을 통해서 event listener을 제거할수있기 때문이다.

onClick="함수( )"
js에서 바로 사용할수있는 eventListener

- preventDefault()함수를 추가함으로서 브라우저의 기본동작을 막을 수 있다

```js
function onLoginSubmit(event) {
  event.preventDefault();
  // 브라우저가 기본 동작을 실행하지 못하게 막기
  // event object는 preventDefault함수를 기본적으로 갖고 있음
  console.log(event);
}
```

- **요소의 속성 다루는 메서드**

  > - .getAttribute("") 요소의 속성 값을 반환하는 방법

  > - .removeAttribute("") 요소의 속성 값을 제거하는 방법

  > - .setAttribute("") 요소에 속성을 추가하는 방법

### css in javascrpit

---

- **classList** 우리가 class들의 목록으로 작업할수 있게끔 허용해준다.
- **className**은 이전 calss를 상관하지않고 모든걸 교체해 버린다.

-> js에서 classList를 사용하는거는 HTML element가 가지고있는 또하나의 요소 사용하는 것이다.  
-> element의 class내용물을 조작하는 것을 허용한다는 뜻

<br/>

**contains**은 우리가 명시한 class가 HTML element의 class에 포함되어 있는지 말해준다  
**remove**라는 function은 명시한 class name을 제거  
**add**라는 function은 명시한 class name을 추가  
**toggle**은 토큰이 존재하면 토큰제거,토큰존재 하지않으면 토큰 추가

### offset(slice bar)

---

```js
let tabs = document.querySelectorAll('.task-tabs div'); //각 목록 전부 들고오기
let underLine = document.getElementById('under-line'); //밑줄

tabs.forEach((menu) => menu.addEventListener('click', (e) => tabsIndicator(e))); //forEach로 clickevent주기

function tabsIndicator(e) {
  underLine.style.left = e.currentTarget.offsetLeft + 'px';
  underLine.style.width = e.currentTarget.offsetWidth + 'px';
  underLine.style.top =
    e.currentTarget.offsetTop + e.currentTarget.offsetHeight + 'px';
}
```

### local storage

---

- localStorage.setItem( "key" ,"value" ) //setltem을 활용하면 local storage에 정보를 저장
- localStorage.getItem( "key" ) //getltem을 활용하면 local storage에 저장된 정보를 불러냄
- localStorage.removeItem("key") // removeItem을 활용하면 loacal storage에 저장된 정보를 삭제
- Date.now( ) 밀리초(1000분의 1초)를 주는 함수-->랜덤숫자가 필요할때 사용

<br/>

localstorage는 안타깝게도 배열 저장 못함 오직 "텍스트"만 저장가능

- JSON.STRINGIFY( ) = 변수 등을 문자열로 바꿈,
- JSON.PARSE( )= 문자열을 Arrau(배열)으로 바꿈

//결론은 parse로 배열을 만든다음 forEach를 사용하여 각각의 배열item에 대해 function을 실행시킴

// local storage에 array로 저장이 안되기 때문에 JSON.stringify로 array처럼 생긴 string으로 저장한 후 다시 JSON.parse 이용해 array로 꺼내는 방법  
 <br/>

### functions

---

#### 📌isNaN():NaN인지 판별하는 방법, boolean으로 알려준다

#### 📌time founction

- setInterval(함수,시간) funtion을 정한 시간마다 실행시키는 방법(시간단위는 ms단위)//계속반복
- setTimeout(함수, 시간) funtion을 정한 시간에 실행//한번만실행

ex)  
**setInterval(sayHello, 1000);** sayHello() 라는 펑션을 1초마다 반복한다는 의미.
단 바로 실행되지 않고 1초 후 첫 시작이 되고 계속 1초마다 반복된다.  
 **setTimeout(sayHello, 1000);** 1초 기다렸다가 한번만 실행.

//호출하는 당시의 현재 날짜와 시간을 알려줌
setInterval(getClock,1000)

```js
function getClock() {
  const date = new Date();
  clock.innerText = `${date.getHours()}:${date.getMinutes()}:${date.getSeconds()}`;
}
```

- Date.now() 밀리초(1000분의1초)를 주는 함수-> 이 함수를 사용하여 램덤숫자 만듬

----->Date().toLocaleTimeString( ) //현시각나타내는함수

 <br/>

#### 📌padStart, padEnd함수

-> string에 쓸수있으며 string을 보다 길게 만들어야 할때 사용  
 padStart(maxlength, fillstring)앞쪽에 문자를 추가  
 padEnd(maxlength, fillstring) 뒤쪽에 문자를 추가

ex) "Hello".padStart(10,"x") // xxxxxHello

 <br/>

#### 📌type change

- **string( )**  
  숫자를 문자로 바꾸는 방법  
  string constructor로 주위 감싸기  
  new Date( ),getHours( ) // 19  
  String(new Date( ).getHours( )) // "19"

- **parseInt**  
  문자열을 숫자로 바꾸는 방법

 <br/>

#### 📌Math 객체기능

- math.random() 램덤한 숫자 생성
- Math.round( ) 소수점 반올림
- Math.ceil( ) 숫자를 천장(ceil)까지 높여주는 것. 즉, 소수점이있으면 무조건 올림하여 값이 정수로 나옴
- Math.floor( ) 숫자를 바닥(floor)까지 낮여주는 것. 즉, 소수점이 있으면 무조건 없애서 값이 정수로 나옴

```js
const todayQuote = quotes[Math.floor(Math.random() * quotes.length)];
```

 <br/>

📌  
**appendChild( )** //함수 안의 경로에 정의한 값을 가장 뒤에 기입함(객체만 추가)  
**prependChild( )**//반대로 앞에 기입  
**insertBefore( )** //참조된 노드 앞에 특정 부모 노드의 자식 노드를 삽입

```js
const h2 = document.querySelector('#clock');
const bgImage = document.createElement('img');
document.body.insertBefore(bgImage, h2);

//두개의 인자중에 앞의 bgImage는 새로운 노드  즉 추가하고 싶은 노드이고 h2는 참조할 노드입니다.
// 즉 이렇게 코드를 짜시면 h2요소 앞에 bgImage가 추가되게 됩니다.
```

```js
const li = document.createElement('li');
const span = document.creatElement('span');
li.appenChild(span);
// li안에 span태그
```

#### 📌대소문자변환

- toLowerCase() - 소문자로 변환
- toUpperCase() - 대문자로 변환

### addEventLister의 정보받기

---

클릭한 버튼 좌표 찾기 ->event.target

```js
button.addEventListener('click', deleteToDo);

function deleteToDo(event) {
  const li = event.target.parentElement;
  li.remove();
}
```

1)click 시, event로 부터 정보를 받아와서 어떤 버튼을 눌렸는지에 대한 정보를 받는다  
2)event안의 target안의 parentElement를 이용하여 버튼을 눌려진 li에 대한 정보를 받는다  
3)지정된 버튼을 누르면 remove( ) 함수를 이용하여 제거

 <br/>

### arrow function

---

->기본 function

```js
function sayHello(item) {
  console.log('lala', item);
}

const arryToDos = localstorage.getItem(TODOS_KEY);

if (arryToDos !== null) {
  const paredToDos = JASON.parse(arryToDos);
  parsedToDos.forEeach(item);
}
```

->arrow function

```js
const arryToDos = localstorage.getItem(TODOS_KEY);

if (arryToDos !== null) {
  const paredToDos = JASON.parse(arryToDos);
  parsedToDos.forEeach((item) => console.log('lala', item));
}
```

 <br/>

### Class

---

객체지향 프로그래밍의 핵심 개념입니다.
비슷한 object를 많이 만들일 있으면 class를 만든다=class는 object뽑는 기계

- 클래스 내에 정의된 함수를 `메서드`라고 부른다
- 클래스를 통해 생성된 객체를 `인스턴스` 라고 부른다

```js
class Car {
  constructor(name, price) {
    this.name = name;
    this.price = price;
    this.department = '선릉지점';
  }

  applyDiscount(discount) {
    return this.price * discount;
  }
}

const ray = new Car('Ray', 2000);
const genesis = new Car('Genesis', 8000);
const sonata = new Car('Sonata', 3000);
//인스턴스는 Class 이름에 new를 붙여서 생성합니다
```

> 클래스의 이름은 대문자로 시작

> `constructor`은 생성자로 class에 필요한 기초 정보를 세팅하는 곳

> `this` 는 본인 객체를 의미합니다. 클래스 내에서 메서드끼리 소통하기 위해서는 this가 필요  
> 멤버변수는 클래스 내에서 name, price와 같이 변경 가능한 상태값이자 클래스 내에서 어느 곳에서나 사용할 수 있는 변수  
> 멤버변수는 this키워드로 접근한다

 <br/>

### 배열함수

---

**배열함수 리스트**

- forEach: 반환값이 없다, 단순 for문과 같이 작동
- map: 반환값을 배열에 담아 반환
- filter: 조건에 충족하는(true)아이템만 배열에 담아 반환
- some: 조건에 충족하는 아이템이 하나라도 있으면 true반환, 아니면 flase
- every: 모든 배열에 아이템이 조건을 충족하면 true반환, 아니면 false
- find: 조건에 충족하는 아이템 "하나만" 반환(여러개라면 첫번째 것만 반환)
- findIndex: 조건에 충족하는 아이템의 인덱스값 반환(여러개라면 첫번째 아이템의 인덱스번호만 반환)

#### 📌 forEach()

array.forEach는 arry에 있는 각각의 item에 대해서 function을 실행하게 해줌

```js
let names = ['yeji', 'rak', 'moon'];

for (let i = 0; i < names.length; i++) {
  console.log(names[i]);
}
//for문
//결과값: yeji rak moon

function printName(item) {
  console.log(item);
}

names.forEach(printName); //forEach문

names.forEach(function (item) {
  console.log(item);
}); //forEach문

names.forEach((item, index) => {
  console.log(item, index);
}); //forEach와 arrow함수
```

```js
const arr = [1, 2, 3];
const squares = [];

arr.forEach((num) => {
  squares.push(num * num);
});
//map과의 큰 차이는 새로운 배열을 return(반환)하지 않는다는 점
```

 <br/>

#### 📌 map()

return이 필요한 함수  
 배열로 결과값 출력  
 배열에서 특정 데이터만 배열로 받고싶을때 많이 사용

```js
let names = ['yeji', 'rak', 'moon'];

let data = names.map((item) => {
  return itme;
});
console.log(data); //결과값: ["yeji","rak","moon"]
```

```js
const arr = [1, 2, 3];
const squares = arr.map((num) => num * num);
console.log(squares); //[ 1, 4, 9 ]
//map 메서드는 배열을 반복해주는데  새로운 배열로 return(반환) 합니다.
```

#### 📌 fliter

"배열"에서 지우고 싶은 것이 있을때 사용(지우고 싶은것을 지우는 것이 아닌 필요없는 것을 배제하고 들고옴으로서 새 배열을 만듬. 즉, filter function은 새 배열을 만듬)

forEach와 비슷하게 모든 배열을 거친다 다만 반드시 return해야함

arry의 item을 유지하고 싶으면 true를 리턴해야함

```js
const arr = [1223, 5443, 100, 345, 1200];
function sexyfliter(num) {
  return num <= 1000;
}
arr.fliter(sexyfliter); // [100, 345]
```

arrow function을 사용하여 filter function쓰기

```js
const arr = [1, 2, 3, 4];
arr.filter((item) => item > 2) / [3, 4];
```

<br/>

### navigator function

---

```js
const weather = document.querySelector('#weather span:first-child');
const city = document.querySelector('#weather span:last-child');

const API_KEY = 'abcf19118a589b2cbbbf87bf809fa89d';

function onGeoOk(position) {
  const lat = position.coords.latitude;
  const lon = position.coords.longitude;
  const url = `https://api.openweathermap.org/data/2.5/weather?lat=${lat}&lon=${lon}=${API_KEY}`; //세 변수는 반드시 필요:api key, lon, lat
  fetch(url)
    .then((response) => response.json())
    .then((data) => {
      city.innerText = data.name;
      weather.innerText = data.weather[0].main;
    });
}

function onGeoError() {
  alert("can't find you. No weather for you.");
}

navigator.geolocation.getCurrentPosition(onGeoOk, onGeoError);
```

Weather api 만들기 https://openweathermap.org/  
세 변수는 반드시 필요:api key, lon, lat
fetch(url) : 실제로 url에 갈 필요없이 js가 대신 url을 호출
.then(response => response.json())
.then((data)=> {}) //정보 불러오기

### ES6 문법

---

📌객체초기화

```js
let name = 'noona';
let age = 17;
let cute = true;

let person = { name, age, cute };
// let person = {name:name,age:age,cute:cute}와 같다
```

📌Destructuing

```js
let person = {
  name: 'noona',
  age: 17,
  cute: true,
};
let { name, age, cute } = person;
/* let name = person.name   let age = person.age   let cute = person.cute   와 같다 */

let array = [1, 2, 3];
let [a, b, c] = array;
/* let a = array[0]   let b = array[1]   let c = array[2]   와 같다 */
```

📌Rest destructuring

```js
let person = {
    name:"noona",
    age:17,
    cute:true
}
let {name, ...rest} = person
console.log(rest) // {age:17, cute:true}

let array = [1,2,3]
let [a,...rest] = array console.log(rest)//[2,3]
```

📌Spread

```js
let a = [1, 2];
let b = [3, 4];
let c = [5, 6];

let result = [...a, ...b, ...c]; // [1,2,3,4,5,6]
```

📌Template Literal

```js
let name = 'noona';
console.log(`제 이름은 ${name}입니다`);
```

📌arrow function  
화살표 함수 표현식은 기존의 function 표현방식보다 간결하게 함수를 표현할 수 있다.
return 생락가능하다
자신의 this, arguments, super을 바인딩하지 않는다(즉, this함수 사용불가능)

```js
function foo() {
  console.log('hello');
} //이전의 함수 선언 방식

let foo = () => {
  console.log('hello');
};
//새로운 함수 선언 방식
```

```js
let age = 17;
let person = {
  name: 'yeji',
  age: 20,
  getInfo: function () {
    console.log(this);
  },
};

person.getInfo();
//{name:"yeji",age:20,getInfo:[function]}
//this 함수를 사용하면 전역변수가 아닌 지역변수사용가능(나 자신을 불러주는 객체)
```

```js
function sumNumber() {
  const sum = function (a, b) {
    return a + b;
  };
  return sum(40, 10);
}

console.log(sumNumber());

function sumNumber() {
  const sum = (a, b) => a + b;
  return sum(40, 10);
}

console.log(sumNumber());
```

📌for-in
객체를 순회하는 새로운 방법  
반복문인 for문과 같은 종류의 문법이지만, 객체와 배열을 위해 특별히 존재하는, ES6에서 추가된 문법  
또한 객체 순회 뿐만 아니라 일반적인 배열을 순회할때도 사용할 수 있다

```js
//배열 순회하기
const arr = ['coconut', 'banana', 'strawberry', 'apple'];
for (let i in arr) {
  // console.log(i) //0 1 2 3
  console.log(arr[i]) // coconut banana strawberry apple
  //i를 0으로 초기화하고, 배열의 길이와 비교하고, i를 1씩 증가시키는 등의 코드를 생략할수 있게 만든 ES6 문법
```

```js
// 객체 순회하기
const obj = {
  name: 'melon',
  weight: 4350,
  price: 16500,
  isFresh: true,
};
for (let key in obj) {
  const value = obj[key];

  console.log('키: ', key); // name weight price isFresh
  console.log('값: ', value); // 'melon' 4350 16500 true
}
```

### api(application programming interface)

---

컴퓨터나 컴퓨터 프로그램 사이의 연결  
즉, 서버(백엔드)와 클라이언트(프론트엔드)사이의 대화

API는 상호 약속한 룰을 가지고 정보를 주고받는것이기 때문에 각각 API별로 룰이 다르다.

> - API endpoint 별 주는 데이터
> - API 인증 방법 (api key로 인증을 하
>   나?
>   아니면 토큰으로 인증을하나?)
> - Query로 쓸 수 있는 인자들
> - API 응답내용들 (어떤 결과를 내가 받아볼 수 있는지)

**Postman**-> api를 호출하는 툴

**HTTP Request**

> HTML처럼 Header과 Body로 나뉘어져 있다. Header에는 이 문서의 타입 또는 인증을위한 api key나 토큰값 등을 넣을 수 있다.
> Body에는 실제 내용이 들어간다.

**http request method**

> API를 호출하는 명령어에는 크게 4가지 종류가 있다.

- GET : 데이터를 얻어온다 (기본값)
- PUT: 데이터를 수정한다
- POST: 데이터를 생성한다
- DELETE: 데이터를 삭제한다

### JS 동작원리

---

<img src="https://i.imgur.com/iyNcZEM.png">

### JS구성요소

---

- **Stack** - js가 실행이 되면 스택 프레임이 쌓이는 장소로 스택에 새로운 프레임이 들어오고 실행이 완료되면 나간다
  first in last out구조의 자료형
- **메모리 heap** - 동적으로 생성된 변수들은 메모리 heap에 가서 저장
- **테스크 큐(queue)**- 웹api로 부터 받은 테스크를 큐에 저장
- **event loop** - 스택과 큐 사이에서 흐름을 제어  
  이벤트루프는 스택이 비어있는지 확인을 하고 비어있으면 큐에 있는 아이템을 꺼내다 스택에 올림
- **웹 api** - Ajax요청,setTimeout(),event Handler와 같이 웹 브라우저에서 제공하는 기능들을 말한다.  
  이들은 js의 stack에서 작업이 이루어지는 것이 아닌 별도의 thread에서 이루어진다
  > - setTimeOut(함수,시간): 시간만큼 코드를 딜레이시키고 함수를 실행한다. 시간은 참고로 마이크로세컨드 단위이기 때문에 1초는 1000ms이다
  > - Ajax, Axios, fetch: 클라이언트와 서버간에 데이터를 주고받는 기술
  > - Event Handler : 클릭과같은 이벤트를 핸들하는 함수들
- **Thread(쓰레드)** - 실제로 작업을 실행하는 주체로 1개이거나 여러개일 수 있다.
  JS는 싱글쓰레드로 하나의 일 밖에 처리를 못해서 동기적으로 일을 처리한다.  
   만약 멀티쓰레드(1개이상)라면 여러개의 작업을 병렬적으로 처리할 수 있다

  ### API부르기

  ***

  ajax,axios,fetch가 있다

- promise-> 비동기 동작을 다루는 하나의 패턴
- async/await -> 동기적인 js를 비동기적으로 처리하기 위해 사용  
   fetch는 promise를 리턴  
   await은 promise가 resolve또는 reject를 호출할때 까지 기다려준다.  
  await이 없으면 그냥 날것 그대로의 promise가 리턴  
  await을 쓰려면 함수를 async로 선언  
  그것외에도 async로 함수를 선언하면 그함수는 자동으로 promise를 반환

- json ->서버 클라이언트 통신에서 많이 쓰이는 데이터 타입 (png, jpg이런것과 같이 어떤 그냥 데이터 타입)  
   객체랑 똑같이생긴 텍스트라고 이해하기  
   간단한 텍스트인데 객체랑 똑같애서 나중에 읽어오기도 편함. 그래서 json타입을 서버통신시 많이 사용  
  fetch를 쓸때 항상 이 패턴

```js
let response = await fetch(url);
let daa = await response.json();
```

✔가장 많이 사용하는 api호출코드

```js
const callAPI = async () => {
  let url = new URL(`url주소`);
  let header = new Headers({ 헤더내용 }); // 이건 필요한 경우만
  let response = await fetch(url, { headers: header });
  let data = await response.json(); //response에서 결과물을 뽑아내는 작업
};
```

api부르는 방법들

```js
//fatch then사용방법
fetch(`https://yts.mx/api/v2/list_movies.json?minimum_rating=8.8&sort_by=year`)
  .then((res) => {
    res.json();
  })
  .then((json) => {
    setMovies(json.data.movies);
    setLoading(false);
  });
//async/awiat사용방법(1)
const getMovies = async () => {
  const response = await fetch(
    `https://yts.mx/api/v2/list_movies.json?minimum_rating=8.8&sort_by=year`
  ); //api가져오기
  const json = await response.json(); //response에서 결과물을 뽑아내는 과정
  setMovies(json.data.movies);
  setLoading(false);
};
//async/awiat사용방법(2)
const getMovies = async () => {
  const json = await (
    await fetch(
      `https://yts.mx/api/v2/list_movies.json?minimum_rating=8.8&sort_by=year`
    )
  ).json(); //api가져오기와 response에서 결과물 뽑는 과정을 동시에 진행
  setMovies(json.data.movies);
  setLoading(false);
};
```

### 에러 핸들링

---

```js
try {
  //소스코드를 쓴다
  //이안에서 에러가 발생하면
} catch (error) {
  //catch가 에러를 잡아준다
}
```

> - catch는 error을 매개변수로 받는다
> - throw는 에러를 강제로 발생시키는것  
>    ex-응답에 따라 throw를 이용해 내가 보여주고싶은 메세지와 함께 에러를 catch문으로 던질 수 있다.
>   throw new Error("페이지를 찾을 수 없습니다") 와 같은 메세지 등  
>    그 외에 내가 에러를 발생시키고 싶은 상황이 있다면 (검색어가 잘못되서 받은데이터가 아무것도 없다던가) throw를 통해 강제로 에러를 발생시킬 수 있다.
>   <br/>

- API응답에서 에러가 났는지 확인하는 방법
  response.status를 통해 아는법 : 주로 디테일하게 어떤 종류의 에러인지 에러 코드를 보내준다 (401,402 등등)
  response.ok : ok가 true이면 정상적인것, false 이면 비정상적인 것이다. 하지만 자세한 에러 코드는 status로 확인해야된다

### pagenation

---

- 현재 페이지를 가지고 몇번째 페이지 그룹인지 확인 -> math.ceil(page/보이는페이지갯수)
- 첫번째 페이지 -> 마지막-4
- 마지막 페이지 -> 그룹숫자\*5
  <br/>

\*URL에 쿼리 더하기 ->new URL()을 써서 선언한 url은 URL 객체에서 제공하는 다양한 함수들을 쓸 수 있다.
그 중 하나가 .URLSearchParams() 이다. query에 있는 파리미터들을 추가하거나, 삭제하거나, 값을 가져오는 등 다양한 작업이 가능하다
