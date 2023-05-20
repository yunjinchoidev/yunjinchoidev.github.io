---
title: "[이코테] 1장, 2장"
last_modified_at: 2023-03-07T16:20:02-05:00
categories:
    - a01_study
tages:
    - aitech
    - nlp
toc: true
toc_sticky: true
toc_label: "목차"
---

![paper.png](../../../image/ps.png)


# 이코테 1 장

## 시간 복잡도
알고리즘을 위해 필요한 연산의 횟수

시간 복잡도는 알고리즘이 문제를 해결하는 데 걸리는 시간을 측정한 것입니다. 
일반적으로 입력 크기의 함수로 표현되며 알고리즘이 문제를 해결하는 데 필요한 기본 작업(또는 단계)의 수를 나타냅니다.

알고리즘의 시간 복잡도는 특정 문제를 해결하기 위해 서로 다른 알고리즘 중에서 선택할 때 고려해야 할 중요한 요소입니다. 
시간 복잡도가 낮은 알고리즘은 일반적으로 시간 복잡도가 높은 알고리즘보다 더 효율적이고 빠릅니다.

시간 복잡도를 표현하는 방법에는 여러 가지가 있지만 가장 일반적인 표기법은 "big O" 표기법입니다. 
Big O 표기법은 입력 크기가 증가함에 따라 기본 작업 수의 증가율에 대한 상한선을 제공합니다. 
예를 들어, 알고리즘의 시간 복잡도가 O(n)인 경우 기본 연산의 수가 입력 크기에 따라 선형적으로 증가한다는 의미입니다.

시간 복잡도를 표현하는 데 사용되는 다른 일반적인 표기법에는 연산 수의 증가율에 대한 하한을 제공하는 빅 오메가(Ω) 표기법과 증가율에 엄격한 한계를 제공하는 빅 세타(Θ) 표기법이 포함됩니다.

시간 복잡성을 이해하는 것은 알고리즘 설계 및 분석에서 중요합니다. 큰 입력에 대해 제대로 확장되지 않을 수 있는 비효율적인 알고리즘을 식별하고 피하는 데 도움이 되기 때문입니다.

## 공간 복잡도
알고리즘을 위해 필요한 메모리의 양

# 빅오 표기법

|빅오 표기법| 명칭|
|:---:|:---:|:---:|:---:|
|O(1)|상수|
|O(logN)|로그 시간|
|O(N)|선형 시간|
|O(NlonN)|로그 선형 시간|
|O(N^2)|이차 시간|
|O(N^3)|삼차 시간|
|O(2^3)|지수 시간|


## 상수 시간 복잡도(O(1))
이것은 입력 크기에 관계없이 실행하는 데 일정한 시간이 걸리는 알고리즘을 말합니다.

```
def get_first_element(lst):
    return lst[0]
```


## 선형 시간 복잡도(O(n))
이것은 입력 크기에 비례하는 시간이 걸리는 알고리즘을 말합니다.
```
def find_element(lst, x):
    for elem in lst:
        if elem == x:
            return True
    return False

```


## 2차 시간 복잡도(O(n^2))
이것은 입력 크기의 제곱에 비례하는 시간이 걸리는 알고리즘을 말합니다.
```
def find_duplicates(lst):
    duplicates = []
    for i in range(len(lst)):
        for j in range(i+1, len(lst)):
            if lst[i] == lst[j] and lst[i] not in duplicates:
                duplicates.append(lst[i])
    return duplicates
```

## 로그 시간 복잡도(O(log n))
이것은 입력 크기의 로그에 비례하는 시간이 걸리는 알고리즘을 나타냅니다.

```
def binary_search(lst, x):
    low, high = 0, len(lst) - 1
    while low <= high:
        mid = (low + high) // 2
        if lst[mid] < x:
            low = mid + 1
        elif lst[mid] > x:
            high = mid - 1
        else:
            return mid
    return -1

```









## 수행 시간 체크
```
import time
start_time = time.time()

소스코드

end_time = time.time()
print("time ", end_time - start_time)



```

<br><br><br><br>


# 자주 나오는 문제
기업 코테에서 그렇게 어려운 문제는 나오지 않습니다. 골드 3 까지 안정적으로 풀면 합격할 수 있습니다.
너무 어려운 알고리즘을 공부할 필요도 없습니다.

## 구현
## 그리디
## 정렬
## DFS, BFS
## 다이나믹 프로그래밍