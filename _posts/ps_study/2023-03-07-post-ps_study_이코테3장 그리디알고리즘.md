---
title: "Post: 이코테 3장(그리디 알고리즘)"
last_modified_at: 2023-03-07T16:20:02-05:00
categories:
    - ps_study
tages:
    - aitech
    - nlp
toc: true
toc_sticky: true
toc_label: "목차"
---


# 그리디 알고리즘

자, 그리디 알고리즘을 공부합시다. 
그리디 알고리즘은 지금 당장 최적인 답을 선택하는 과정을 반복하여 결과를 도출하는 알고리즘을 말합니다.


## 큰수의 법칙 

```
N, M, K = map(int, input().split())
numbers = list(map(int, input().split()))

# N : 주어지는 수의 개수
# M : 몇 개의 수자를 모을 것인가
# K : k 개 초과 불가

numbers.sort(reverse=True)

check = 0
loop = 0
r = []
while len(r) != M:
    check += 1
    r.append(numbers[loop])

    if loop == 1:
        loop = 0
        continue

    if check % K == 0:
        check = 0
        loop = 1


# print(numbers)
# print(r)
print(sum(r))

```

## 숫자 카드게임

```
N, M = map(int, input().split())

arry = [list(map(int, input().split())) for n in range(N)]

r = []
for idx, value in enumerate(arry):
    r.append([idx, min(value)])

r.sort(key=lambda x:-x[1])

print(r[0][1])
```

## 1이 될 때까지

```
N, K = map(int, input().split())

dp = [0 for i in range(N + 1)]
dp[1] = 1
if K == 2:
    dp[2] = 1
else:
    dp[2] = 2

dp[K] = 1

for i in range(3, N + 1):
    dp[i] = min(dp[i - 1] + 1, dp[int(i/N)] + 1)

print(dp[N])
```



<br>
<br>
<br>
<br>

<br>
<br>
<br>
<br>



