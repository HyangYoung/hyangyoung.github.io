---
title: "Big O Shorthands"
excerpt: "Algorithm study week2 - Time complexity"

categories:
  - Algorithm
tags:
  - Algorithm, time complexity, Big o

permalink: categories/algorithm/BigO/

toc: true
toc_sticky: true

date: 2023-02-19
last_modified_at: 2023-02-19
---

## 🦥 Big O Shorthands

1. Recursion 이해하고 ↔ for/while loop로 전환 하기
    1. 장/단점은 무엇일까요?
    2. 고민해볼 점? 그렇다면 언제 recursion을 사용하면 좋을지
2. Time complexity(시간복잡도) / space complexity(공간복잡도)를 이해하기

   O(1) O(logn) O(nlogn) O(n^2) case 이해하기

3. Theta / Omega 는 또 뭘까요? (이런게 있다 정도는 아시면 나쁘지 않아요)

재귀란?
재귀는 자기가신을 호출하는 절차
A process (a function in our case) that calls itself.
1. it's everywhere
- JSON.parse/ JSON.stringify (재귀함수의 종류)

The call stack <-> Recurssion

Base Case: The condition whe the recursion stop
Different Input
