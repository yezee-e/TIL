## 자료구조
효과적인 자료의 조직, 관리, 저장   
효율적인 알고리즘을 사용할 수 있게함   
효과적인 자료구조는 실행시간 및 메모리 용량과 같은 자원을 최소화하여 직접 수행   
즉, 내가 원하는 데이터를 좀 더 쉽고 빠르게 꺼내서 쓰기 위해 잘 정리된 형태로 데이터를 정렬하는 방식   
- ex- 잘 정돈된 도서관

## 알고리즘
어떤 믄제를 해결하기 위하여 정해진 절차

## Big-O
알고리즘 성능 측정기(알고리즘이 얼마나 빠르고 효율적으로 동작하는지 확인)   
O(1) < O(logN) < O(N) < O(NlogN) < O(N^2)   

## Bubble sort
* **Big-O는 O(N^2)** -for문을 두번돌림
```py
def bubbleSort(list):
    #크기 =5
    length =len(list)
    for i in range(0,length-1):
        print("")
        print("i:",i)

        for j in range(0,length-1-i):
            print("j:",j)

            if(list[j]>list[j+1]) :
                list[j],list[j+1] = list[j+1], list[j] #앞번호가 뒷번호 보다 크면 둘이 자리바꾸기
list =[5,1,4,2,8]
bubbleSort(list)
print(list)

# i: 0
# j: 0
# j: 1
# j: 2
# j: 3

# i: 1
# j: 0
# j: 1
# j: 2

# i: 2
# j: 0
# j: 1

# i: 3
# j: 0
# [1, 2, 4, 5, 8]
```

## Insert Sort 
* **Big-O는 O(N^2)**  -반복문을 두 번 중첩
```py
def insertSort(list):

    for i in range(1, len(list)): #첫번째 수 부터 비교하지 않기 때문에 0번 부터가 아닌 1부터 시작

        key=list[i]
        j=i-1

        print("key:",key)

        while j >= 0 and key < list[j] :

            list[j+1] =list[j]
            print("list:",list)
            j-=1
            print("list:",list)
            list[j+1] =key
            print("list:",list)
            

list =[12,11,13,5,6]
insertSort(list)

# key: 11
# list: [12, 12, 13, 5, 6]
# list: [12, 12, 13, 5, 6]
# list: [11, 12, 13, 5, 6]
# key: 13
# key: 5
# list: [11, 12, 13, 13, 6]
# list: [11, 12, 13, 13, 6]
# list: [11, 12, 5, 13, 6]
# list: [11, 12, 12, 13, 6]
# list: [11, 12, 12, 13, 6]
# list: [11, 5, 12, 13, 6]
# list: [11, 11, 12, 13, 6]
# list: [11, 11, 12, 13, 6]
# list: [5, 11, 12, 13, 6]
# key: 6
# list: [5, 11, 12, 13, 13]
# list: [5, 11, 12, 13, 13]
# list: [5, 11, 12, 6, 13]
# list: [5, 11, 12, 12, 13]
# list: [5, 11, 12, 12, 13]
# list: [5, 11, 6, 12, 13]
# list: [5, 11, 11, 12, 13]
# list: [5, 11, 11, 12, 13]
# list: [5, 6, 11, 12, 13]
```