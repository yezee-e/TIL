# html

!DOCTYPE html를 사용하여 시작   
html은 부모,자식 태그로 만들어져있다
### 🎈태그배우기
<br/>

**H1 제목** 
 <br/>

 **U 밑줄** 
<br/>

**a 링크** 
<br/>

**strong 강조** 
<br/>

 **input 문자판숫자,문자,암호 넣기가능**    
 - 태그의 required 속성은 폼 데이터(form data)가 서버로 제출되기 전 반드시 채워져 있어야 하는 입력 필드를 명시합니다.
 
- form태그를 사용하면 자동으로 페이지 유효성 검사가 가능하다(예를들어, 공란이나 엔터 등을 관리)    
- form을 submit하면 브라우저는 기본적으로 페이지를 새로고침 하도록 되어있다. << 우리가 원하는 것이 아님!    
- preventDefault() 함수를 추가함으로써 브라우저의 기본 동작을 막을 수 있다!!   

    ```js
    function onLoginSubmit(event){
    event.preventDefault(); // 브라우저가 기본 동작을 실행하지 못하게 막기    
    // event object는 preventDefault함수를 기본적으로 갖고 있음
    console.log(event);
    }
    ```

<br/>

 **button 버튼** 
<br/>

 **img 이미지넣기** 
<br/> 

**div 줄바꾸기** 
<br/>

**p 줄바꾸기** 
 <br/>

**span 그룹을 나누어 주되 다른 기능은 없음** 
 <br/>

**form**   
2가지 속성(attribute)->하나는 action이고, 다른 하나는 method이다.

    -action은 어떤 페이지로 data를 보낼건지 지정    
    action에 적어 놓은 URL에 해당하는 파일이 반드시 존재해야한다.   

    -method는 2가지 방식 중 하나를 쓸 수 있다. 하나는 POST이고, 다른 하나는 GET이다.    
    - POST는 백엔드 서버에 정보를 전송하는 방식    
    - GET 방식은 보안에 취약하다. username이랑 password를 GET 방식으로 보내선 안된다. URL에 포함되어도 상관없는 정보들을 GET 방식으로   보내는 것

**ol 번호 리스트 만들기**
<br/>

**ul 점 리스트만들기**
 <br/>

 **blockquote**   
 인용구문을 넣을 때 쓰는 태그  
 양쪽 여백을 넣는 기본 스타일을 자동으로 적용
  <br/>


### 🎈learn more
***
* 문장사이에 스페이스 추가방법   
스페이스를 의미하는   `&nbsp;` 을 추가
  ```html
  <p>스페이스 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;넣는 예제</p>
  ```
* CND(content delivery)   
웹 콘텐츠를 사용자와 가까운 곳에서 전송함으로서 전송 속도를 높임   




### 🎈단축키
***
* **이모지**  윈도우키+;
* **control+d** 한번에 태그 같이 수정
* **shift + alt + 아래(or 위)방향키**   해당줄을 복붙 
* **태그자동완성** div class="name"은 div.name으로
div id="id"는 div#id
* **태그 많이 만들기** ex. div를 10개 -> div*10
*  comment 처리  작성후 Ctrl + / 윈도우키 + .

