# html

!DOCTYPE html를 사용하여 시작  
html은 부모,자식 태그로 만들어져있다

### 🎈태그배우기

<br/>

**`<H1></H1>` 제목**
<br/>

**`<U></U>` 밑줄**
<br/>

**`<a></a>` 링크**
<br/>

**`<strong></strong>` 강조**
<br/>

**` <input>``<textarea> ` 사용자가 직접 텍스트를 입력할 수 있는 태그**

- input

  - 문자판숫자,문자,암호 넣기가능
  - 태그의 required 속성은 폼 데이터(form data)가 서버로 제출되기 전 반드시 채워져 있어야 하는 입력 필드를 명시합니다.

  - form태그를 사용하면 자동으로 페이지 유효성 검사가 가능하다(예를들어, 공란이나 엔터 등을 관리)
  - form을 submit하면 브라우저는 기본적으로 페이지를 새로고침 하도록 되어있다. << 우리가 원하는 것이 아님!
  - preventDefault() 함수를 추가함으로써 브라우저의 기본 동작을 막을 수 있다!!

    ```js
    function onLoginSubmit(event) {
      event.preventDefault(); // 브라우저가 기본 동작을 실행하지 못하게 막기
      // event object는 preventDefault함수를 기본적으로 갖고 있음
      console.log(event);
    }
    ```

- textarea  
  input보다는 더 긴 텍스트를 입력받고 싶을 때 사용  
  보통 짧은 방명록이나 댓글을 입력할때 사용

<br/>

**`<button></button>` 버튼**
<br/>

**`<img>` 이미지넣기**

- img 태그에 사용된 속성
  - alt: 이미지가 불러올 수 없을 때(서버에서 이미지가 삭제됐거나 잘못된 이미지 주소일 때..), 이미지 대신 보여줄 텍스트
  - src: 이미지 파일 경로 혹은 이미지 url 주소
    <br/>

**`<div></div>` 줄바꾸기**
<br/>

**`<p></p>` 줄바꾸기**
<br/>

**`<span></span>` 그룹을 나누어 주되 다른 기능은 없음**
<br/>

**`<form></form>`**  
2가지 속성(attribute)->하나는 action이고, 다른 하나는 method이다.

    -action은 어떤 페이지로 data를 보낼건지 지정
    action에 적어 놓은 URL에 해당하는 파일이 반드시 존재해야한다.

    -method는 2가지 방식 중 하나를 쓸 수 있다. 하나는 POST이고, 다른 하나는 GET이다.
    - POST는 백엔드 서버에 정보를 전송하는 방식
    - GET 방식은 보안에 취약하다. username이랑 password를 GET 방식으로 보내선 안된다. URL에 포함되어도 상관없는 정보들을 GET 방식으로   보내는 것

**`<li></li>, <ol></ol>, <ul></ul>`리스트 만들기**  
목록 아이템 하나하나를 `<li>` 태그로 감싸준다  
목록은 항상 `<ul>` 나 `<ol>`태그로 감싸야 한다(아무 스타일도 넣고 싶지 않다고 `<il>`태그만 사용불가)  
`<ol>`은 ordered list라는 의미로, 목록에 숫자를 달아준다  
즉, 자동으로 numbering

`<ul>`태그는 unordered list라는 의미로 숫자없는 목록을 표현(점으로 표현)

<br/>

**`<blockquote></blockquote>`**  
 인용구문을 넣을 때 쓰는 태그  
 양쪽 여백을 넣는 기본 스타일을 자동으로 적용
<br/>

**`<table></table>` 표만들기**  
테이블은 항상 `<table>`태그로 감싸져있다 , 태그 내에 행도 만들고 열도 만드는 것  
한 행을 시작할 때는 `<tr>`로 시작 -> tr은 table row의 줄임말  
각각의 셀은 `<tr>`태그 내에 `<td>`태그를 사용 -> td는 table data의 줄임말  
`<th>`태그 -> th는 table heading의 줄임말

병합은 `<td>` 나 `<th>`태그에 colspan, rowspan이라는 attribute를 추가해서 구현  
rowspan은 행 병합, colspan은 열을 병합

**`<select><select/>`**

```html
<select>
  <option>옵션1</option>
  <option>옵션2</option>
</select>
```

### 🎈learn more

---

- 문장사이에 스페이스 추가방법  
  스페이스를 의미하는 `&nbsp;` 을 추가
  ```html
  <p>스페이스 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;넣는 예제</p>
  ```
- CND(content delivery)  
  웹 콘텐츠를 사용자와 가까운 곳에서 전송함으로서 전송 속도를 높임

### 🎈단축키

---

- **이모지** 윈도우키+;
- **control+d** 한번에 태그 같이 수정
- **shift + alt + 아래(or 위)방향키** 해당줄을 복붙
- **태그자동완성** div class="name"은 div.name으로
  div id="id"는 div#id
- **태그 많이 만들기** ex. div를 10개 -> div\*10
- comment 처리 작성후 Ctrl + / 윈도우키 + .
