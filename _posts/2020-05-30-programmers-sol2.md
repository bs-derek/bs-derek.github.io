---
layout: post
title:  "[프로그래머스] 튜플"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
---

## 2019 카카오 개발자 겨울 인턴십 - 튜플

* 문제 링크 : [튜플](https://programmers.co.kr/learn/courses/30/lessons/64065)

사용 언어 : Python3

문자열 이용하면 쉽더라

```python
def solution(s):
    
    answer = []
    s = s[2:len(s)-2]
    s = s.split('},{')
    s = sorted(s, key = lambda x:len(x))
    for i in s:
        if ',' in i :
            temp = i.split(',')
            for j in temp :
                if int(j) not in answer :
                    answer.append(int(j))
                    break
        else :
            answer.append(int(i))
    return answer
```