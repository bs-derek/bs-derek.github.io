---
layout: post
title:  "[프로그래머스] 두 정수 사이의 합"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 연습문제 - 두 정수 사이의 합

* 문제 링크 : [두 정수 사이의 합](https://programmers.co.kr/learn/courses/30/lessons/12912)

사용 언어 : Python3


```python
def solution(a, b):
    answer = 0
    
    if a >= b :
        for i in range(b, a+1):
            answer += i
    else :
        for i in range(a, b+1):
            answer += i

    return answer
```