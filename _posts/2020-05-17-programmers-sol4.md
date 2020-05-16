---
layout: post
title:  "[프로그래머스] 기능개발"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
---

## 스택/큐 - 기능개발

* 문제 링크 : [기능개발](https://programmers.co.kr/learn/courses/30/lessons/42586)

사용 언어 : Python3

```python
def solution(progresses, speeds):
    answer = []
    while(progresses):
        for i in range(len(speeds)):
            progresses[i] += speeds[i] 
        if len(progresses) > 0 and progresses[0] >= 100 :
            count = 0
            while progresses and progresses[0] >= 100 :
                count += 1
                progresses.pop(0)
                speeds.pop(0)
            answer.append(count)
    return answer
```