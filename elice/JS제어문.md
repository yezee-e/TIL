## 제어문:논리 흐름을 내맘대로

### 📌 연산자
산술연산자: 숫자뿐 아니라 문자열도 산술 연산자 사용 가능
```js
console.log(20+10); //30
console.log(20-10); //10
console.log(20*10); //200
console.log(20/10); //2
console.log(20%10); //0
```
```js
console.log("20"+"10"); //2010
console.log("20"-"10"); //10
console.log("20"*"10"); //200
console.log("20"/"10"); //2
console.log("20"%"10"); //0
```

증감연산자: ++ 1씩 증가, --1씩 감소
```js
var num =10;

console.log(++num); //num+1 후 num 출력, 11
console.log(--num); //num-1 후 num 출력, 10

console.log(num++); //num 출력 후 num+1, 10
console.log(num--); //num 출력 후 num-1, 11

//연산자가 뒤에 붙으면 다음 출력에 영향을 미침

```

비교 연산자
```js
console.log(20==10); //값이 같다
console.log(20===10); //데이터 타입과 값이 같다
console.log(20!==10); //값이 같지 않다

console.log(20>10); 
console.log(20>=10); 
console.log(20<10); 
console.log(20<=10); 
```

== 와 === 의 차이    
boolean 데이터 타입인 true 혹은 false 반환
```js
console.log(10 =="10"); //true
console.log(10 === "10"); //false
```

논리 연산자
```js
//앞 뒤 조건 모두 참인 경우에만 true 반환하는 AND연산자
console.log(10 === 10 && 20 === 30); //false

// 둘 중 하나만 참이여도 true 반환하는 OR 연산자
console.log(10 === 10 || 20 === 30); //true 
```


### 📌 조건문    
주어진 조건에 따라 결과값을 출력하는 구문    
조건으로는 비교연산자 또는 논리연산자 사용    

#### 💭 조건문-if문    
if(조건){수행할 명령}   
만약 a<b가 참이라면 중괄호 안에 코드를 실행
```js
var a=20;
var b=40;

if (a<b){
    console.log("a는 b보다 작다");
}
```
#### 💭 조건문-if~else문
조건이 true면 if문 false면 else문 실행    
```js
var a =20;
var b =40;

if(a>b){
    console.log("a는 b보다 크다.")
}else {
    console.log("a는 b보다 작거나 같다.")
}
```

#### 💭 조건문-else if문
여러개의 조건문을 생성할 때 사용
```js
var a=20;
var b=40;
var c=60;

if(a>b){
    console.log("a는 b보다 크다.");
} else if(b>c){
    console.log("b는 c보다 크다.");
} else if(a<c>){
    console.log("a는 c보다 작다.");
} else if(b<c>){
    console.log("b는 c보다 작다.");
}else{
    console.log("모든 조건을 만족하지 않는다.");
}
```

#### 💭 조건문-중첩 if문
if문 안에 또다른 if문을 삽입할 때 사용
```js
 var a=20;
 var b=40;

 if(a!==b){
    if(a>b){
        console.log("a는 b보다 크다.");
    } else {
        console.log("a는 b보다 작다.");
    }
 } else {
    console.log("a와 b는 같다.");
 }
```

### 📌 반복문     

#### 💭 for문
for(초기화한 변수값; 조건; 증감표시){수행할 명령}

```js
for(var i=0; i<10; i++){
    console.log(i);
}
```


#### 💭 while문    
조건이 true이면, 명령을 계속 수행    
while(조건){수행할 명령}    
num<10 이 참일 동안 중괄호 안의 코드를 실행

```js
var num=0;

while (num <10){
    console.log(num); //0123456789
    num++;
    //증감과 콘솔의 순서가 바뀌면 값도 달라진다    
}
```

#### 💭 do~while문

do{수행할 명령} while(조건);    
while의 조건과 관계없이, do의 명령을 무조건 실행부터 한다    
```js
var i =12;

do{
    console.log(i);
    i++;
}while(i<10);
```

### 📌 활용

💭 주사위게임
```js
var dice =Math.floor(Math.random()*6)+1;
```

💭 소수 출력하기
```js
function isPrime(n){
    var divisor =2;            //2부터 나누기 시작
    while(n>divisor){          //n이 나누는 수보다 클 때까지
        if(n % divisor ===0){  //n과 나누는 수가 나누어 떨어지면
            return false;
        }else{
            divisor++;         //나누어 떨어지지 않는다면 나누는 수 1증가
        }
    }return true;
}
```

💭 문자열 거꾸로 출력하기    
문자열 맨 뒤부터 출력해야 하므로 str이 0이 될때까지 1씩 감소    
인덱스는 0부터(문자열길이 -1)이라는 점 유의
```js
function reverse(str){
    var reverStr='';
    for(var i=str.length-1; i>=0; i--){
        reverStr=reverStr+str.charAt(i);
    } return reverStr;
}

console.log(reverse('Hello')) //olleH
```

💭 구구단 만들기
```js
function timesTable(n){
    for(var i=1; i<10; i++){
        document.write(n," x ",i," = ", n*i +"<br/>")
    }
}

timesTable(2); //2단만 출력
timesTable(3); //3단만 출력 
```

💭 이중반복문으로 구구단만들기
```js
for(var i=2; i<10; i++>){
    for(var j=1; j<10; j++>){
        document.writeln(i," + ",j," = ",i*j)
        document.writeln("<br/>") //줄바꿈역활(파이썬의 end="")
    }
}
