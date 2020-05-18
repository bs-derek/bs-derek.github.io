---
layout: post
title:  "[프로그래머스] K번째수"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
---

## 정렬 - K번째수

* 문제 링크 : [K번째수](https://programmers.co.kr/learn/courses/30/lessons/42748)

사용 언어 : Python3

사기적인 Python의 텍스트 슬라이싱..

```python
def solution(array, commands):
    answer = []
    for i, j, k in commands :
        temp = sorted(array[i-1:j])
        answer.append(temp[k-1])
    return answer
```