---
layout: post
title:  "[프로그래머스] 구명보트"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 탐욕법(Greedy) - 구명보트

* 문제 링크 : [구명보트](https://programmers.co.kr/learn/courses/30/lessons/42885#)

블로그에는 안 올렸지만, 한동안 C++로 코딩 테스트하다가 python으로 하려니까 어색하다.

사용 언어 : Python3

```python
from collections import deque

def solution(people, limit):
    answer = 0
    
    people = deque(sorted(people, reverse=True))
    weight = 0
    
    while(people) :
        if weight + people[0] <= limit :
            weight += people.popleft()
            if len(people) == 0 :
                answer += 1
        else :
            if weight + people[len(people)-1] <= limit :
                weight += people.pop()
            else :
                weight = 0
                answer+=1
    return answer
```