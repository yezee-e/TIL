
## 숫자자료형
***
### 임의의 값 생성
```py
from random import *
from math import *

range(5) #[0,1,2,3,4]
range(1,6) #[1,2,3,4,5]

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
index =python.index("n", index+1) #찾은문자열의 다음번자리찾기 ,15
print(python.find("n"))   #몇번째문자열인지찾기 ,5

python.find("java") #-1  
index =python.index("java") #출력오류발생
#find함수는 원하는 값이 없을경우 -1을 반환, 반면 index함수는 오류출력
 
python.count("n") #문자열이 몇개인지 출력
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

* 방법3
```py
print("나는 {age}살이며, {color}색을 좋아해요" .format(age=20, color="빨간"))
print("나는 {age}살이며, {color}색을 좋아해요" .format( color="빨간",age=20))
```

* 방법4(V3.6 이상~)
```py
age="20"
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
## 리스트[ ] 
순서를 가지는 객체의 집합
***
```py
subway =["유재석","조세호","박명수"]
subway.append("하하") #배열끝에 아이템 추가
subway.pop() #배열끝에 있는 아이템을 제거
subway.insert(1,"정형돈") #(추가할위치,추가할사항),배열사이에추가
print(subway.count("유재석")) #아이템중복갯수
subway.clear() #배열아이템모두삭제
```

```py
num_list =[5,2,4,3,1]

num_list.sort() #순서정렬 
num_list.reverse()#배열순서뒤집기

```
```py
mix_list =["조세호", 20,True] #다양한 자료형 함께 사용가능

a=[1,"예지",True]
b=[25,False, "하나",3]
a.extend(b)
print(a) #배열확장, [1, '예지', True, 25, False, '하나', 3]
```
## 사전 
***
-key에 대한 중복이 허용되지 않는다
```py
cabinet={3:"유재석", 100:"김태호"}
print(cabinet[3]) #유재석 ,key값이 틀릴경우 출력오류 
print(cabinet.get(3)) #유재석 ,key값이 틀릴경우 none

print(3 in cabinet) #True ,key값포함여부확인
print(5 in cabinet) #False
```
```py
cabinet2={"A-3":"유재석", "B-100":"김태호"} #key값은 문자열로도 만들수있다 
print(cabinet2["A-3"]) #유재석
cabinet2["c-20"]="조세호" #key값 추가하기 
cabinet2["A-3"]="김종국" #key값 변경하기(유제석에서->김종국으로 )
del cabinet2["B-100"] #key값 제거
print(cabinet2.keys()) #key값만 출력
print(cabinet2.values()) #value값만 출력
print(cabinet2.items()) #key과 value값 모두출력
cabinet2.clear() # 모든값제거
```
## tuple(튜플)
***
 -속도가 list보다 빠르다   
 -내용의 변경이나 추가가 불가능하다
```py
menu=("돈까스","치즈까스")
print(menu[0]) #돈까스

name,age,hobby ="김종국",20,"코딩" # 한번에 값을 선언 
print(name,age,hobby) #김종국 20 코딩
```
## set(집합)
***
```py
my_set ={1,2,3,3,3}
print(my_set) #{1,2,3} ->중복안됨,순서없음
```
```py
java ={"유재석","김태호","양세형"}
python =set(["유재석","박명수"])


#교집합(java와 python을 모두 할 수 있는 개발자)
print(java &python)
print(java.intersection(python))

#합집합(java 할 수 있거나 python 할 수 있는 개발자)
print(java | python)
print(java.union(python))

#차집합(java는 할 수 있지만 python은 할줄 모르는 개발자)
print(java-python)
print(java.difference(python))

#추가(python 할 줄 아는 사람이 늘어남)
python.add("김태호")

# 삭제(java를 잊었어요)
java.remove("김태호")
```

## 자료구조의 변경
***
```py
menu ={"커피","우유","주스"}
print(menu,type(menu)) #{'우유', '주스', '커피'} <class 'set'>

menu=list(menu)
print(menu,type(menu)) #['우유', '주스', '커피'] <class 'list'>

menu=tuple(menu)
print(menu,type(menu)) #('우유', '주스', '커피') <class 'tuple'>
```

## if
***
```py
weather=input("오늘날씨는 어때요?") #콘솔창으로 이동(string타입으로 받음)
if weather =="비" or weather =="눈":
    print("우산을 챙기세요")
elif weather =="미세먼지":
    print("미스크를 챙기세요")
else:
    print("준비물 필요 없어요")   
```

## for
***
```py
for waiting_num in range(1,6): #1,2,3,4,5
    print(f"대기번호:{waiting_num}")
```
```py
starbucks =["아이언맨","토르","아이엠 그루트"]
for customer in starbucks:
    print(f"{customer}, 커피가 준비되었습니다")
```
## 한줄for
***

```py
# 출석번호가 1,2,3,4,5 ,앞에 100을 붙이기로함 ->101,102...105

student=[1,2,3,4,5]

print(student) #[1, 2, 3, 4, 5]

student=[i+100 for i in student]
print(student) #[101, 102, 103, 104, 105]
```
```py
#이름을 길이로 변환
students =["iron man","thor","i am groot"]
students=[len(i) for i in students]
print(students)
```
```py
#이름을 대문자러 변환
students =["iron man","thor","i am groot"]
students=[i.upper() for i in students]
print(students)
```


