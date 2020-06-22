---
layout: post
title:  "문자열 내 p와 y의 개수"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3 C++
comments: true
# 공개여부:
published : true
---

## 연습문제 - 문자열 내 p와 y의 개수

* 문제 링크 : [문자열 내 p와 y의 개수](https://programmers.co.kr/learn/courses/30/lessons/12916)

사용 언어 : Python3

```python
def solution(s):    
    p, y = 0, 0
    for i in s :
        if i == 'p' or i == 'P' :
            p+=1
        elif i == 'y' or i == 'Y' :
            y+=1
        else :
            continue
    if p == y :
        return True
    else :
        return False
    
```