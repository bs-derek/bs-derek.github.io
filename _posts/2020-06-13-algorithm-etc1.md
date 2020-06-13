---
layout: post
title:  "[C++] 나를 위한 STL 정리 (계속 Update 예정)"
# subtitle: 
categories: algorithm
tags: 알고리즘 C++ etc
comments: true
# 공개여부:
published : true
---

## STL 정리

### 1. vector

```cpp
#include <vector>

int n = 5;

vector<int> v1;  // vector 초기화 방법 (double, node, etc...)  
vector<int> v2(n);  // vector 크기를 n으로 설정  
vector<int> v3(n, 0);   // vector 크기를 n으로 설정하고 0으로 초기화  

vector<vector<int>> v4 ;    // 2차원 vector 선언  
vector<vector<int>> v5(n, vector<int>(m));  // n x m 크기의 vector 선언  

v1.push_back(n) // v1 맨 뒤에 n을 push
v1.pop_back()   // v1 맨 뒤에 요소 pop
v1.clear()  // vector 초기화
v1.begin()  // v1의 첫 원소 주소
v1.end()    // v1의 마지막 원소의 다음 주소(push로 들어올 영역)
```

### 2. algorithm

```cpp
#include <algorithm>


```