---
layout: post
title:  "가장 큰 정사각형 찾기"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 연습문제 - 가장 큰 정사각형 찾기

* 문제 링크 : [가장 큰 정사각형 찾기](https://programmers.co.kr/learn/courses/30/lessons/12905)

사용 언어 : Python3

DP를 이용하여 푸는 문제, DP는 알았으나 점화식을 찾을 생각을 못해봤다. 
검색을 해보니 board의 왼쪽 상단, 왼쪽, 상단 이 세개의 최솟값에서 1을 더하면 나올 수 있는 정사각형의 한 변의 길이라고 한다. 그걸 이용해서 풀면 쉽게 풀린다.

```python
def solution(board):
    answer = 1234
    
    for i in range(0, len(board)) :
        if board[i][0] == 0 : max = 0
        else : 
            max = board[i][0]
            break
    for i in range(0, len(board[0])) :
        if max == 1 : break
        if board[0][i] == 0 : max = 0
        else :
            max = board[0][i]
            break
    
    for i in range(1, len(board)):
        for j in range(1, len(board[0])):
            if board[i][j] == 0 :
                continue
            else :
                board[i][j] = min(board[i-1][j-1], board[i-1][j], board[i][j-1]) + 1
                if board[i][j] > max : max = board[i][j]
    answer = max * max
    return answer
    
```