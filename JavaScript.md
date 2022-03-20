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

<img src="ZBYTs8Y.png">

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