💭 구구단
```js
for(let i=2; i<=9; i++){
for(let j=1; j<=9; j++){
  console.log(i+"*"+j+"="+i*j)
 }
}
```

💭 증감연산자를 이용한 while문 실행
```js
let i=2
while(i<5){
  console.log("while문 실행",i)
  i++;
}
// while문 실행 2
// while문 실행 3
// while문 실행 4
```

💭 배열과 for문
```js
let fruit =["banana","apple","grape","mango"]

for(let i=0; i<fruit.length; i++){
  console.log(fruit[i])
}
// banana
// apple
// grape
// mango
```
💭 합구하기
```js
let sum = 0
for(let i=1;i<=100;i++){
 sum+=i
}
console.log(sum)
//5050
```

💭 홀수만들기
```js
for(i=1; i<=10; i+=2){
  console.log(i)
}

// 1
// 3
// 5
// 7
// 9
```

💭 짝수만들기
```js
 for(i=0; i<=10; i+=2){
  console.log(i)
} 

// 0
// 2
// 4
// 6
// 8
// 10
```
💭 3.6.9만들기
```js
for(i=1; i<=50; i++){
  if(i.includes("3")||i.includes("6")||i.includes("9")){
    console.log("짝") 
  }else if (i.includes("3")&&i.includes("3")){
    console.log("짝짝")
  }
}
```

```js
for(let i=1; i<=35; i++){
  let stringValue= i.toString() //숫자를 문자열로 변환하는 함수
  let result =""
  for(let j=0; j<stringValue.length; j++){
    if(stringValue[j]=="3" || stringValue[j]=="6" || stringValue[j]=="9"){
      result+="짝"
    }
  }  
  console.log(result.length>0?result:i)
}
```

💭 소수판별
```js
let n =7
let isPrime = true//isPrime()소수출력

if (n ===1){// 1은 소수가 아님 
    isPrime = false
}
for(let i=2;i<n;i++){
  if(n % i == 0){
    isPrime =  false 
  }
}
console.log(isPrime)
```

💭 달력출력
```js
function meetAt(year, month, date) {
  let todayYear = year;
  let todayMonth = month;
  let todayDate = date;

  if (todayDate) {
    return `${todayYear}/${todayMonth}/${todayDate}`;
  }
  if (todayMonth) {
    return `${todayYear}년 ${todayMonth}월`;
  }
  if (todayYear) {
    return `${todayYear}년`;
  }

}

console.log(meetAt(2022,1,22))
```

```js
function meetAt(year, month, date) {
  if(date){
    return `${year}/${month}/${date}`
  }else if(month){
    return `${year}년,${month}월`
  }else if(year){
    return `${year}년`
  }
}

console.log(meetAt(2022,1,7))
```

어떤 정수의 제곱근인지 확인    
제곱근이 정수면, 약수의 갯수가 홀수
```js
console.log(Math.sqrt(121));   // 11 
```

주어진 값이 정수인지 확인 
```js
Number.isInteger(1.5);   // false
Number.isInteger(2);     // true
Number.isInteger(3);     // true
```

map()    
현재의배열에서 새로운배열로 반환하는 역할
배열의 모든 원소에 대해 body를 수행한다. (for each문처럼 알아서 각 요소에 body를 적용한다.)
```js
배열.map((요소) => {
  console.log(요소);    //body 예시
}

배열.map((요소, 인덱스) => {
  console.log(인덱스);  //body 예시
  return 요소;    //body 예시
}
```

sort()
sort()의 return 값에 따른 실행내용   
반환 값 < 0 : a가 b보다 앞에 있어야 한다.    
반환 값 = 0 : a와 b의 순서를 바꾸지 않는다.    
반환 값 > 0 : b가 a보다 앞에 있어야 한다.    
```js
배열.sort((a, b)=>{return a - b});
```

filter()
조건을 만족하는 요소 새 배열에 담기
```js
const 변수 = 배열.filter((요소) => 조건문);
//예시
const upTo9000 = itemArr.filter((item) => item.price <= 9000);    //9000원 이하 상품만 새 배열에 담기
```