---
layout: post
title:  "[프로그래머스] 문자열 내 마음대로 정렬하기"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
---

## 연습문제 - 문자열 내 마음대로 정렬하기

* 문제 링크 : [문자열 내 마음대로 정렬하기](https://programmers.co.kr/learn/courses/30/lessons/12915)

사용 언어 : Python3

sorted 함수를 쓰면 제한 조건까지 쉽게 끝낸다.


```python
def solution(strings, n):
    answer = []
    strings = sorted(strings)
    answer = sorted(strings, key = lambda x : x[n])
    return answer
```