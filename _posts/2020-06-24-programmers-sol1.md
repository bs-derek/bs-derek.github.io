---
layout: post
title:  "[프로그래머스] 문자열 다루기 기본"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 연습문제 - 문자열 다루기 기본

* 문제 링크 : [문자열 다루기 기본](https://programmers.co.kr/learn/courses/30/lessons/12918)

사용 언어 : Python3

```python
def solution(s):
    answer = True
    
    for i in s :
        if '0' <= i <= '9' :
            pass
        else :
            answer = False
            break
            
    if (len(s) == 4 or len(s) == 6) and answer==True :
        answer = True
    else :
        answer = False
    return answer
```