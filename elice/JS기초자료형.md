## 기초 자료형:JavScript으로의 초대

### 📌 JS소개

HTML - 구조    
CSS - 꾸미기    
JS- 이미지 슬라이스 효과, 팝업 효과 등의 기능을 포함한 동적인 웹사이트 제작    

자바 활용범위 - IoT / 하이브리드앱 / 서버개발

### 📌JS변수

* 변수: 데이터를 담는 공간
* 변수선언: 데이터를 담을 공간을 생성
* 변수초기화: 생성된 변수에 데이터를 전달
    ```js
    var fruit; // 변수선언
    fruit="apple" //변수 초기화 

    var fruit ="apple"; //변수 선언 및 초기화 
    ```
* 데이터변경: 변수는 이미 선언되었으므로 var 다시 작성할 필요가 없다 
    ```js
    var fruit="apple";
    fruit="banana";
    ```

* 변수안의 데이터 확인방법    
console.log(); 는 변수 안에 데이터를 확인할때 사용하는 명령어     
document.write(변수명) 은 변수의 데이터를 웹 화면에 출력할때 사용하는 명령어  
 **document.writeln();** 을 사용하면 출력값 사이에 공백을 넣을 수 있다  

    ```js
    var fruit="apple";
    console.log(fruit); //apple 출력
    document.write(fruit); //변수의 데이터를 웹화면에 출력 
    ```

   

* 변수 생성 시 주의사항
    ```js
    //변수명은 숫자로 시작할 수 없다
    var 1str;
    //변수명은 최대한 자세하게 작성
    var randomNumber
    //의미가 불명확한 단어들의 조합은 피해야함
    var tmax;
    ```
* JS사용방법 및 변수데이터 확인방법   
    script 태그<> 안에 src의 속성값으로 js파일을 입력 후 html파일과 연동    

    우클릭 후 크롬개발자 검사 or F12
    ```js
    <body>
    <script src="index.js"></script>
    </body>
    ```

### 📌JS데이터 타입

데이터타입이란? 초콜릿도 다양한 종류가 존재하듯이 변수에 전달되는 데이터 타입에도 여러 종류가 존재

8가지 데이터 타입
* 문자열(string)
* 숫자(number)
* 함수(function)
* 배열(array)
* 객체(object)
* 불린(boolean)
* 정의되지 않음(undefined)
* 널(null)

#### 💭 문자열
"큰 따옴표" 또는 '작은 따옴표'안에 작성된 데이터   
자바스크립트는 상대적으로 자유도가 높아서, 정수와 실수가 서로 연산이 가능
```js
var str1="He's a boy"; // '때문에 문자로 인식x
var str2='He\'s a boy' // \로 문자열 인식
```
문자열 메서드로는 length, charAt, split 등이 있다
```js
var str1="Hi!Elice";

str1.length; //8
str1.charAt(1) //!
str1.split("!") // [Hi, Elice]
```

#### 💭 숫자
별도의 기호없이 숫자를 입력한 상태
```js
var num1=10; //정수
var num2=-10; //음수
var num3=3.14; //실수
```

#### 💭 함수
함수생성: function키워드를 사용하여 생성    

함수호출: 함수안에 있는 코드를 실행시키겠다는 의미
```js
var func1 =function(){
    console.log("Func1");
} //함수생성

func1(); //함수호출
```
```js
function func1(){
    console.log("Func1");

} //함수생성

func1() //함수호출
```
매개변수:  인자로부터 전달받은 값이 들어가는 통로. 상황에 따라 생략가능 

인자: 함수에 절달하는 데이터   

return: 함수 안에 데이터를 저장할 때 시용

```js
var area=function(width, height){
    return width* height;
}

area(10,20);
```

함수데이터 호출방법
```js
var area=function(width,height){
    return width*height;
}

//새 변수를 생성한 후, 그 변수를 console.log()로 감사기
var result=area(10,20);
console.log(result);

//힘수 자체를 console.log()로 감싸기
console.log(area(10,20));
```

#### 💭  배열
비슷한 성격을 갖고 있는 데이터를 하나의 변수 안에서 관리    
배열데이터 추출: 데이터의 좌표값(index)작성, 첫번째 좌표값은 0

```js
var fruit =["사과"."배","수박"];
console.log(fruit[0]); //데이터확인, 0번째 인덱스의 데이터 추출  
```
배열데이터 변경: 인덱스를 사용하여 접근 후 새로운 데이터 대입
```js
var fruit =["사과"."배","수박"];
fruit[0]="포도"; //["포도", "배", "수박"]

console.log(fruit);
```

#### 💭  객체
프로퍼터, 메서드,데이터로 구성    
여러 종류의 데이터 타입 삽입 가능
```js
var student={
    name:"yeji",
    age:20,
    skills: ["js","html","css"]
    sum: function(num1,num2){return num1+num2;}
}

console.log(student.name); //객체명.프로퍼티명
console.log(student['name']); //객체명["프로퍼티명"]

student.name="Park" // name프로퍼티의 데이터 변경
console.log(student.name) //Park출력 

// 프로퍼티는 이름을 가지고 있는 모든 데이터들
//메서드는 이름을 가지고 있는 함수를 의미
```

#### 💭  undefined, null

undefined: 변수 안에 데이터를 입력하지 않은 상태(데이터가 없는 것)    

null: 개발자가 임의로 변수 안에 빈 데이터를 삽입한 상태(빈 데이터를 지정한 것)
```js
var unde;  //undefined
var empty=null;  //null
```

#### 💭  Boolean
참 또는 것짓 데이터가 들어가 있는 상태
```js
var t =true;
var f = false;
```

### 📌 프로퍼티와 메서드

배열 프로퍼티와 메서드
```js
var fruit=["사과", "배", "포도"];

fruit.length; //데이터 개수

fruit.push("딸기"); //배열 뒤에 데이터 삽입
fruit.unshift("레몬"); //배열 앞에 데이터 삽입

fruit.pop(); //배열 뒤의 데이터 제거
fruit.shift(); //배열 앞의 데이터 제거 

```

math의 수학 연산 메서드
```js
Math.abs(-3); //절대값 3
Math.ceil(0.3) //올림 1
Math.floor(10.9) //내림 10
Math.random(); //임의의 숫자출력
```

문자를 숫자로 변환하는 메서드
```js
parseInt("20.6"); //정수형태의20변환
parseFloat("20.6"); //실수 형태의 20.6변환
```

배열 안의 배열 데이터에 접근하기
```js
var arrTest=[
[100,200,300],
[1000,2000,3000],
[1111,2222,3333]
];

document.write(arrTest[1][2]); //3000출력

//[][]와 같이 연속적으로 대괄호를 써서 인덱싱을 할 수 있다

```