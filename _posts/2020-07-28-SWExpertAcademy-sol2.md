---
layout: post
title:  "[SWEA] 1210. [S/W 문제해결 기본] 2일차 - Ladder1"
# subtitle: 
categories: algorithm
tags: 알고리즘 SWEA Java
comments: true
# 공개여부:
published : true
---

## SW Expert Academy - 1210. [S/W 문제해결 기본] 2일차 - Ladder1

사용 언어 : Java

```java
import java.util.Scanner;
class Solution
{
    public static void main(String args[]) throws Exception
    {
        Scanner sc = new Scanner(System.in);
        int[][] map = new int[100][100];
        for (int test_case = 1; test_case <= 10; test_case++) {
            int temp = sc.nextInt();
            int x_pos = 0, y_pos = 0;
 
            for (int i = 0; i < 100; i++) {
                for (int j = 0; j < 100; j++) {
                    map[i][j] = sc.nextInt();
                    if (map[i][j] == 2) {
                        x_pos = j;
                        y_pos = i;
                    }
                }
            }
            y_pos--;
            int dir = 0;
            while (true) {
                if (y_pos == 0) break;
                else if (dir == 1) {
                    if (x_pos > 0 && map[y_pos][x_pos - 1] == 1) x_pos--;
                    else dir = 0;
                }
                else if (dir == 2) {
                    if (x_pos < 99 && map[y_pos][x_pos + 1] == 1) x_pos++;
                    else dir = 0;
                } 
                else if (dir == 0){
                    y_pos--;
                    if (dir != 1 && x_pos > 0 && map[y_pos][x_pos - 1] == 1) {
                        x_pos--;
                        dir = 1;
                    }
                    else if (dir != 2 && x_pos < 99 && map[y_pos][x_pos + 1] == 1) {
                        x_pos++;
                        dir = 2;
                    }
                }
            }
            System.out.println("#" + temp + " " + x_pos);
        }
        sc.close();
    }
}
```