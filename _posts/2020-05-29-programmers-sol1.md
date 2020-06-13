---
layout: post
title:  "[프로그래머스] 가운데 글자 가져오기"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 연습문제 - 가운데 글자 가져오기

* 문제 링크 : [가운데 글자 가져오기](https://programmers.co.kr/learn/courses/30/lessons/12903?language=python3)

사용 언어 : Python3


```python
def solution(s):
    answer = ''
    
    if len(s) % 2 == 0 :
        answer += s[(len(s)//2)-1:(len(s)//2)+1]
    else :
        answer += s[len(s)//2]
        
    return answer
```