## while
***
```py
customer ="토르"
index=5

while index >=1:
    print(f"{customer},커피가 준비되었습니다 {index} 번 남았어요")
    index-=1
    if index ==0:
        print("커피는 폐기처분되었습니다")

#토르,커피가 준비되었습니다 5 번 남았어요
#토르,커피가 준비되었습니다 4 번 남았어요
#토르,커피가 준비되었습니다 3 번 남았어요
#토르,커피가 준비되었습니다 2 번 남았어요
#토르,커피가 준비되었습니다 1 번 남았어요
#커피는 폐기처분되었습니다
```
```py
customer="토르"
person="unknown"
while person != customer:
    print(f"{customer},커피가 준비되었습니다")
    person =input("이름이 어떻게 되세요?")
#토르,커피가 준비되었습니다
#이름이 어떻게 되세요?
```
## continue 와 break
```py
absent =[2,5] #결석
no_book=[7]
for student in range(1,11): #1,2,3,4,5,6,7,8,9,10
    if student in absent:
        continue #absent가 나오면 바로 print하지않고 다시 for문으로 들어간다
    elif student in no_book:
        print("오늘수업 여기까지.{0}는 교무실로 따라와" .format(student))
        break
    print(f"{student},책을 읽어봐")
```
## 함수
***
```py
def open_account():
    print("새로운 계좌가 생성되었습니다.")

open_account()    #함수는 호출해줘야한다
```
### 💨함수)전달값과 반환값
```py
def deposit(balance,money): #입금
    print(f"입금이 완료되었습니다.  잔액은 {balance+money}원입니다.")
    return balance+money

def withdraw(balance,money): #출금
    if balance >=money: #잔액이 출금보다 많으면
        print(f"출금이 완료되었습니다. 출금요청금액은{money}원이고 잔액은 {balance-money}원입니다")
        return balance-money,money
    else:
        print(f"출금이 완료되지 않았습니다. 잔액은{balance}입니다")  
        return balance 

def widthdraw_night(balance,money): # 저녁에 출금
    commission =100 #수수료 100원
    return commission,money, balance-money-commission #튜플형식으로 return


balance =0 #현재잔액
balance=deposit(balance,3000) # 입금
balance,money=withdraw(balance, 1000) # 출금 
commission,money, balance=widthdraw_night(balance,500)
print(f"저녁시간 수수료 {commission} 원이며,출금금액은{money}원이며, 잔액은 {balance} 원입니다")

# 새로운 계좌가 생성되었습니다.
# 입금이 완료되었습니다.  잔액은 3000원입니다.
# 출금이 완료되었습니다. 출금요청금액은1000원이고 잔액은 2000원입
# 니다
# 수수료 100 원이며,출금금액은500원이며, 잔액은 1400 원입니다
```
### 💨함수)기본값

```py
#같은학교 같은반 같은수업이라고 가정
def profile(name,age=17,main_lang="파이썬"): 
    print(f"이름:{name}\t나이:{age} \t주 사용 언어:{main_lang}")

profile("유재석")
profile("김태호")
#이름:유재석     나이:17         주 사용 언어:파이썬
#이름:김태호     나이:17         주 사용 언어:파이썬

```


## 💙quiz
***

### 🔹램덤 당첨자만들기🔹
```py
from random import *

users=range(1,21) #1부터 20까지의 숫자를 생성 
users=list(users) #type이 range라서 type을 list로 반환필요

shuffle(users) #정렬된 숫자 섞기

winner=sample(users,4)

print(f"--당첨자 발표--\n치킨 당첨자:{winner[0]} \n커피당첨자:{winner[1:]}\n--축하합니다--")
```

### 🔹택시매칭프로그램🔹
당신은 택시 기사님입니다.   
**50명의** 승객과 매칭 기회가 있을 때, 총 탑승 승객 수를 구하는 프로그램을 작성하시오

조건1: 승객별 운행 요소 시간은 **5~50분** 사이의 난수로 정해집니다   
조건2: 당신은 소요 시간 **5~15분** 사이의 승객만 매칭해야 합니다   
(출력문 예제)   
[0] **1번째** 손님 (소요시간 :**15분**)   
[ ] **2번째** 손님 (소요시간 :**50분**)   
[0] **3번째** 손님 (소요시간 :**7분**)   
...   
[ ] 50번째 손님 (소요시간 :**16분**)   

총 탑승 승객: 2분   

```py
from random import *

cnt=0  # 총 탑승 승객수
for i in range(1,51): #1~50이라는 수
    time=randrange(5,51) # 5분~50분 소요시간
    if 5<= time <=15: #5분~15분 이내의 손님(매칭성공),탑승 승객수증가처리
        print(f"[0] {i}번째 손님(소요시간:{time}분)")
        cnt+=1
    else: #매칭 실패한 경우
        print(f"[] {i}번째 손님(소요시간:{time}분)")

print(f"총 탑승승객: {cnt}분")        
```
