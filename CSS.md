# css
***
* class를 이용한 스타일주기
* id를 이용
* 직접적으로 스타일 주기
* 복합 선택자
### 실습해보기
***
**색상/뒷배경색/글자위치**
````css
        .red{
    color:red;
    background-color:yellow;
    text-align: center;

        }
````
**테두리/폭/높이**
```css
        .border-blue{
    border:1px solid blue;
        }

        .img-size{
    width: 200px;
    height: 200px;
        }
```
**바깥쪽 공간은 margin**
```css
        .margin-space{
    margin-top:40px;
    margin-left:100px;
    margin-bottom:40px;
        }
```
**요소 안쪽에 공간은 padding**
```css
    .padding-space{
    padding-top:40px;
    padding-left:50px;
    }
````
### learn more(스타일정리)
***
* float -이미지 또는 html태그 _요소를 배치하는데 쓰임_. float를 쓰게되면 해당 영역의 사이즈가 float을 포함하고 있는 컨텐츠 영역 만큼 줄어듬

* text-decoration -밑줄치기, 가운대로 긋기 등 텍스트에 여러 효과를 줄 수 있다. 주로 a태그의 거슬리는 스타일 중 하나인 밑줄을 제거하는데 많이 쓴다

* border -div태그로 영역을 나눠도 영역이 얼마나 큰지,어디에 위치하는지 잘 보이지 않을때가 있다. 이때 border을 통해 div 또는 다른 태그들에 태두리를 그림으로서 해당 태그가 얼마나 맣은 영역을 차지하는지 확인   
ex)border:1px solid red(두께,테두리,색깔)

* hover -css스타일로 이벤트가 발생했을때의 스타일도 줄수있다   
마우스가 태그위로 올라왔을때 발생하는 이벤트 //이외에도 active,focus 등이 있다.

* display -요소가 어떻게 보여질지를 결정
* border-radius -모서리를 둥글게함
* width -넓이지정 
* height -높이지정
* postion -HTML태그의 위치시키는 방식 지정
* font-family -폰트 스타일
* box-shadow -박스뒤그림자

### padding or margin
***
>padding과 margin은 1개,2개,3개의 값을 가질 수 있다   

**padding:20px** ->top,bottom,right 모든 방향에 20px의 공간을 준다   

**padding:20px 10px** -> 가로방향(top,bottom)에는 20px공간을, 세로방향(left,rigth)에는 10px 만큼의 공간

**padding:10px 20px 30px 40px** ->첫번째부터 top,left,bottom,right순으로 공간을 적용

### position 속성값
***
* **static**: 웹사이트의 기본 속성값   
* **relative**: html태그가 있는 위치에서 left,right,top, bottom값을 통해 움직임   
* **absolute**: 부모 영역에서 left, right, top, bottom을 이용해 주어진 위치로 움직임   
* **fixed**: absolute와 비슷하지만 스크롤로 내려도 그 위치에 고정   
* **sticky**: relative와 비슷하지만 스크롤로 내리면 fixed처럼 그 위치에 고정

### about- display: flex
***

>**justify-content**   
(이 CSS 속성은 요소들을 _가로선_ 상에서 정렬하며 다음의 값들을 인자로 받는다)
 * flex-start: 요소들을 컨테이너의 왼쪽으로 정렬합니다.
 * flex-end: 요소들을 컨테이너의 오른쪽으로 정렬합니다.
 * center: 요소들을 컨테이너의 가운데로 정렬합니다.
 * space-between: 요소들 사이에 동일한 간격을 둡니다.
 * space-around: 요소들 주위에 동일한 간격을 둡니다.  


> **align-items**   
(이 CSS 속성은 다음의 값들을 인자로 받아 요소들을 _세로선_ 상에서 정렬)
 * flex-start: 요소들을 컨테이너의 꼭대기로 정렬합니다.
 * flex-end: 요소들을 컨테이너의 바닥으로 정렬합니다.
 * center: 요소들을 컨테이너의 세로선 상의 가운데로 정렬합니다.
 * baseline: 요소들을 컨테이너의 시작 위치에 정렬합니다.
 * stretch: 요소들을 컨테이너에 맞도록 늘립니다. 

>**flex-direction**   
 (이 CSS 속성은 다음의 값들을 인자로 받아 컨테이너 안에서 요소들이 정렬해야 할 _방향_을 지정)
 * row: 요소들을 텍스트의 방향과 동일하게 정렬합니다.
 * row-reverse: 요소들을 텍스트의 반대 방향으로 정렬합니다.
 * column: 요소들을 위에서 아래로 정렬합니다.
 * column-reverse: 요소들을 아래에서 위로 정렬합니다.

>** Flex의 방향이 column일 경우 justify-content의 방향이 세로로, align-items의 뱡향이 가로로 바뀝니다.**

>**row** 컨테이너의 row나 column의 순서를 역으로 바꾸는 것만으로는 충분하지 않습니다.  order의 기본 값은 0이며, 양수나 음수로 바꿀 수 있습니다.

>**align-self**
 (개별 요소에 적용할 수 있는 또 다른 속성)
 이 속성은 align-items가 사용하는 값들을 인자로 받으며, 그 값들은 지정한 요소에만 적용됩니다.

>**flex-wrap**
 * nowrap: 모든 요소들을 한 줄에 정렬합니다.
 * wrap: 요소들을 여러 줄에 걸쳐 정렬합니다.
 * wrap-reverse: 요소들을 여러 줄에 걸쳐 반대로 정렬합니다.

>**flex-flow**   
 flex-direction과 flex-wrap이 자주 같이 사용되기 때문에, flex-flow가 이를 대신
 이 속성은 공백문자를 이용하여 두 속성의 값들을 인자로 받습니다.
예를 들어, 요소들을 가로선 상의 여러줄에 걸쳐 정렬하기 위해 flex-flow: row wrap을 사용할 수 있습니다.

>**align-content**   
 (여러 줄 사이의 간격을 지정)
 * flex-start: 여러 줄들을 컨테이너의 꼭대기에 정렬합니다.
 * flex-end: 여러 줄들을 컨테이너의 바닥에 정렬합니다.
 * center: 여러 줄들을 세로선 상의 가운데에 정렬합니다.
 * space-between: 여러 줄들 사이에 동일한 간격을 둡니다.
 * space-around: 여러 줄들 주위에 동일한 간격을 둡니다.
 * stretch: 여러 줄들을 컨테이너에 맞도록 늘립니다.


### 의미론적인 태그(semantic elements)
***
문서의 정보를 더 잘 표현하기 위해 부위에 맞게 의미를 부여하는 태그

|< header >|  |
|:---|:---:|
|< nav >|     |
|< section >|< aside > |
|< article >|  |
|< footer >|  |

이외에도 < details > < figcaption > < figure > < main > < summary> < time >이 있음

### 단위정리
***
* __px__ -절대적인 값. 다른 값이 영향을 받지 않음
* __em__ -상위 요소 폰트크기 기준. 예를들어 폰트가 12px이면 1em은 12px. 화면사이즈에 따라 반응형웹을 만들 때 쓰기 좋음
* __rem__ -em이랑 비슷함 하지만 HTML태그의 폰트크기 기준. 예를들어 내 자신이 12PX이라도 html이 20px이면 1rm은 20px
* __%__ -상위요소 크기 기준으로 %를 따짐







