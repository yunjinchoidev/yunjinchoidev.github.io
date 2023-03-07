---
title: "Post: Python 정리"
last_modified_at: 2023-03-07T16:20:02-05:00
categories:
    - aitech
tages:
    - aitech
    - nlp
---

---
jupyter:
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
  language_info:
    codemirror_mode:
      name: ipython
      version: 3
    file_extension: .py
    mimetype: text/x-python
    name: python
    nbconvert_exporter: python
    pygments_lexer: ipython3
    version: 3.9.16
  nbformat: 4
  nbformat_minor: 0
---

# boostcamp_AITech_5th
![image](../../../image/aitech.png)

---
jupyter:
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
  language_info:
    codemirror_mode:
      name: ipython
      version: 3
    file_extension: .py
    mimetype: text/x-python
    name: python
    nbconvert_exporter: python
    pygments_lexer: ipython3
    version: 3.9.16
  nbformat: 4
  nbformat_minor: 0
---

::: {.cell .markdown collapsed="false"}
# \[파이썬\] 강의 노트

# \[목차\]

> ### 개요
>
> ### 기초 문법
>
> ### 객체 지향
>
> ### 파이썬으로 데이터 다루기
>
> ### Numpy
>
> ### Pandas

------------------------------------------------------------------------

# 개요

-   운영체제
    -   윈도우, 맥, 리눅스
-   파일시스템
    -   root 디렉토리에서 시작하는 트리 구조
    -   디렉토리, 파일
    -   절대경로, 상대경로
    -   
-   터미널
    -   CLI
-   파이썬
    -   플랫폼 독립적
    -   인터프리터 언어
    -   객체 지향
    -   동적 타이핑 언어
-   컴파일러 VS 인터프리터
    -   컴파일러
    -   인터프리터
-   Why Python ?
    -   Life is too short, You need Python
-   실행환경
    -   주피터 노트북
    -   코랩
    -   Visual Studio Code
:::

::: {.cell .markdown collapsed="false"}
# 기초 문법 {#기초-문법}

-   Variable
    -   변수는 메모리 주소를 가지고 있고
    -   변수에 들어가는 값은 메모리 주소에 할당된다.
    -   패킹, 언패킹
        -   t = \[1, 2, 3\]
        -   a, b, c = t
-   Function and Console I/O
    -   함수적 개념이 대단히 중요하다.
    -   Function
        -   어떤 일을 수행하는 코드의 덩어리
:::

::: {.cell .markdown collapsed="false"}
:::

::: {.cell .code execution_count="4" collapsed="false"}
``` python
# 함수 예시
def cal_rec(x, y):
    return x*y
area = cal_rec(1,2)
print(area)
```

::: {.output .stream .stdout}
    2
:::
:::

::: {.cell .code execution_count="5" collapsed="false"}
``` python
# 입력 받기 Console I/O
x = input()
print(x)
```

::: {.output .stream .stdout}
    10
:::
:::

::: {.cell .code execution_count="19" collapsed="false"}
``` python
# 포맷에 따른 출력

# (1) % string
print('%s %s' % ('x', 'u'))
print('{} {}'.format('x', 'y'))
print('%d %d' % (1, 2))
print('{} {}'.format(1, 2))

# (2) format
print("I eat %d appe %s" % (3, 'G'))
print("product %10s" % "GGG")
print("gogo {0} {1} {2}".format(1, 2, 3))


# (3) fstring
# 가장 많이 쓴다.
name = "yunjin"
age = 1111
print(f"Hello, {name:*>20} {age}")




# padding 방법 참고

```

::: {.output .stream .stdout}
    x u
    x y
    1 2
    1 2
    I eat 3 appe G
    product        GGG
    gogo 1 2 3
    Hello, **************yunjin 1111
:::
:::

::: {.cell .markdown collapsed="false"}
-   Conditionals & Loops
    -   조건문과 반복문
        -   if, for
    -   논리적인 생각의 기본
-   String & advanced function concept
    -   데이터 타입은 메모리의 효율적 활용을 위해 매우 중요합니다.
-   Call By Value \|\| Call By Reference
    -   Call By Value
        -   값을 넘김
    -   Call By Reference
        -   메모리 주소를 넘김
        -   포인터 개념
-   파이썬은 call by Object References
:::

::: {.cell .code execution_count="1" collapsed="false"}
``` python
def spam(eggs):
    eggs.append(1)
    eggs.append(5)
    eggs = [2, 3]
    print(eggs)

ham = [0]
spam(ham)
print(ham)
```

::: {.output .stream .stdout}
    [2, 3]
    [0, 1, 5]
:::
:::

::: {.cell .markdown collapsed="false"}
-   Scoping Rule
    -   지역 변수 local variable
    -   전역 변수 Global variable
-   재귀 함수
    -   재귀 함수를 잘 활용해야 진정한 고수다!
-   functino type hints
    -   리턴 타입을 알 기 쉽게 해주는 것
    -   안전성 보장
