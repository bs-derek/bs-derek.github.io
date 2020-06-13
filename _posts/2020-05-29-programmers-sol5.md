---
layout: post
title:  "[프로그래머스] 나누어 떨어지는 숫자 배열"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 연습문제 - 나누어 떨어지는 숫자 배열

* 문제 링크 : [나누어 떨어지는 숫자 배열](https://programmers.co.kr/learn/courses/30/lessons/12910)

사용 언어 : Python3


```python
def solution(arr, divisor):
    answer = []
    
    for i in arr :
        if i % divisor == 0 :
            answer.append(i)
    if len(answer) == 0 :
        answer.append(-1)
    answer = sorted(answer)
    return answer
```