---
layout: post
title:  "[프로그래머스] 위장"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 해시 - 위장

* 문제 링크 : [위장](https://programmers.co.kr/learn/courses/30/lessons/42578)

사용 언어 : Python3

파이썬은 딕셔너리가 해시로 구현되어 있기 때문에 딕셔너리를 사용했다. 경우의 수는 각 종류별 의상 수를 각각 곱하면 구할 수 있다. 단, 해당 의상의 종류를 입지 않을 수도 있기 때문에 각 종류별 의상 수에 +1을 해줘서 곱한다. 또한, 옷을 아예 입지 않는 경우는 없기 때문에 최종 값에 1을 빼주면 된다.

```python
def solution(clothes):
    answer = 1
    
    temp = dict()
    for name, category in clothes:
        if category in temp :
            temp[category] += 1
        else :
            temp[category] = 1
    
    for i in temp :
        answer = answer * (temp[i]+1)
    
    answer -= 1
    
    return answer
```