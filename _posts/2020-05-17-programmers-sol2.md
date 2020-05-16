---
layout: post
title:  "[프로그래머스] 주식가격"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
---

## 스택/큐 - 주식가격

* 문제 링크 : [주식가격](https://programmers.co.kr/learn/courses/30/lessons/42584?language=python3)

사용 언어 : Python3
```python
def solution(prices):
    answer = []
    while(prices) :
        count = 0
        select = prices.pop(0)
        if prices :
            forcount = 0
            for i in range(len(prices)):
                if prices[i] >= select :
                    forcount += 1
                    count += 1
                elif forcount == 0 & prices[i] < select :
                    count = 1
                    break
                elif forcount != 0 & prices[i] < select :
                    count += 1
                    break
        answer.append(count)       
    return answer
```