---
layout: post
title:  "[프로그래머스] 카펫"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
---

## 완전탐색 - 카펫

* 문제 링크 : [카펫](https://programmers.co.kr/learn/courses/30/lessons/42842)

사용 언어 : Python3

brown의 갯수와 yellow 갯수의 합의 약수가 카펫의 가로, 세로 크기가 된다. 그렇기 때문에 약수를 먼저 구한다.
나의 경우에는 가로, 세로의 크기가 어차피 3을 넘어가기 때문에 3부터 약수를 구했고, 3부터 나눌 것이기 때문에
total에서 3을 나눈 값까지만 약수를 구했다. 여기까지 하면 알고리즘은 끝이다.

yellow의 값은 (가로-2) x (세로-2) 이기 때문에 그 조건을 만족하는 약수를 출력하면 끝.

```python
def solution(brown, yellow):
    answer = []
    
    total = brown + yellow
    yaksoo = []
    for i in range(3, (total//3)+1) :
        if total % i == 0 :
            yaksoo.append(i)
    
    while(yaksoo) :
        if len(yaksoo) >= 2 :
            row = yaksoo.pop(0)
            col = yaksoo.pop(len(yaksoo)-1)
        else :
            row = yaksoo.pop(0)
            col = row
        
        if (row-2) * (col-2) == yellow :
            answer.append(col)
            answer.append(row)
            break
        else :
            continue
    
    return answer
```