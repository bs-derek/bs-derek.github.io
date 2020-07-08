---
layout: post
title:  "[프로그래머스] 시저 암호"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 연습문제 - 시저 암호

* 문제 링크 : [시저 암호](https://programmers.co.kr/learn/courses/30/lessons/12926#)

사용 언어 : Python3

```python
def solution(s, n):
    answer = ''
    for i in s :
        if ord('a') <= ord(i) <= ord('z') :
            if ord(i) + n > ord('z') :
                answer += chr(ord(i) + n - ord('z') + ord('a') - 1)
            else :
                answer += chr(ord(i) + n)
        elif ord('A') <= ord(i) <= ord('Z') :
            if ord(i) + n > ord('Z') :
                answer += chr(ord(i) + n - ord('Z') + ord('A') - 1)
            else :
                answer += chr(ord(i) + n)
        else :
            answer += ' '
    return answer
```