---
layout: post
title:  "[프로그래머스] 소수 찾기"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
---

## 완전탐색 - 소수 찾기

* 문제 링크 : [소수 찾기](https://programmers.co.kr/learn/courses/30/lessons/42839)

사용 언어 : Python3


소수 찾는 것 까지 완탐으로 풀어버리면 시간 초과가 날 것 같아서 제곱근까지 돌려보는 것으로 함. 파이썬은 permutation을 쓰면 금방 끝난다.


```python
import math
import itertools

def solution(numbers):
    answer = 0
    
    numbers = list(numbers)
    numList = []
    for i in range(1, len(numbers)+1) : 
        for num in itertools.permutations(numbers, i):
            temp = ''
            for j in num:
                temp += j
            numList.append(int(temp))
    numList = list(set(numList))
    
    for i in numList :
        count = 0
        for j in range(2, math.ceil(math.sqrt(i))+1) :
            if i > 1 and i % j == 0 :
                count += 1
        if (i >= 2 and count == 0) or i == 2 :
            answer += 1
    
    return answer
```