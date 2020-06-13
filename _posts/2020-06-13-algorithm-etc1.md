---
layout: post
title:  "[C++] 나를 위한 STL 정리 (계속 Update 예정)"
# subtitle: 
categories: algorithm
tags: 알고리즘 c++ etc
comments: true
---

## STL 정리

### 1. vector

```cpp
#include <vector>

vector<int> v1;  // vector 초기화 방법 (double, node, etc...)'
vector<int> v2(n);  // vector 크기를 n으로 설정
vector<int> v3(n, 0);   // vector 크기를 n으로 설정하고 0으로 초기화

vector<vector<int>> v4 ;    // 2차원 vector 선언
vector<vector<int>> v5(n, vector<int>(m));  // n x m 크기의 vector 선언
``