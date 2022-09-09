## Semantic Web과 Semantic Tag
***
### 📌Semantic Web   
기계가 읽고 처리할 수 있는 웹을 개발하고자 탄생   
잡다한 데이터 집합이 아닌 ‘의미’ 와 ‘관련성’을 가지는 거대한 데이터베이스를 구축하고자 하는 발상    
구성요소:RDF, XML, Ontology,Agent   


```html
<div id="header"></div> 
<!-- 이전 -->
```
```html
<header></header> 
<!-- 이후 -->
```
### 📌Semantic Tag    
과거 무분별한 태그의 사용으로 인해 정보를 찾기 위해 사람들이 직접 개입해야 하는 비효율적인 시스템을 개선하고자, 의미있는 태그들를 개발

* div, span 등 이들의 태그는 content에 대한 설명이 없다
* article, aside, footer, header, main, nav, section 등 부분의 성격에 따라 쓰는 태그들이 등장

  <img src="pic\semantictag.png" width=50%>

* img Tag vs div background-image   
img태그를 사용시 alt속성에 문자열 삽입가능     
alt속성에 작성된 문자열은 meta정보가 되며, 검색엔진은 alt속성에 지정된 문자열을 인식   
사용자는 검색을 통해 정보를 가져간다 => 내 이미지가 사용자의 검색에 노출되어야 한다면, img 태그를 사용하는 것이 좋다

  div background-image의 경우 단순한 이미지 첨부일 뿐, 어떠한 정보도 담지 않는다.
  사이트를 꾸미기 위한 장식 => 이미지의 활용이 순수 사이트의 장식을 위해서라면, background-image를 사용하는 것이 좋다.

결론적으로    
**img tag**    
결국 의미가 있는 시멘틱 태그로서 컴퓨터가 이해할 수 있다   
alt속성으로 에러 발생 시 이미지가 깨져도 의미를 알 수 있다

**background-image**     
의미있는 태그가 아닌 그냥 속성으로 에러시 어떠한 이미지인지 어떠한 정보도 알 수 없다   
또 컴퓨터는 이 태그가 어떤 이미지인지 알 수 없습니다