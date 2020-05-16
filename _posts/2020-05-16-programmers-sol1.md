---
layout: post
title:  "[프로그래머스] 크레인 인형뽑기 게임"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
---

## 2019 카카오 개발자 겨울 인턴십 - 크레인 인형뽑기 게임

```
* 문제 링크 : https://programmers.co.kr/learn/courses/30/lessons/64061
```

사용 언어 : Python3
```python
def solution(board, moves):
    answer = 0
    bucket = []; board_state = [0 for i in range(len(board))]
    bucket_num = 0
    previous_rem = 0
    # board의 가장 위에 있는 행 번호를 저장
    for i in range(len(board)) :
        for j in range(len(board)):
            if board[j][i]!= 0:
                board_state[i] = j
                break
    for i in moves :
        # board의 각 열의 행이 board의 크기가 되면
        if board_state[i-1] == len(board) :
            continue
        else :
            bucket.append(board[board_state[i-1]][i-1])
            board_state[i-1] += 1
            
            if len(bucket) > 1 and bucket[len(bucket)-1] == bucket[len(bucket)-2] :
                bucket.pop()
                bucket.pop()
                answer += 2
    return answer
```