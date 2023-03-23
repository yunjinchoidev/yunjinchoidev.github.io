---
title: "[이코테] 1장, 2장"
last_modified_at: 2023-03-07T16:20:02-05:00
categories:
    - ps
tages:
    - aitech
    - nlp
toc: true
toc_sticky: true
toc_label: "목차"
---


# 이코테 1 장

# 개요
## 시간 복잡도
알고리즘을 위해 필요한 연산의 횟수
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