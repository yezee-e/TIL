
## 숫자자료형
***
### 임의의 값 생성
```py
from random import *
from math import *

print(floor(random()*45+1)) #1~45이하의 임의의 값 생성 
print(int(random()*45+1)) #1~45이하의 임의의 값 생성 
print(randrange(1,46)) #1~46 미만의 임의의 값 생성 
print(randint(1,45)) #1~45 이하의 임의의 값 생성(괄호안의 수를 포함하여 램덤숫자생성) 
```

## 문자열 자료형
***
### 💨변수에 여러문자 넣기
```py
sentence="""
나는 소년이고,
파이썬은 쉬어요,
자바스크립트랑 조금 달라요
"""
print(sentence)
```
### 💨슬라이싱
```py
jumin ="950119-1234567"

print("성별:"+jumin[7]) #성별:1
print("연:"+jumin[0:2]) #0~2직전까지 ,연:95
print("월:"+jumin[2:4]) #월:01
print("일:"+jumin[4:6]) #일:19
print("생년월일:"+jumin[:6]) #처음부터 6직전까지 ,생년월일:950119
print("뒤 7자리:"+jumin[7:]) #7부터 끝까지 ,뒤 7자리:1234567
print("뒤 7자리(뒤에서부터):"+jumin[-7:]) #뒤 7자리(뒤에서부터):1234567
```
### 💨문자열처리함수
```py
python ="Python is Amazing"

print(python.lower()) #소문자출력
print(python.upper()) #대문자출력
print(python[0].isupper()) #변수python의 첫번째문자의 값이 대문자이냐(boolen)
print(len(python)) #문자열길이반환
print(python.replace("Python","java")) #문자열변환

index =python.index("n") #몇번째문자열인지찾기 ,5
print(index)
index =python.index("n", index+1) #찾은문자열의 다음번자리찾기 ,15
print(index)
print(python.find("n"))   #몇번째문자열인지찾기 ,5

print(python.find("java")) #-1  
index =python.index("java") #출력오류발생
print(index)
#find함수는 원하는 값이 없을경우 -1을 반환, 반면 index함수는 오류출력 
print(python.count("n")) #문자열이 몇개인지 출력
```
### 💨문자열포맷방법
* 방법1- %사용
```py
print("나는 %d살 입니다" %20) #d는 정수를 의미(integer)
print("나는 %s을 좋아해요" %"파이썬") #s는 문자열을 의미(string)
print("Apple은 %c로 시작해요" %"A") #c는 한 글자만을 의미(character)

print("나는 %s살 입니다" %20) #%s는 정수로 출력가능
print("나는 %s색과 %s색을 좋아해요" %("파란","빨간")) 
```

* 방법2-{}사용
```py
print("나는 {}살입니다." .format(20))
print("나는 {}색과 {}색을 좋아해요" .format("파란","빨간")) #나는 파란색과 빨간색을 좋아해요
print("나는 {1}색과 {0}색을 좋아해요" .format("파란","빨간")) #나는 빨간색과 파란색을 좋아해요
```

* 방법3-지역변수로 사용
```py
print("나는 {age}살이며, {color}색을 좋아해요" .format(age=20, color="빨간"))
print("나는 {age}살이며, {color}색을 좋아해요" .format( color="빨간",age=20))
```

* 방법4(V3.6 이상~)-전역변수로 사용
```py
color ="빨간"
print(f"나는 {age}살이며, {color}색을 좋아해요")
```
### 💨탈출문자 
* \n:줄바꿈
```py
print("백문이 불여일견 \n백견이 불여일타")    
```

* \"\' :문자 내에서 따옴표
```py
print("저는 '나도코딩'입니다.") #저는 '나도코딩'입니다.
print('저는 "나도코딩"입니다.') #저는 "나도코딩"입니다.
print("저는 \"나도코딩\"입니다.") #""앞에 \붙이기 (""출력해주는역할) ,저는 "나도코딩"입니다.
```

* \\ :문자내에서 \
```py
print("\\Desktop\\코코\\learn_python") #\Desktop\코코\learn_python
``` 

* \r :커서를 맨 앞으로 이동
```py
print("Red Apple\rpine") #pineApple
```

* \b :백스페이스(한 글자 삭제)
```py
print("Redd\bApple") #RedApple
```

* \t :탭
```py
print("Red\tApple") #Red     Apple
```