-   docstring
    -   함수의 스펙을 사전에 작성하는 것
-   코드는 하나의 보고서다.
    -   잘 해야지 !
    -   코딩 컨벤션을 잘 지키자. (구글 컨벤션)
    -   일관성을 지켜야지.
    -   [링크](https://yosseulsin-job.github.io/Google-Python-Style-Guide-kor/)
    -   conda install -c anaconda flake8
        -   이걸로 체크하라.
    -   conda install black
        -   이것은 수정해줌 (표준임)
:::

::: {.cell .code execution_count="1" collapsed="false"}
``` python
def do(name: str) -> str:
    """_summary_
    이것이 docstring 다.

    Args:
        name (str): _description_

    Returns:
        str: _description_
    """    
    return f"GGG {name}"
gg = do("qq")
print(gg)
```

::: {.output .stream .stdout}
    GGG qq
:::
:::

::: {.cell .markdown}
## Python Data Structure

-   stack
    -   LIFO
-   queue
    -   FIFO
-   tuple, set
-   dictionary
-   Collection
:::

::: {.cell .markdown}
# Pythonic code

-   파이썬 다운 스타일
    -   많은 딥러닝 논문, 엔지니어가 파이쏘닉 코드를 쓰고 있기 때문에
        인지하고 있어야 한다.
-   split, join
-   list comprehension
-   enumerate, zip
-   lambda
-   map
-   reduce
    -   대용량의 데이터를 다룰 때
    -   리스트에 특정 람다함수를 지속적으로 적용시켜줄 때
-   generator (주의 !! )
    -   실제로 값을 안 들어놓고 실제 호출했을 때 호출
    -   메모리를 절약할 수 있음.
    -   파일 데이터, 큰 데이터를 처리할 때 사용 하면 된다.
-   asterisk
-   fucntion parameter
    -   keyword arguments
    -   Default arguments
    -   variable arguments
        -   asterist = \* 기호

        -   -   

        -   딕트만 받기 -\> \*\*

        -   unpacking
:::

::: {.cell .code execution_count="9"}
``` python
result = [i for i in range(10)]
print(result)
result2 = [i+j for i in 'to' for j in 'one']
print(result2)

#zip
k = ['go', 'ho', 'no']
n = ['ba', 'qa', 'to']
uu = [[a,b] for a, b in zip(k, n)]
print(uu)

# reduce
from functools import reduce
reduce(lambda x, y:x+y, [1,2,3,4,5])


# asterisk
def asterisk_test(a, b, *args):
    return a+b+sum(args)
print(asterisk_test(1,2,3,45))

def asterisk_test2(**kwards):
    print(kwards)

asterisk_test2(a=3, b='gg', c='ggg')
```

::: {.output .stream .stdout}
    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    ['to', 'tn', 'te', 'oo', 'on', 'oe']
    [['go', 'ba'], ['ho', 'qa'], ['no', 'to']]
    51
    {'a': 3, 'b': 'gg', 'c': 'ggg'}
:::
:::

::: {.cell .markdown}
# 객체 지향 {#객체-지향}

-   Object-Oriented Programming

-   객체

    -   속성 `Variable`
    -   행동 `Method`

-   **init** : 초기화 함수

-   매직 메서드 [링크](https://tibetsandfox.tistory.com/42)

-   실전 클래스를 만들어서 연습해보라.

-   상속 (Inheritance)

    -   super() 부모 객체 불러오기

-   다형성 (Polymorphism)

    -   내부로직을 다르게 구현하기..
    -   `NotImplementedError()`

-   가시성 (Visibility)

    -   심판이 축구 선수의 가족을 알아야 합니까?
    -   인터페이스만 알아서 쓰시라.
    -   private 변수로 선언해서 타객체가 접근하지 못하도록 합니다.
    -   데코레이터 : \@property

-   일급객체 (first-class object)

    -   변수나 데이터 구조에 할당이 가능한 객체
    -   파이썬 함수는 일급함수.

-   inner function

    -   closures : inner function 을 return 을 반환

-   decorator

    -   함수를 어노테이션으로 써버리는 것.
:::

::: {.cell .markdown}
# 모듈

-   남이 만든 것을 가져다 쓰기 By Module
-   조각을 모아 프로그램을 만든다.

# 가상환경

-   pip
-   conda
    -   conda install \~
    -   conda create -n \'\'
    -   conda activate \~\~

# 오픈소스

-   matplotlib
-   tqdm
:::

::: {.cell .code execution_count="2"}
``` python
import matplotlib.pyplot as plt

plt.plot([1,2,3,4])
plt.ylabel('some numbers')
plt.show()


# 반복문에서 실행 바를 보여주기 
from tqdm import tqdm
import time

for i in tqdm(range(100000)):
    if i % 1000 == 0:
        time.sleep(1)
```

::: {.output .display_data}
![](vertopal_1fb2eb6261c4413e91a100c67cd2e458/4babb087123953cd4985ad474581b3954675c63e.png)
:::
:::

::: {.cell .markdown}
# 데이터 다루기

## Exception

-   예외처리를 잘 하면 프로그램은 안전하게 실행할 수 있다.
-   전체 익셉션을 잡으면 추적이 어렵다. (좋은 코드가 아니다.)
-   try, except, finally
-   

## File

-   Binary 파일
-   Text 파일
-   `open` 키워드를 사용해서 파일 읽는다.
    -   r : 읽기
    -   w : 쓰기
    -   a : 추가

## Log Handling
:::

::: {.cell .code execution_count="12"}
``` python
f = open("test.txt", "r")
content = f.read()
print(content)
f.close()

with open("test.txt", "r") as my_file:
    cc = my_file.read()
    print(type(cc), cc)

ff = open("gogo.txt", "w", encoding="utf8")
for i in range(1, 11):
    data = "GG" + str(i) +"\n"
    ff.write(data)
ff.close()

```

::: {.output .stream .stdout}
    ddddfasdfa
    <class 'str'> ddddfasdfa
:::
:::

::: {.cell .markdown}
Picle

-   객체를 임시로 저장
-   딥러닝에서 사용 되는 원리 (미분값보관)

## Loggin Handle

-   로깅 데이터를 추적하는 것은 굉장한 이슈
    -   딥러닝 학습 중 필요한 로깅을 슬랙, 카카오톡, 라인으로 발송
        해준다.
-   게임에서 핵을 어떻게 잡는가 ?
-   import logging
-   loggging.debug
-   loggging.warn
-   debug \> INFO \> warnning \> error \> critical
-   logger.setLevel(loggin.INFO)
-   \<\> (야믈을 쓸꺼냐, cli를 쓸꺼냐.)
    -   cofigparser
    -   argpaser
        -   command line option
:::

::: {.cell .markdown}
:::

::: {.cell .markdown}
# 데이터 타입 (CSV, 웹, XML, JSON)

------------------------------------------------------------------------

### CSV

### 웹

### XML

### JSON

------------------------------------------------------------------------

### 정규식

-   복잡한 문자열 패턴을 정의하는 문자 표현 공식
-   파이썬
    -   import re

------------------------------------------------------------------------

## \### beautifulsoup {#-beautifulsoup}
:::

::: {.cell .markdown}
# Numpy {#numpy}

-   dl 에 있어서 가장 기본적인 모듈. 아주 잘 다뤄야 한다.
-   선형대수학
-   행렬과 텐서를 어떻게 넘파이로 표현할 것인가?
-   import numpy as np
-   conda install numpy
-   numpy 는 c 로 구현 되어 있어서 성능 이점
-   ndarray
    -   np.array(\[1,2,3,4\], float)
-   rank
    -   scalar
    -   vector
    -   matrix
    -   3-tensor
    -   n-tensor
-   np.reshape(m,n)
    -   np.reshape(-1,m)
-   np.flatten()
-   np.arrang(n, m, t)
-   np.zeros
-   np.ones()
-   np.empty()
    -   does\'nt memory initialization
-   np.ones_like()
-   np.identity(n=3)
-   np.diag()
-   np.random.uniform()
-   test_array.sum(axis=n)
-   test_array.std(axis=n)
-   test_array.mean(axis=n)
-   np.vstack()
-   np.hstack()
-   test_array.dot(test_array2)
-   test_array.T
-   test_array.transpose()
-   broadcasting
-   np.where
-   np.all
-   np.any
-   np.argmax
-   np.argmin
-   boolean index
-   fancy index
-   loadtxt & savetxt
    -   np.loadtxt
    -   np.savetxt

## 참고

-   %timeit 를 앞에 붙이면 시간 계산 해줌
    -   numpy \> list comporehension \> loop
    -   넘파이의 성능 이점
:::

::: {.cell .markdown}
# Pandas {#pandas}

-   구조화된 데이터 처리 도구
-   conda install pandas
-   import pandas as np
-   pd.read_csv
-   DataFrame, Series
-   df.head()
-   df.head().T
-   conda install \--y -c anaconda xlrd
-   df.loc
-   df.iloc
-   df.index
-   df.reset_index
-   df.drop(1, inplace=True)
-   df.add(x, fill_value=0)
-   lambda
-   map
-   apply
-   df.describe()
-   df.unique
-   df.sum(axis=1)
-   df.corr
-   df.innull()

## Pandas 연산

-   groupby
-   groupby - transform
    -   그룹별로 특정 연산 (Ex. 정규화)
-   groupby - filter
-   pivot_table
-   joint method
    -   merge
-   database connection
    -   db 연결
    -   import sqlite3
-   xls persistence
    -   엑셀을 피클형태로 하는걸 추천

## 참고 {#참고}

-   가장 좋은 것은 배운 수학/통계적 지식을 실제 데이터에 적용해보는 것.

## 추천

-   판다스로 실제 데이터를 다루는 연습을 하시라.
-   캐글 하자 \~
:::
