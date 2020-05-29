---
layout: post
title:  "[프로그래머스] 다음 큰 숫자"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
---

## 연습문제 - 다음 큰 숫자

* 문제 링크 : [다음 큰 숫자](https://programmers.co.kr/learn/courses/30/lessons/12911)

사용 언어 : Python3

```python
def solution(n):
    dup_n = n
    num_one = 0
    
    while(dup_n!=0) :
        if dup_n % 2 == 1 :
            num_one += 1
        dup_n = dup_n // 2
    
    while(True):
        n += 1
        dup_n = n
        dup_n_num_one = 0
        while(dup_n!=0):
            if dup_n % 2 == 1 :
                dup_n_num_one += 1
            dup_n = dup_n // 2
        
        if num_one == dup_n_num_one :
            break
    return n
```