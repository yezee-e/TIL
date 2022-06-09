## quiz


### 램덤 당첨자만들기
***
```py
from random import *

users=range(1,21) #1부터 20까지의 숫자를 생성 
users=list(users) #type이 range라서 type을 list로 반환필요

shuffle(users) #정렬된 숫자 섞기

winner=sample(users,4)

print(f"--당첨자 발표--\n치킨 당첨자:{winner[0]} \n커피당첨자:{winner[1:]}\n--축하합니다--")
```

### 택시매칭프로그램
***
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
###  표준체중을 구하는 프로그램을 작성
***
*표준체중: 각 개인의 키에 적당한 체중    

(성별에 따른 공식)   
남자:키(m) x 키(m) x 22   
여자:키(m) x 키(m) x 21   

조건1:표준 체중은 별도의 함수 내에서 계산   
        * 함수명:std_weight   
        * 전달값:키(height), 성별(gender)   
조건2:표준 체중은 소수점 둘째자리까지 표시   

(출력예제)   
키 175cm 남자의 표준 체중은 67.38kg입니다   
```py
def std_weight(height,gender):
    
    if gender =="men":
       return height*height*22
    else:
        return height*height*21

height=160
gender="women"
weight=round(std_weight(height/100,gender),2)
print(f"키 {height}cm {gender}의 표준 체중은 {weight}kg입니다")
```
### 주간 보고서 작성
***
당신의 회사에서는 매주 1회 작성해야하는 보고서가 있습니다
보고서는 항상 아래와 같은 형태로 출력되어야 합니다.

 -x주차 주간보고-
 부서:
 이름:
 업무 요약:

1주차부터 50주차까지의 보고서 파일을 만드는 프로그램을 작성하시오.
조건:파일명은 "1주차.txt","2주차.txt",...와 같이 만듭니다.

```py
for i in range(1,51):
    with open(str(i)+"주차.txt","w",encoding="utf8") as report_file:
         report_file.write(f"-{i}주차 주간보고-")
         report_file.write("\n부서:")
         report_file.write("\n이름:")
         report_file.write("\n업무 요약:")
       
```

### 부동산 프로그램
***
(출력예제)   
총 3대의 매물이 있습니다.   
강남 아파트 매매 10억 2010년   
마포 오피스텔 전세 5억 2007년   
송파 빌라 월세 500/50 2000년   
```py
# [코드]
class House:
    #매물초기화
    def __init__(self,location,house_type,deal_type,price,completion_year):
        self.location=location
        self.house_type=house_type
        self.deal_type=deal_type
        self.price=price
        self.completion_year=completion_year
    

    #매물정보표시
    def show_detail(self):
        print(f"{self.location} {self.house_type} {self.deal_type}{self.price}{self.completion_year}")


home=[]
home1=House("강남","아파트","매매","10억","2010년")
home2=House("마포","오피스텔","전세","5억","2007년")
home3=House("송파","빌라","월세","500/5","2000년")

home.append(home1)
home.append(home2)
home.append(home3)

print(f"총 {len(home)}대의 매물이 있습니다")
for seoul_home in home:
    seoul_home.show_detail()
    
```