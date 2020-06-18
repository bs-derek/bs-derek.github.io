---
layout: post
title:  "[프로그래머스] 수박수박수박수박수박수?"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3 C++
comments: true
# 공개여부:
published : true
---

## 연습문제 - 수박수박수박수박수박수?

* 문제 링크 : [수박수박수박수박수박수?](https://programmers.co.kr/learn/courses/30/lessons/12922)

사용 언어 : Python3

```python
import math

def solution(n):
    answer = '수박' * math.ceil(n/2)
    answer = answer[:n]
    return answer
```

사용 연어 : C++

```cpp
#include <string>
#include <vector>

using namespace std;

string solution(int n) {
    string answer = "";
    for(int i=1; i<=n; i++){
        if(i % 2 == 0) answer+="박";
        else answer+="수";
    }
    return answer;
}
```