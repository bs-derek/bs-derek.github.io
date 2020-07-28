---
layout: post
title:  "[SWEA] 1954. 달팽이 숫자"
# subtitle: 
categories: algorithm
tags: 알고리즘 SWEA Java
comments: true
# 공개여부:
published : true
---

## SW Expert Academy - 1954. 달팽이 숫자

사용 언어 : Java

```java
import java.util.Scanner;
 
class Solution
{
    public static void main(String args[]) throws Exception
    {
        Scanner sc = new Scanner(System.in);
        int T;
        T = sc.nextInt();
        for (int test_case = 1; test_case <= T; test_case++) {
            int N = sc.nextInt();
 
            int map[][] = new int[N][N];
 
            int count = 1;
            int x_pos = 0, y_pos = 0;
            map[y_pos][x_pos] = count++;
            while (count <= N * N) {
                if (x_pos + 1 < N && map[y_pos][x_pos + 1] == 0) {
                    while(true) {
                        if(x_pos + 1 >= N || map[y_pos][x_pos + 1]!=0) break;
                        map[y_pos][++x_pos] = count++;
                    }
                }
                else if (y_pos + 1 < N && map[y_pos + 1][x_pos] == 0) {
                    while(true) {
                        if(y_pos + 1 >= N || map[y_pos + 1][x_pos]!=0) break;
                        map[++y_pos][x_pos] = count++;
                    }
                }
                else if (x_pos - 1 >= 0 && map[y_pos][x_pos - 1] == 0) {
                    while(true) {
                        if(x_pos - 1 < 0 || map[y_pos][x_pos - 1] != 0) break;
                        map[y_pos][--x_pos] = count++;
                    }
                } else if (y_pos - 1 >= 0 && map[y_pos - 1][x_pos] == 0) {
                    while(true) {
                        if(y_pos - 1 < 0 || map[y_pos - 1][x_pos] != 0) break;
                        map[--y_pos][x_pos] = count++;
                    }
                }
 
            }
            System.out.println("#" + test_case);
            for (int i = 0; i < N; i++) {
                for (int j = 0; j < N; j++) {
                    System.out.print(map[i][j] + " ");
                }
                System.out.println();
            }
        }
        sc.close();
    }
}
```