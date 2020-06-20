---
layout: post
title:  "[프로그래머스] 크레인 인형뽑기 게임"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
---

## 2019 카카오 개발자 겨울 인턴십 - 크레인 인형뽑기 게임

* 문제 링크 : [크레인 인형뽑기 게임](https://programmers.co.kr/learn/courses/30/lessons/64061)

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

사용 언어 : C++

```cpp
#include <string>
#include <vector>
#include <iostream>
#include <deque>

using namespace std;

int solution(vector<vector<int>> board, vector<int> moves) {
    int answer = 0;
    int board_count[31];
    deque<int> bucket;
    for(int i=0; i<board.size(); i++){
        for(int j=0; j<board.size(); j++){
            if(board[j][i] != 0) {
                board_count[i] = j;
                break;
            }
        }
    }
    
    for(int i=0; i<moves.size(); i++){
        if (board_count[moves[i]-1] == board.size()){continue;}
        else{
            bucket.push_back(board[board_count[moves[i]-1]][moves[i]-1]);
            board_count[moves[i]-1] += 1;
            
            if (bucket.size() > 1 && bucket[bucket.size()-1] == bucket[bucket.size()-2]){
                bucket.pop_back();
                bucket.pop_back();
                answer += 2; 
            }
        }
    }
    return answer;
}
```