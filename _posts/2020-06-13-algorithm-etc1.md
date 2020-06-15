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
vector<int> v3(n, x);   // vector 크기를 n으로 설정하고 x로 초기화  

vector<vector<int>> v4 ;    // 2차원 vector 선언  
vector<vector<int>> v5(n, vector<int>(m));  // n x m 크기의 vector 선언  

v1.push_back(n) // v1 맨 뒤에 n을 push
v1.pop_back()   // v1 맨 뒤에 요소 pop
v1.clear()  // vector 초기화
v1.begin()  // v1의 첫 원소 주소
v1.end()    // v1의 마지막 원소의 다음 주소(push로 들어올 영역)
```

### 2. deque

```cpp
#include <deque>

deque<int> dq;  // deque 초기화
deque<int> dq2(n);  // deque의 크기를 n으로 설정
deque<int> dq3(n, x)    // deque 크기를 n으로 설정하고 x로 초기화

dq.push_back(x) // deque의 끝에 x를 push
dq.push_front(x)    // deque의 앞에 x를 push
dq.pop_back()   // deque 마지막 원소 pop
dq.pop_front()  // deque 첫 원소 pop

a = dq.insert(p, x) //  p가 가리키는 위치에 x를 삽입한다. a는 x를 나타낸다.
dq.empty()  // deque가 비었는지 조사한다.
dq.clear()  // dq를 초기화 한다.


```


### 3. algorithm

```cpp
#include <algorithm>


```