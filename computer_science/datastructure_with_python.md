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
* **Big-O는 O(N^2)** -반복문이 중첩이기 때문
* 옆에 있는 원소와 비교해서 정렬해주는 알고리즘입니다. 거품이 비비듯이 움직임
* 오른쪽에 있는 애가, 왼쪽에 있는 애보다 작으면, 위치를 바꿔줍니다. 

```py
def bubbleSort(list):
    # 리스트의 길이=5
    length =len(list)

    #리스트의 마지막 것은 비교할 것이 뒤에 없기 때문에 -1이 붙음
    for i in range(0,length-1):
       
        #위의 반복문이 한번 실행되면
        #마지막에 가장 큰 값이 들어감
        #length-1-i로 해줘서 마지막 값을 제외
        for j in range(0,length-1-i):
            print("j:",j)

            #앞번호가 뒷번호 보다 크면 둘이 자리바꾸기(스왑)
            if(list[j]>list[j+1]) :
                #스왑하는 부분
                list[j],list[j+1] = list[j+1], list[j] 
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
* **Big-O는  O(n) 또는 O(N^2)**  
* bubble sort 같은 경우에, 왼쪽에 있는 애를 오른쪽으로 계속 미는 느낌이었다면 
  insert sort 같은 경우에는 오른쪽애 있는 애를 왼쪽으로 민다는 느낌

```py
def insertSort(list):

    for i in range(1, len(list)): #첫번째 수 부터 비교하지 않기 때문에 0번 부터가 아닌 1부터 시작

        #key값 정하기
        key=list[i]

        #바로 앞의 비교할 값을 위해 j를 설정
        j=i-1

        #만약 리스트 앞에 값이 있고
        #앞의 값이 key값 보다 크면
        while j >= 0 and key < list[j] :

            #한칸씩 밀어줌 
            list[j+1] =list[j]
          
            j-=1
           
           #key가 들어갈 위칭 key값을 위치 
            list[j+1] =key
         
            

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

## Selection Sort
* **Big-O는** (n-1) + (n-2) + .... + 2 + 1 => n(n-1)/2 즉,O(n2) 
* 골라서 정렬
* 왼쪽부터, 리스트에 있는 가장 작은 애랑 순서를 바꿈
```py
def selectionSort(list):

    for i in range(len(list)-1):
    
        #가장 작은 값의 위치
        min_index=i

        #리스트에 있는 애들을 하나하나 보면서 가장 작은 값을 찾아준다
        for j in range(i+1, len(list)):

            if list[min_index] > list[j]:
                min_index=j

            #swap
        list[i],list[min_index] =list[min_index], list[i]
         

list =[64,25,12,22,11]
selectionSort(list)
print(list)
```

## Merge Sort
* **Big-O는**  O(N logN) - 분할하는 과정은  O(log N)이고 합쳐주는 과정은 O(N)
*  모든 것을 다 나누고나서 합치는것이 아니라, 나누는 중간에 합칩
```py
def mergeSort(list):
    #완전히 다 쪼개질 때 까지 돌리기
    if len(list)>1:

        #중간을 기준으로 쪼개기
        mid =len(list) //2

        left=list[:mid]
        right=list[mid:]

        #왼쪽, 오른쪽 부분 쪼개기
        mergeSort(left)
        mergeSort(right)

        #합치는 과정
        i=0
        j=0
        k=0

        #일단 임시로 정렬
        while i<len(left) and j <len(right):
            if left[i]<right[j]:
                list[k] =left[i]
                i+=1
            else:
                list[k] = right[j]
                j+=1
            k +=1

        while i < len(left):
            list[k] =left[i]
            i +=1
            k +=1
            
        while j < len(right):
            list[k] =right[j]
            j +=1
            k +=1
            
        print(list)
        print("")

list =[38,27,43,3,9,82,10]
mergeSort(list)
```

## Quick Sort
*  pivot이라는 좀 특이한 방식을 사용하고
*  **시간복잡도**가 n log n ~ n^2 입니다.
```py

# pivot을 기준으로 쪼갠다

def zzogaeggi(list, low, high):

    #pivot
    pivot = list[high]

    #i는 pivot을 기주으로 list를 정렬
    i =(low-1)

    #j를 통해 list를 하나씩 훑으면서
    for j in range(low,high) :

        #i 값을 변경해준다
        #pivot보다 작은 애를 왼쪽으로 정렬

        if list[j] <pivot :
            i=i+1
            #swap
            list[i],list[j] =list[j],list[i]

    #pivot이 들어갈 위치로 swap
    list[i+1], list[high] =list[high] ,list[i+1]
    return i+1

def quickSort(list, low, high):

    #피봇이 알맞은 위치에 있어서 
    #qicksort를 실행해줘도 되는지 확인하는 부분
    if low<high :

       #pivot값을 기준으로 쪼개기
       pivot_position =zzogaeggi(list,low,high)

       #왼쪽 오른쪽 쪼개서 sorting
       quickSort(list,low,pivot_position-1)
       quickSort(list,pivot_position+1,high)


list =[10,80,90,40,50,70]
n =len(list)
quickSort(list,0,n-1)
print(list)
```

## Heap Sort
* * **Big-O는** O(NlogN)
* 최대값 및 최소값을 찾아내기 위해 고안된 완전 이진트리 형태의 자료구조
* 트리 같은 형태로 자료 쌓아놓고, 최대값이나 최소값 빨리 찾는 것

```py
#heapify 동작
def heapify(list, n,i):
    #루트값, 왼쪽값, 오른쪽
    root_largest =i
    left =2*i+1
    right =2*i+2

    #왼쪽 애가 존재하고
    #왼쪽 애가 루트보다 더 클때
    if left < n and list[i]<list[left]:
    
        root_largest =left

    #오른쪽 애가 존재하고
    #오른쪽 애가 루트보다 더 클때
    if right < n and list[root_largest] <list[right]:

        root_largest = right

        
    #왼쪽이나 오른쪽 자식들과 바꿔줘야 할 위치를 찾았을때
    if root_largest !=i :

        #찾아낸 값이랑 swap하고
        list[i],list[root_largest] =list[root_largest], list[i]

        #다시 heapify 실행
        heapify(list, n, root_largest)

def heapSort(list):

    n= len(list)

    #heap의 형태로 데이터를 정렬하기

    for i in range(n, -1,-1):

        heapify(list, n, i)

    #root에 있는 애와, 마지막에 있는 애를 바꿔서 정렬해주고 바뀐 애를 기준으로 다시 heapify 실행

    for i in range(n -1, 0 ,-1):
        list[i],list[0] = list[0],list[i]
        heapify(list, i,0)

list=[4,10,3,5,1]
heapSort(list)
n=len(list)
print("result:",list)
```