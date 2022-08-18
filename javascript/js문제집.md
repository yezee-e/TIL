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