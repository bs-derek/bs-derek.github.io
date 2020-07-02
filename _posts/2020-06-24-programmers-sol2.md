---
layout: post
title:  "[프로그래머스] 문자열 내림차순으로 배치하기"
# subtitle: 
categories: algorithm
tags: 알고리즘 프로그래머스 Python3 C++
comments: true
# 공개여부:
published : true
---

## 연습문제 - 문자열 내림차순으로 배치하기

* 문제 링크 : [문자열 내림차순으로 배치하기](https://programmers.co.kr/learn/courses/30/lessons/12917)

사용 언어 : Python3

```python
def solution(s):
    answer = ''.join(sorted(s, reverse=True))
    return answer
```

사용 연어 : C++

```cpp
#include <string>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;

bool compare_val(int a, int b){return a > b;}

string solution(string s) {
    string answer = "";
    sort(s.begin(), s.end(), compare_val);
    answer = s;
    return answer;
}
```