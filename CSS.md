# css

**색상/뒷배경색/글자위치**

```css
.red {
  color: red;
  background-color: yellow;
  background-color: transparent;
  /* input배경색상 뒷배경과 동일하게 만들기 */
  text-align: center;
}
```

```css
.input-area:focus {
  outline: none;
  /* input테두리없애기 */
}
```

**테두리/폭/높이**

```css
.border-blue {
  border: 1px solid blue;
}

.img-size {
  width: 200px;
  height: 200px;
}
```

**바깥쪽 공간은 margin**

```css
.margin-space {
  margin-top: 40px;
  margin-left: 100px;
  margin-bottom: 40px;
  margin: auto; /* 요소를 가로중앙에 위치 */
}
```

**요소 안쪽에 공간은 padding**

```css
.padding-space {
  padding-top: 40px;
  padding-left: 50px;
}
```

### Html태그에 스타일 주기

---

1. class를 이용한 스타일 주기

```css
.new-style {
  color: red;
}
```

2. id를 이용

```css
#new-style {
  color: red;
}
```

3. 직접적으로 스타일 주기

```css
div {
  color: red;
}
```

4. 복합 선택자

- div span { } : div 부모태그 밑의 모든 span 자식태그들을 지정한다.
- div > span { } : div 부모태그 바로 밑의 span 자식태그를 지정한다.(바로 밑 자식에게만 스타일을 적용)
- div + span { } : div의 바로 아래있는 형제 span 선택.(형제 자식에게 스타일을 적용)
- div~span{ }: div와 같은 부모를 공유하는 모든 span 선택(바로 뒤에 오는 형제 관계가 아닌 tag에도 스타일을 적용)

5.  CSS 적용 우선순위  
    tag << class <<<< id <<<<<<< inline css

### css style

---

- float  
  -주로 이미지 주변에 텍스트를 감싸기 위해 만들어진 프로퍼티  
  -이미지 또는 html태그 _요소를 배치하는데 쓰임_. float를 쓰게되면 해당 영역의 사이즈가 float을 포함하고 있는 컨텐츠 영역 만큼 줄어듬  
  -float 속성에는 left, right, none 가운데 하나를 값으로 줄 수 있다

  - float 문제해결

    1. 바깥 div마지막에 아무태그나 넣고 clear속성을 적용(단점은 html코드가 늘어남)
    2. 바깥 div에 overflow:hidden;을 주는 것

- text-decoration  
  -밑줄치기, 가운대로 긋기 등 텍스트에 여러 효과를 줄 수 있다. 주로 a태그의 거슬리는 스타일 중 하나인 밑줄을 제거하는데 많이 쓴다

- border  
  -div태그로 영역을 나눠도 영역이 얼마나 큰지,어디에 위치하는지 잘 보이지 않을때가 있다. 이때 border을 통해 div 또는 다른 태그들에 태두리를 그림으로서 해당 태그가 얼마나 맣은 영역을 차지하는지 확인  
  ex)border:1px solid red(두께,테두리,색깔)

- hover  
  -css스타일로 이벤트가 발생했을때의 스타일도 줄수있다  
  마우스가 태그위로 올라왔을때 발생하는 이벤트 //이외에도 active,focus 등이 있다.

- display  
  -요소가 어떻게 보여질지를 결정(block,inline-block,none 등)

- border-radius  
  -모서리를 둥글게함

- width  
  -넓이지정

- height  
  -높이지정

- postion  
  -HTML태그의 위치시키는 방식 지정
  -top, right, bottom, left는 postion이라는 프로퍼티가 있을 때만 적용되는 프로퍼티

- font-family  
  -폰트 스타일
  `css #title { font-family: Georgia, "Times New Roman", Times, serif; } `
  "Times New Roman"만 ""(쌍따옴표)로 감싸져 있는데, 폰트 이름에 띄워쓰기가 되어있으면 ""(쌍따옴표)를 사용  
   사용자가 어떤 브라우저를 사용할지 모르기 때문에 font-family 값에는 보통 여러가지 폰트를 나열합니다. 가장 뒤에 위치한 serif같은 폰트는 모든 브라우저에서 지원하는 폰트

- box-shadow  
  -박스뒤그림자
- opacity  
  -투명도
