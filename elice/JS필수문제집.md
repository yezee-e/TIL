
💭  여러줄로 출력    
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

💭  따옴표 출력     
```js
function solution() {
    
  return "\"It\'s all right.\"";
}
//"It's all right."
```

💭 공백추가    
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

💭 한식 10%할인
```js
function solution() {
  var korean=7000;
  var discount_korean=korean-korean*0.1; //한식 10%할인가격
  
  return discount_korean;
  //6300
}
```

💭 몫과 나머지 구하기
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

💭 문자열 자르기
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
💭 N줄 입력받기    
```js
const arr = "goodnogoodnogood".split("no");
console.log(arr); // [good, good, good]
```

💭 1부터 200사이의 소수의 합 구하기     
**소수- 1과 자기 자신만을 약수로 가지는 수**
```js
function solution() {
  var sum = 0;

  for (var i = 1; i <= 200; i++) { //상위 반복문에서 1부터 200까지 반복을 합니다.
    for (var j = 2; j <= i; j++) { //하위 반복문에서는 1은 소수에 포함되지 않기에 2부터 i까지 반복을 합니다.
      if (i % j == 0) {
        break; //i와 j를 나누었을 때, 나머지가 0이면 자기 자신만을 가지는 가지는 소수이기 때문에 하위 반복문을 멈춥니다. 
      }
    }
    if (j == i) {
      sum += j; //상위 반복문에서는 j와 i가 같을 때 소수이기 때문에 sum 변수에 소수를 더합니다.
    }
  }

  return sum; //4227
}
```

💭 약수찾기    
```js
//input값까지 i값을 증가시키면서, input이 i값으로 나누어 나머지가 0인 수를 answer 배열에 추가
function solution(input) {
  var answer = [];
  for (let i = 1; i <= input; i++) {
    if (input % i === 0) {
      answer.push(i);
    }
  }
  return answer;
}
```

💭 중첩된 배열펼치기   
자바스크립트 배열 메소드 중에서 **flat 메소드** 활용    
```js  
function solution(arr) {
  var answer;

  answer = arr.flat();

  return answer;
}
```
주어진 2차원 배열을 모두 읽기 위해서는 반복문을 두 번 돌아야 한다       
먼저 [ ]를 돌기 위한 것이고, 그 다음에는 [ [ ] ] 배열 안에있는 배열을 돌기 위한 것
```js
function solution(arr) {
  var answer = [];

  for (let i = 0; i < arr.length; i++) {
      for (let j = 0; j < arr[i].length; j++) {
          answer.push(arr[i][j]);
      }
  }

  return answer;
}
```

💭 노동요   
둘의 차이 비교
```js
function solution(s) {
  var answer="";
  for(var i=0; i<s.length; i++){
      if(s[i]==" "){
          answer+="링디기디기\n"
      }else if(s[i]=="."){
          answer+="딩딩딩\n"
      }else{
          answer+="링딩동 "
      }
  }

  return answer;

 // 링딩동 링딩동 링디기디기
//링딩동 링딩동 링딩동 딩딩딩
}
```
```js
function solution(s) {
  var answer=[];
  for(var i=0; i<s.length; i++){
      if(s[i]==" "){
          answer.push("링디기디기\n")
      }else if(s[i]=="."){
          answer.push("딩딩딩\n")
      }else{
          answer.push("링딩동 ")
      }
  }

  return answer;
  //[ '링딩동 ', '링딩동 ', '링디기디기\n', '링딩동 ', '링딩동 ', '링딩동 ', '딩딩딩\n' ]
}
```