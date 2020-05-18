---
layout: post
title:  "[프로그래머스] 2016년"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
---

## 연습문제 - 2016년

* 문제 링크 : [2016년](https://programmers.co.kr/learn/courses/30/lessons/12901)

사용 언어 : Python3

텍스트 슬라이싱을 쓰면 쉽다.

```python
def solution(a, b):
    answer = ''
    days = [31, 29, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
    
    count = sum(days[0:a-1]) + b - 1
    
    if count % 7 == 0 :
        answer += 'FRI'
    elif count % 7 == 1 :
        answer += 'SAT'
    elif count % 7 == 2 :
        answer += 'SUN'
    elif count % 7 == 3 :
        answer += 'MON'
    elif count % 7 == 4 :
        answer += 'TUE'
    elif count % 7 == 5 :
        answer += 'WED'
    else :
        answer += 'THU'
        
    return answer
```