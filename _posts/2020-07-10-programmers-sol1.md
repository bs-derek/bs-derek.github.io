---
layout: post
title:  "[프로그래머스] 키패드 누르기"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 2020 카카오 인턴십 - 키패드 누르기

* 문제 링크 : [키패드 누르기](https://programmers.co.kr/learn/courses/30/lessons/67256)

며칠 전에 인턴십때 풀었던 거네..

사용 언어 : Python3

```python
def solution(s):
    answer = ''
    count = 0
    for i in s :
        if i == ' ' :
            count = 0
            answer += ' '
        elif count % 2 == 1 :
            answer += i.lower()
            count += 1
        else :
            answer += i.upper()
            count += 1
    return answer
```