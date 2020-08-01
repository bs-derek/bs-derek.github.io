---
layout: post
title:  "[SWEA] 1861. 정사각형 방"
# subtitle: 
categories: algorithm
tags: 알고리즘 SWEA Java
comments: true
# 공개여부:
published : true
---

## SW Expert Academy - 1861. 정사각형 방

사용 언어 : Java

```java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.Arrays;
import java.util.StringTokenizer;
class Solution
{
	public static void main(String args[]) throws Exception
	{
        BufferedReader in = new BufferedReader(new InputStreamReader(System.in));
		int T = Integer.parseInt(in.readLine());
		int map[][] = new int[1000][1000];
		int dp[] = new int[1000001];
		for(int test_case=1; test_case<=T; test_case++) {
			int N = Integer.parseInt(in.readLine());
			
			for(int y = 0; y<N; y++) {
				StringTokenizer st = new StringTokenizer(in.readLine());
				for(int x = 0; x<N; x++) {
					map[y][x] = Integer.parseInt(st.nextToken());
				}
			}
			int index = 999999999, max = 0;
			for(int y=0; y<N; y++) {
				for(int x=0; x<N; x++) {
					int count = 0;
					int x_copy = x, y_copy = y;
					while(true) {
						if(dp[map[y_copy][x_copy]]!=0) {
							count += (dp[map[y_copy][x_copy]]);
							dp[map[y][x]] = count;
							if (count + 1>max) {
								max = count + 1;
								index = map[y][x];
							}
							else if(count + 1 == max) {
								if(index > map[y][x]) index = map[y][x];
							}
							break;
						}
						else if(x_copy + 1 < N && map[y_copy][x_copy+1] == (map[y_copy][x_copy] + 1)) {
							x_copy++;
							count++;
						}
						else if(x_copy - 1 >= 0 && map[y_copy][x_copy-1] == (map[y_copy][x_copy] + 1)) {
							x_copy--;
							count++;
						}
						else if(y_copy + 1 < N && map[y_copy+1][x_copy] == (map[y_copy][x_copy] + 1)) {
							y_copy++;
							count++;
						}
						else if(y_copy -1 >= 0 && map[y_copy-1][x_copy] == (map[y_copy][x_copy] + 1)) {
							y_copy--;
							count++;
						}
						else {
							dp[map[y][x]] = count;
							if (count + 1 > max) {
								max = count + 1;
								index = map[y][x];
							}
							else if(count + 1 == max) {
								if(index > map[y][x]) index = map[y][x];
							}
							break;
						}
					}
				}
			}
			System.out.println("#" + test_case + " " + index + " " + max);
			Arrays.fill(dp, 0);
		}
	}
}
```
