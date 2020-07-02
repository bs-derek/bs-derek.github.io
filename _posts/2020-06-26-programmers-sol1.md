---
layout: post
title:  "[프로그래머스] 서울에서 김서방 찾기"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 연습문제 - 서울에서 김서방 찾기

* 문제 링크 : [서울에서 김서방 찾기](https://programmers.co.kr/learn/courses/30/lessons/12919?language=python3)

사용 언어 : Python3

```python
def solution(seoul):
    answer = '김서방은 '
    answer += str(seoul.index("Kim")) + '에 있다'
    return answer
```