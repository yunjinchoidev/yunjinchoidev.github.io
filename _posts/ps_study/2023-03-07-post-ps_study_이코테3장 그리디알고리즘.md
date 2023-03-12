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





<br>
<br>
<br>
<br>




# 내가 사랑한 그리디 알고리즘 27 문제 [링크](https://github.com/tony9402/baekjoon/tree/main/greedy)

[백준 문제집](https://www.acmicpc.net/workbook/view/6833)

|          순번          |        추천 문제         |        문제 번호         |        문제 이름         |         난이도          |        풀이 링크         |
| :-----: | :-----: | :-----: | :-----: | :-----: | :-----: |
| 00 |  ❌  | <a href="https://www.acmicpc.net/problem/14916" target="_blank">14916</a> | <a href="https://www.acmicpc.net/problem/14916" target="_blank">거스름돈</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/6.svg"/> | <a href="./../solution/greedy/14916">바로가기</a> |
| 01 |  ❌  | <a href="https://www.acmicpc.net/problem/1343" target="_blank">1343</a> | <a href="https://www.acmicpc.net/problem/1343" target="_blank">폴리오미노</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/6.svg"/> |                      |
| 02 |  ❌  | <a href="https://www.acmicpc.net/problem/2217" target="_blank">2217</a> | <a href="https://www.acmicpc.net/problem/2217" target="_blank">로프</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/7.svg"/> | <a href="./../solution/greedy/2217">바로가기</a> |
| 03 |  ❌  | <a href="https://www.acmicpc.net/problem/1758" target="_blank">1758</a> | <a href="https://www.acmicpc.net/problem/1758" target="_blank">알바생 강호</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/7.svg"/> | <a href="./../solution/greedy/1758">바로가기</a> |
| 04 |  ❌  | <a href="https://www.acmicpc.net/problem/11399" target="_blank">11399</a> | <a href="https://www.acmicpc.net/problem/11399" target="_blank">ATM</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/7.svg"/> | <a href="./../solution/greedy/11399">바로가기</a> |
| 05 |  ❌  | <a href="https://www.acmicpc.net/problem/11508" target="_blank">11508</a> | <a href="https://www.acmicpc.net/problem/11508" target="_blank">2+1 세일</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/7.svg"/> | <a href="./../solution/greedy/11508">바로가기</a> |
| 06 |  ❌  | <a href="https://www.acmicpc.net/problem/11047" target="_blank">11047</a> | <a href="https://www.acmicpc.net/problem/11047" target="_blank">동전 0</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/7.svg"/> |                      |
| 07 |  ❌  | <a href="https://www.acmicpc.net/problem/13305" target="_blank">13305</a> | <a href="https://www.acmicpc.net/problem/13305" target="_blank">주유소</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/8.svg"/> | <a href="./../solution/greedy/13305">바로가기</a> |
| 08 |  ❌  | <a href="https://www.acmicpc.net/problem/20115" target="_blank">20115</a> | <a href="https://www.acmicpc.net/problem/20115" target="_blank">에너지 드링크</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/8.svg"/> | <a href="./../solution/greedy/20115">바로가기</a> |
| 09 |  ❌  | <a href="https://www.acmicpc.net/problem/20300" target="_blank">20300</a> | <a href="https://www.acmicpc.net/problem/20300" target="_blank">서강근육맨</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/8.svg"/> | <a href="./../solution/greedy/20300">바로가기</a> |
| 10 |  ❌  | <a href="https://www.acmicpc.net/problem/20365" target="_blank">20365</a> | <a href="https://www.acmicpc.net/problem/20365" target="_blank">블로그2</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/8.svg"/> | <a href="./../solution/greedy/20365">바로가기</a> |
| 11 |  ❌  | <a href="https://www.acmicpc.net/problem/1541" target="_blank">1541</a> | <a href="https://www.acmicpc.net/problem/1541" target="_blank">잃어버린 괄호</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/9.svg"/> | <a href="./../solution/greedy/1541">바로가기</a> |
| 12 |  ❌  | <a href="https://www.acmicpc.net/problem/16953" target="_blank">16953</a> | <a href="https://www.acmicpc.net/problem/16953" target="_blank">A → B</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/9.svg"/> |                      |
| 13 |  ❌  | <a href="https://www.acmicpc.net/problem/21314" target="_blank">21314</a> | <a href="https://www.acmicpc.net/problem/21314" target="_blank">민겸 수</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/9.svg"/> |                      |
| 14 |  ❌  | <a href="https://www.acmicpc.net/problem/1931" target="_blank">1931</a> | <a href="https://www.acmicpc.net/problem/1931" target="_blank">회의실 배정</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/10.svg"/> | <a href="./../solution/greedy/1931">바로가기</a> |
| 15 |  ❌  | <a href="https://www.acmicpc.net/problem/11000" target="_blank">11000</a> | <a href="https://www.acmicpc.net/problem/11000" target="_blank">강의실 배정</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/11.svg"/> | <a href="./../solution/greedy/11000">바로가기</a> |
| 16 |  ❌  | <a href="https://www.acmicpc.net/problem/13164" target="_blank">13164</a> | <a href="https://www.acmicpc.net/problem/13164" target="_blank">행복 유치원</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/11.svg"/> | <a href="./../solution/greedy/13164">바로가기</a> |
| 17 |  ❌  | <a href="https://www.acmicpc.net/problem/19598" target="_blank">19598</a> | <a href="https://www.acmicpc.net/problem/19598" target="_blank">최소 회의실 개수</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/11.svg"/> | <a href="./../solution/greedy/19598">바로가기</a> |
| 18 |  ❌  | <a href="https://www.acmicpc.net/problem/2212" target="_blank">2212</a> | <a href="https://www.acmicpc.net/problem/2212" target="_blank">센서</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/11.svg"/> | <a href="./../solution/greedy/2212">바로가기</a> |
| 19 |  ❌  | <a href="https://www.acmicpc.net/problem/1092" target="_blank">1092</a> | <a href="https://www.acmicpc.net/problem/1092" target="_blank">배</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/11.svg"/> | <a href="./../solution/greedy/1092">바로가기</a> |
| 20 |  ❌  | <a href="https://www.acmicpc.net/problem/21758" target="_blank">21758</a> | <a href="https://www.acmicpc.net/problem/21758" target="_blank">꿀 따기</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/11.svg"/> | <a href="./../solution/greedy/21758">바로가기</a> |
| 21 |  ❌  | <a href="https://www.acmicpc.net/problem/2141" target="_blank">2141</a> | <a href="https://www.acmicpc.net/problem/2141" target="_blank">우체국</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/12.svg"/> | <a href="./../solution/greedy/2141">바로가기</a> |
| 22 |  ❌  | <a href="https://www.acmicpc.net/problem/13975" target="_blank">13975</a> | <a href="https://www.acmicpc.net/problem/13975" target="_blank">파일 합치기 3</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/12.svg"/> |                      |
| 23 |  ❌  | <a href="https://www.acmicpc.net/problem/1715" target="_blank">1715</a> | <a href="https://www.acmicpc.net/problem/1715" target="_blank">카드 정렬하기</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/12.svg"/> |                      |
| 24 |  ❌  | <a href="https://www.acmicpc.net/problem/2285" target="_blank">2285</a> | <a href="https://www.acmicpc.net/problem/2285" target="_blank">우체국</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/12.svg"/> |                      |
| 25 |  ❌  | <a href="https://www.acmicpc.net/problem/2812" target="_blank">2812</a> | <a href="https://www.acmicpc.net/problem/2812" target="_blank">크게 만들기</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/13.svg"/> | <a href="./../solution/greedy/2812">바로가기</a> |
| 26 |  ❌  | <a href="https://www.acmicpc.net/problem/8980" target="_blank">8980</a> | <a href="https://www.acmicpc.net/problem/8980" target="_blank">택배</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/14.svg"/> |                      |
| 27 |  ❌  | <a href="https://www.acmicpc.net/problem/21313" target="_blank">21313</a> | <a href="https://www.acmicpc.net/problem/21313" target="_blank">문어</a> | <img height="25px" width="25px" src="https://static.solved.ac/tier_small/4.svg"/> |                      |
