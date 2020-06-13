---
layout: post
title:  "[프로그래머스] 124 나라의 숫자"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 연습문제 - 124 나라의 숫자

* 문제 링크 : [124 나라의 숫자](https://programmers.co.kr/learn/courses/30/lessons/12899#)

그냥 3진수로 바꾼다고 생각하면 쉽다. 3으로 나눈 나머지를 케이스로 나눠 처리한다.

사용 언어 : Python3

```python
def solution(n):
    answer = ''
    temp = []
    
    while(n>0) :
        if n % 3 == 1 :
            temp.append('1')
            n = n // 3
        elif n % 3 == 2 :
            temp.append('2')
            n = n // 3
        else :
            temp.append('4')
            n = (n // 3) - 1
    # list to str / [::-1] 은 역순출력
    answer = (''.join(temp[::-1]))
    return answer
```