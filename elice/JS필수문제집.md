
📌  여러줄로 출력    
400,bus,like단어들 사이에 \n을 입력하여 줇바꿈
```js
function solution(){
    return "400\nbus\nlike";
}

fuction()

//400
//bus
//like
```

📌  따옴표 출력     
```js
function solution() {
    
  return "\"It\'s all right.\"";
}
//"It's all right."
```

📌 공백추가    
+연산자를 이용하여 문자열을 합한다       
세 변수 사이에는 공백이 들어가야 하므로 " "를 추가
```js
function solution() {
    var a=400
    var b="bus"
    var c="like"
  return a+" "+b+" "+c;
//400 bus like
}
```

📌 한식 10%할인
```js
function solution() {
  var korean=7000;
  var discount_korean=korean-korean*0.1; //한식 10%할인가격
  
  return discount_korean;
  //6300
}
```

📌 몫과 나머지 구하기
```js
function solution(num1, num2) {
  let answer = [];
    answer.push(Math.floor(num1/num2));
    answer.push(num1%num2);
  return answer; 
}

solution(35,3) //[ 11, 2 ]
```
```js
function solution(num1, num2) {
    var a =Math.floor(num1/num2);
    var b =Math.floor(num1%num2);
  let answer = [a,b];

  return answer; 
}

solution(35,3) //[ 11, 2 ]
```

📌 문자열 자르기
```js
function solution(str) {
  var answer = []; 
  var a = str.split(" "); //주어진 문자열을 공백을 기준으로 나눠 배열로
    answer.push(typeof a) //a의 타입을 알 수 있도록 typeof 연산자 결과를 answer 배열에 추가
    answer.push(a[0]) //주어진 문자열의 첫번째 단어를 a의 두번째 원소에 저장
  return answer;
  //[ 'object', 'Good' ]
}
```
📌 N줄 입력받기    
```js
const arr = "goodnogoodnogood".split("no");
console.log(arr); // [good, good, good]
```