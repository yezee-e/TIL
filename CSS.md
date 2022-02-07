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

### flexbox의 특징
***
* **display:flex**는 모든 요소를 가로로 둔다

* **dispay:flex**는 부모한테 적용을 하고 자손을 컨트롤한다.

* **justify-content** :가로로 요소들을 움직인다. (flex-start, center,flex-end,space-between,space-around 등의 값이 있음)

* **align-items** : 세로로 요소들을 움직인다

* **flex-direction**:column 가로로 정렬된 요소들을 세로로 바꾸고 justify-content는 세로로 align-items는 가로방향으로 바뀐다.





