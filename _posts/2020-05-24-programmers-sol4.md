---
layout: post
title:  "[프로그래머스] H-Index"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
---

## 정렬 - H-Index

* 문제 링크 : [H-Index](https://programmers.co.kr/learn/courses/30/lessons/42747#)

사용 언어 : Python3

### 첫 번째 풀이

정렬하고나서 중앙값이면 대충 되겠네~ 라고 생각했던 안일한 코드

```python
import math

def solution(citations):
    answer = 0
    citations = sorted(citations)
    
    if len(citations) == 1 :
        answer = citations[0]
    elif len(citations) % 2 == 0 :
        answer = math.ceil((citations[math.floor((len(citations) / 2)) - 1] + citations[math.floor(len(citations) / 2)]) / 2)
    else :
        answer = citations[math.floor(len(citations) / 2)]
    return answer
```

### 두 번째 풀이

temp 리스트를 만들어 citations의 최댓값부터 0까지 감소시키면서 몇번씩 인용되었는지 체크해서 풀었다.

```python
def solution(citations):
    answer = 0
        
    citations = sorted(citations)
    temp = []
    
    for i in range(citations[-1], -1, -1) :
        count = 0
        for j in citations :
            if j >= i :
                count += 1
        if count >= i :
            break
    if sum(citations) == 0 :
        answer = 0
    elif len(set(citations)) == 1 : 
        answer = citations[0]
    else:
        answer = i
    return answer
```