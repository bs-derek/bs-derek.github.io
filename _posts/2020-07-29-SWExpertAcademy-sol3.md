---
layout: post
title:  "[SWEA] 2805. 농작물 수확하기"
# subtitle: 
categories: algorithm
tags: 알고리즘 SWEA Java
comments: true
# 공개여부:
published : true
---

## SW Expert Academy - 2805. 농작물 수확하기

사용 언어 : Java

```java
import java.util.Scanner;
class Solution
{
    public static void main(String args[]) throws Exception
    {
        Scanner sc = new Scanner(System.in);
        int T = Integer.parseInt(sc.nextLine());
        int[][] map = new int[50][50];
         
        for(int test_case = 1; test_case <= T; test_case++)
        {
            int N = Integer.parseInt(sc.nextLine());
            int count = 0;
            for(int y=1; y<=N; y++) {
                String s = sc.nextLine();
                for(int x=1; x<=N; x++) {
                    map[y][x] = s.charAt(x-1) - 48;
                }
            }
             
            for(int y = 1; y<=N; y++) {
                count += map[y][(N+1)/2];
            }
             
            int y_pos = N-1;
            for(int x = (N+1)/2 - 1; x>0; x--) {
                for(int y = N-y_pos+1; y<=y_pos; y++) {
                    count += map[y][x];
                }
                y_pos--;
            }
             
            y_pos = N-1;
            for(int x = (N+1)/2 + 1; x<=N; x++) {
                for(int y = N-y_pos+1; y<=y_pos; y++) {
                    count += map[y][x];
                }
                y_pos--;
            }
            System.out.println("#" + test_case + " " + count);
        }
    }
}
```
