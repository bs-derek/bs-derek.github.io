---
layout: post
title:  "[프로그래머스] 프린터"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 스택/큐 - 프린터

* 문제 링크 : [프린터](https://programmers.co.kr/learn/courses/30/lessons/42587)

사용 언어 : Python3
```python
def solution(priorities, location):
    answer = 0
    flag = 0
    indexList = []
    count = 0
    for i in range(len(priorities)):
        indexList.append(i)
    while(priorities) :
        flag = 0
        select = priorities.pop(0)
        for i in range(len(priorities)):
            if priorities[i] > select :
                flag = 1
                break
        if flag == 1 :
            priorities.append(select)
            indexList.append(indexList[0])
            indexList.pop(0)
        else :
            count+=1
            order = indexList.pop(0)
            if order == location :
                answer = count
                break    
    return answer
```