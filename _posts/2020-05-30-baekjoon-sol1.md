---
layout: post
title:  "[백준] 15649번 - N과 M(1)"
# subtitle: 
categories: algorithm
tags: 알고리즘 백준 Python3
comments: true
# 공개여부:
published : true
---

## 15649번 - N과 M(1)

* 문제 링크 : [N과 M(1)](https://www.acmicpc.net/problem/15649)

DFS를 이용한 재귀함수 다시 공부할겸, 순열과 조합 라이브러리 사용할 겸 다시 풀어보는 N과 M시리즈

### 첫 번째 풀이(python 라이브러리 사용)

사용 언어 : Python3

```python
import sys
import itertools

N, M = map(int, sys.stdin.readline().split())

for i in itertools.permutations([j for j in range(1, N+1)], M):
    print(str(i)[1:-1].replace(',', ''))
```

### 두 번째 풀이(DFS구현)

효율성 높여보겠다고 deque 쓰고 sys.stdin 썼는데, 우째서 예전 코드보다 메모리랑 시간 둘 다 많이 쓴 거지..?

사용 언어 : Python3

```python
import sys
from collections import deque

N, M = map(int, sys.stdin.readline().split())
temp = deque()
isVisited = [0] * N

def dfs(start):
    if start == M:
        print (*temp)
        return

    for i in range(0, N) :
        if isVisited[i] == True :
            continue
        isVisited[i] = True
        temp.append(i+1)
        dfs(start+1)
        temp.pop()
        isVisited[i] = 0

dfs(0)
```

### 세 번째 풀이

어쩌다 보니 C++로 코딩테스트를 볼 일이 생겨 다시 짜보게 되었다.

사용 언어 : C++

```cpp
#include <iostream>
#include <cstring>
#include <vector>

using namespace std;

int N, M;
int arr[8];
int selected[8];
vector<int> V;

void Print(){
	for(int i=0; i<V.size(); i++){
		cout<<V[i]<<" ";
	}
	cout<<"\n";
}

void DFS(int count){
	if(count == M){
		Print();
		return;
	}

	for(int i=0; i<N; i++){
		if(selected[i] == 1) continue;
		selected[i] = 1;
		V.push_back(arr[i]);
		DFS(count+1);
		selected[i] = 0;
		V.pop_back();
	}
}

int main(){
	cin>>N>>M;

	for(int i=0; i<N; i++){
		arr[i] = i+1;
	}

	DFS(0);
}
```