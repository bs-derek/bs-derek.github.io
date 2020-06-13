---
layout: post
title:  "[프로그래머스] 땅따먹기"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 연습문제 - 땅따먹기

* 문제 링크 : [땅따먹기](https://programmers.co.kr/learn/courses/30/lessons/12913?language=python3)

사용 언어 : Python3

효율성 문제는 deque로 뚝딱, 메모이제이션을 사용했다.

```python
from collections import deque

def solution(land):
    for i in range(1, len(land)):
        for j in range(0, 4):
            temp = deque(land[i-1])
            del temp[j]
            land[i][j] += max(temp)

    return max(land[len(land)-1])
```