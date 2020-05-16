---
layout: post
title:  "[프로그래머스] 탑"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
---

## 스택/큐 - 탑

* 문제 링크 : [탑](https://programmers.co.kr/learn/courses/30/lessons/42588)

사용 언어 : Python3

```python
def solution(heights):
    tmp = []
    answer = []
    while(heights) :
        flag = 0
        right = heights.pop()
        for i in range(len(heights)-1, -1, -1) :
            if heights[i] > right :
                tmp.append(i+1)
                flag = 1
                break
        if flag == 0:
            tmp.append(0)
    answer = tmp[::-1]
    
    return answer
```