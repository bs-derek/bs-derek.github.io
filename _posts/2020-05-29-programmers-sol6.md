---
layout: post
title:  "[프로그래머스] 올바른 괄호"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
---

## 연습문제 - 올바른 괄호

* 문제 링크 : [올바른 괄호](https://programmers.co.kr/learn/courses/30/lessons/12909)

사용 언어 : Python3

앞으로 queue와 stack의 기능을 이용할 땐 효율성을 위해 deque를 무조건 사용할 것이다.

```python
from collections import deque
def solution(s):
    answer = True
    s = deque(s)
    temp = deque()
    while(s):
        a = s.popleft()
        if a == '(':
            temp.append(a)
        else :
            if len(temp) == 0 :
                answer = False
                break
            else :
                temp.pop() 
                
    if answer != False and len(temp) == 0 :
        answer = True
    else :
        answer = False
    return answer
```