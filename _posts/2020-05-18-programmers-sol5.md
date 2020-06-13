---
layout: post
title:  "[프로그래머스] 체육복"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 탐욕법(Greedy) - 체육복

* 문제 링크 : [체육복](https://programmers.co.kr/learn/courses/30/lessons/42862?language=python3#)

사용 언어 : Python3

문제를 대충 읽었더니 제한사항 마지막 거를 놓쳐서 조금 시간이 걸렸다. 그 외에는 되게 금방 풀어버렸음

```python
def solution(n, lost, reserve):
    answer = 0
    
    count = 0
    for i in lost :
        if i in reserve :
            reserve.remove(i)
            count+=1
            continue
        if i-1 in reserve :
            reserve.remove(i-1)
            count+=1
            continue
        if i+1 in reserve and i+1 not in lost:
            reserve.remove(i+1)
            count+=1
            continue
            
    answer = n - len(lost) + count
    return answer
```