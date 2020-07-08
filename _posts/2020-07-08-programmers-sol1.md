---
layout: post
title:  "[프로그래머스] 숫자의 표현"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 연습문제 - 숫자의 표현

* 문제 링크 : [숫자의 표현](https://programmers.co.kr/learn/courses/30/lessons/12924)

사용 언어 : Python3

```python
import math
def solution(n):
    answer = 0
    if n % 2 == 0 :
        mid = n//2
    else:
        mid = math.ceil(n/2)
    
    for i in range(1, mid+1) :
        sum = i
        for j in range(i+1, mid+1):
            sum += j
            if sum == n :
                answer += 1
                break
            if sum > n :
                break
    answer += 1
    return answer
```