- z-index  
  -숫자가 작을수록 낮은 layer, 클수록 위의 layer  
  fixed, absolute position에 이용 가능.  
  default: 0
- box-sizing:border-box  
  -padding에 상관없이 box의 크기를 변경하고 싶지 않을경우 사용  
  즉, 박스의 크기를 유지한채 paddig을 줄 수 있다  
  -보이는대로 width 값을 주고, 그 후에 그 안 쪽으로 padding을 주는 것  
  -보통 아래와 같이 사용
  ```css
     position:ficxed;
      width:100%:;
      box-sizing: border-box;
  ```
- background-size 속성  
   width와 height를 300px로 만들면 이미지를 담는 영역인 .bgImg크기만 줄인것이고, 배경이미지의 실제 크기는 원본크기 그대로 이면서,
  그 중에서 .bgImg 의 크기(300px\*300px)만큼만 보여지는 것

  이럴 때는 아래와 같이 background-size 속성을 사용하여 배경이미지 크기를 조정

  ````css
  .bgImg {
  background-size: 100%;
   }
   ```
  <br/>

  ````

- visibility:hidden
  - 공간은 그대로 두고 보이지만 않는것
- display:none
  - 잡아둔 공간도 사라짐

### padding or margin

---

> padding과 margin은 1개,2개,3개의 값을 가질 수 있다

**padding:20px** ->모든 방향에 20px의 공간을 준다

**padding:20px 10px** -> 가로방향(top,bottom)에는 20px공간을, 세로방향(left,rigth)에는 10px 만큼의 공간

**padding:10px 20px 30px 40px** ->첫번째부터 top,left,bottom,right순으로 공간을 적용

margin에 auto로 설정하면 요소를 가로 중앙에 위치

### position 속성값

---

- **relative**: 있는자리 기준에서 옮김 (html태그가 있는 위치에서 left,right,top, bottom값을 통해 움직임)
- **absolute**: 부모 절대값 기준으로 옮김( 부모 영역에서 left, right, top, bottom을 이용해 주어진 위치로 움직임)  
   가장 가까운 releative부모를 기준으로 이동
  position:relative; 를 해주면 부모가 된다.
  없으면 body.  
  absolute값을 가지게 되면, 내용의 크기만큼만이 가로크기

- **static**: left.top 등을 이해하지 못함 즉, 자기 자리만 지킴(브라우저의 기본속성)

- **fixed**: absolute와 비슷하지만 스크롤로 내려도 그 위치에 고정. 무조건 브라우저 창 기준(따라 내려오는것 처럼 보임)  
  초기 위치에 고정. 다른 레이어상에서 자리잡음 따라서 top,bottom,right,left사용시 margin과 초기 위치등이 무시되고 명령한 위치에 자리
  즉, potion:fixed는 새로운 layer를 만듦

- **sticky**: relative와 비슷하지만 스크롤로 내리면 fixed처럼 그 위치에 고정

### display: flex

---

**flex-box**  
자식에게 명시하지 않고 부모 엘리먼트에만 명시  
div의 부모를 display:flex로 만든다  
justify-content:주축은 수쳥(row)  
align-items:교차축은 수직(colum)  
flex-direction:flex의 방향을 명시  
flex-wrap:

> **justify-content**  
> (이 CSS 속성은 요소들을 _가로선_ 상에서 정렬하며 다음의 값들을 인자로 받는다)

- flex-start: 요소들을 컨테이너의 왼쪽으로 정렬합니다.
- flex-end: 요소들을 컨테이너의 오른쪽으로 정렬합니다.
- center: 요소들을 컨테이너의 가운데로 정렬합니다.
- space-between: 요소들 사이에 동일한 간격을 둡니다.
- space-around: 요소들 주위에 동일한 간격을 둡니다.

> **align-items**  
> (이 CSS 속성은 다음의 값들을 인자로 받아 요소들을 _세로선_ 상에서 정렬)

- flex-start: 요소들을 컨테이너의 꼭대기로 정렬합니다.
- flex-end: 요소들을 컨테이너의 바닥으로 정렬합니다.
- center: 요소들을 컨테이너의 세로선 상의 가운데로 정렬합니다.
- baseline: 요소들을 컨테이너의 시작 위치에 정렬합니다.
- stretch: 요소들을 컨테이너에 맞도록 늘립니다.

> **flex-direction**  
>  (이 CSS 속성은 다음의 값들을 인자로 받아 컨테이너 안에서 요소들이 정렬해야 할 *방향*을 지정)

- row: 요소들을 텍스트의 방향과 동일하게 정렬합니다.
- row-reverse: 요소들을 텍스트의 반대 방향으로 정렬합니다.
- column: 요소들을 위에서 아래로 정렬합니다.
- column-reverse: 요소들을 아래에서 위로 정렬합니다.

> ** Flex의 방향이 column일 경우 justify-content의 방향이 세로로, align-items의 뱡향이 가로로 바뀝니다.**

> **order** 컨테이너의 row나 column의 순서를 역으로 바꾸는 것만으로는 충분하지 않습니다. order의 기본 값은 0이며, 양수나 음수로 바꿀 수 있습니다.

> **align-self**
> (개별 요소에 적용할 수 있는 또 다른 속성)
> 이 속성은 align-items가 사용하는 값들을 인자로 받으며, 그 값들은 지정한 요소에만 적용됩니다.

> **flex-wrap**

- nowrap: 모든 요소들을 한 줄에 정렬합니다.
- wrap: 요소들을 여러 줄에 걸쳐 정렬합니다.
- wrap-reverse: 요소들을 여러 줄에 걸쳐 반대로 정렬합니다.

> **flex-flow**  
>  flex-direction과 flex-wrap이 자주 같이 사용되기 때문에, flex-flow가 이를 대신
> 이 속성은 공백문자를 이용하여 두 속성의 값들을 인자로 받습니다.
> 예를 들어, 요소들을 가로선 상의 여러줄에 걸쳐 정렬하기 위해 flex-flow: row wrap을 사용할 수 있습니다.

> **align-content**  
>  (여러 줄 사이의 간격을 지정)

- flex-start: 여러 줄들을 컨테이너의 꼭대기에 정렬합니다.
- flex-end: 여러 줄들을 컨테이너의 바닥에 정렬합니다.
- center: 여러 줄들을 세로선 상의 가운데에 정렬합니다.
- space-between: 여러 줄들 사이에 동일한 간격을 둡니다.
- space-around: 여러 줄들 주위에 동일한 간격을 둡니다.
- stretch: 여러 줄들을 컨테이너에 맞도록 늘립니다.

### block 요소와 inline 요소

---

- block요소  
  대부분의 HTML element는 block 요소  
  `<header>, <footer>, <p>, <li>, <table>, <div>, <h1>` 등  
  block 요소의 의미는, 이 요소 바로 옆(좌우측)에 다른 요소를 붙여넣을 수 없다는 뜻(가로 전체를 차지)

- inline요소  
  `<span>, <a>, <img>` 태그 등  
  inline이라는 말 그대로 inline 요소는 요소끼리 서로 한 줄에, 바로 옆에 위치할 수 있다는 뜻

<br/>

아무 태그나 사용해도 결국은 CSS를 통해 얼마든지 성질을 바꿀 수 있다
inline 성질을 갖도록 하는 CSS property는 `display` 와 `float` 이 있다

### 의미론적인 태그(semantic elements)

---

문서의 정보를 더 잘 표현하기 위해 부위에 맞게 의미를 부여하는 태그

| < header >  |           |
| :---------- | :-------: |
| < nav >     |           |
| < section > | < aside > |
| < article > |           |
| < footer >  |           |

이외에도 < details > < figcaption > < figure > < main > < summary> < time >이 있음

### 단위정리

---

- **px** -절대적인 값. 다른 값이 영향을 받지 않음
- **em** -상위 요소 폰트크기 기준. 예를들어 폰트가 12px이면 1em은 12px. 화면사이즈에 따라 반응형웹을 만들 때 쓰기 좋음
- **rem** -em이랑 비슷함 하지만 HTML태그의 폰트크기 기준. 예를들어 내 자신이 12PX이라도 html이 20px이면 1rm은 20px
- **%** -상위요소 크기 기준으로 %를 따짐

### pseudo selectors

---

좀더 세부적으로 엘리먼트를 선택해 주는 것
선택의 복잡한 과정을 pseudo selector로 가능함

```css
div:first-child {
  background-color: tomato;
}
```

### status(active,focus,hover,over,visited,focus-withn)

---

조건을 나열해 여러 상황을 설정할 수 있음.
EX> form:hover input:focus{ }
<br/>

- **active** 해당 요소를 마우스로 "클릭"했을 때 효과를 적용
- **hover** 마우스가 해당 요소 "위를 지나갈 때" 효과를 적용
- **focus** 키보드로 선택되었을 때 효과를 적용
- **visited** "링크"에만 적용. 방문한 사이트일 경우에 효과를 적용
- **focus-within** 부모 요소에게 적용. 자신의 자식 요소 중 하나가 focused되었을 때 효과를 적용

### pseudo element

---

- ::placeholder placehoder만을 꾸밀때 사용
- ::selection 드래그 했을때 css
- ::first-letter 앞 글자에 css
- ::first-line 첫 줄 css

### color system

---

1. hex code
   : #2ecc71와 같은 색상 코드
2. rgb
   : 각각 red, green, blue를 의미  
   가령, rgb(0,140,200)의 경우엔 red 값이 0, green 값이 140, blue 값이 200이라고 이해할 수 있습니다.
3. rgba
   : 2와 동일하지만 a가 포함된 형태. 'a(alpha)'는 투명도를 담당
   0(투명)~1(불투명) 사이의 값으로 조절

### variable(custom property)

---

:root 라는 엘리먼트에 변수를 추가하는 것  
:root은 기본적으로 모든 document의 뿌리가 되는 것

```css
:root{
--main-color
}
var(--main-color)
```

### transition

---

어떤 상태에서 다른 상태로의 변화! 를 보내주는 애니매이션  
transition 값은 태그의 root(근원, 기본css 태그) 에 넣는 것이고  
transition 이 적용되는 항목은 “어떤 속성(attribute 조건)일 때 어떻게 변할지 따로” 적는다.  
예) “김 ㅇㅇ씨 링크 글씨색을 마우스 갖다대면 바뀌게 할 수 있어요?
좀 부드럽게?”

```css
a {
color: white;
transition: all 1s ease-in-out

a:hover{
color: tomato;

```

=기본값(root)에선 링크의 폰트컬러가 화이트
마우스를 갖다대면 폰트컬러가 1초에 걸쳐 토마토색으로 변한다  
<br/>
"ease-in function"은 브라우저에게 애니메이션이 어떻게 변할지 말해주는 기능이다.
→ default로 갖고 있는 것은 linear, ease-in, ease-in-out, ease-out, ease

### transformation

---

transformation은 box element를 변형시키지 않는다.  
즉, 옆에 sibling들에게 영향을 끼치지 않는다.
margin, padding이 적용되지 않는다. 일종의 3D transformation이기 때문  
transform과 transition을 조합하면 더 역동적인 애니메이션을 만들 수 있다.  
 CSS 3D는 GPU로 돌아가므로, 3D 작업을 할 수 있다.

### animations

---

- 애니메이션 코드를 작성 한 후 적용을 원하는 대상 요소에서
  animation: animationname 5s ease-in-out infinite;를 넣어 실행시킬 수 있다.

- from to 말고, 1,2,3,4,5...10 혹은 0% 25% 50% 75% 100% 같이 여러 단계로 나뉘어 애니매이션을 만들 수 있다.

```CSS
@keyframs 에니메이션이름{
from {
transform: rotatex(0);
}
to {
transform: rotatex(360deg);
}
}
```

OR

```CSS
@keyframs 에니메이션이름{
0% {
transform: rotatex(0);
}
50% {
transform: rotatex(180deg) translateY(100px);
}
100%{
transform:rotex(0);
 }
}
```

### media queries

---

```CSS
 @media screen and (min-width: npx) and (max-width:npx) and (orientation : landscape혹은portrait) {
div{ backgound-color:wheat;}
}
```

스크린 사이즈에 따라서 property 조정 가능함. orientation으로 가로 세로 감지 가능  
 <br/>

@media print를 이용하면 브라우저 프린트 화면에서의 속성을 변경할 수 있다.

@media query는 코드의 조건을 추가 할 수 있는 방법이다.

- media query도 {} 중괄호로 여닫는다. 그 안에 element에 속성을 적용시켜야 한다.
- media query는 "and"를 써서 연결된다.
- "min-width" 뿐만 아니라, "min-device-width"도 있다.(-device-width는 오직 핸드폰에만 적용된다.)
