---
layout: post
title:  "[프로그래머스] K번째수"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3
comments: true
# 공개여부:
published : true
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

원치 않게 c++과 병행하고 있는데 파이썬과 너무 차이난다..

```cpp
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

vector<int> solution(vector<int> array, vector<vector<int>> commands) {
    vector<int> answer;
    vector<int> temp;
    for(int i=0; i<commands.size(); i++){
        for(int j=commands[i][0]-1; j<commands[i][1]; j++){
            temp.push_back(array[j]);
        }
        sort(temp.begin(), temp.end());
        answer.push_back(temp[commands[i][2]-1]);
        temp.clear();
    }

    return answer;
}
```