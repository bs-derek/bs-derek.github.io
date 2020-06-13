---
layout: post
title:  "[프로그래머스] 같은 숫자는 싫어"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 연습문제 - 같은 숫자는 싫어

* 문제 링크 : [같은 숫자는 싫어](https://programmers.co.kr/learn/courses/30/lessons/12906)

사용 언어 : Python3

deque 쓰면 효율성까지 통과한다. deque 쓰는 버릇을 들여야겠다.


```python
from collections import deque

def solution(arr):
    answer = []
    
    arr = deque(arr)

    previous = arr.popleft()
    while(arr):
        current = arr.popleft()
        if previous != current :
            answer.append(previous)
            previous = current
        if len(arr) == 0 :
            answer.append(current)
                
    return answer
```