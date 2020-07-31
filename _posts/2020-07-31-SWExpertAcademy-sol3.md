---
layout: post
title:  "[SWEA] 3499. 퍼펙트 셔플"
# subtitle: 
categories: algorithm
tags: 알고리즘 SWEA Java
comments: true
# 공개여부:
published : true
---

## SW Expert Academy - 3499. 퍼펙트 셔플

DFS 제대로 배우고 가지치기 나중에 업데이트 할 예정

사용 언어 : Java

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.StringTokenizer;
 
class Solution{
    static int[] permutations = new int[10];
    static boolean[] isSelected = new boolean[11];
    static int[][] visit = new int[10][2];
    static int min = 9999;
    static int company_y, company_x, home_y, home_x;
     
    public static void main(String args[]) throws Exception{
        BufferedReader in = new BufferedReader(new InputStreamReader(System.in));
         
        int T = Integer.parseInt(in.readLine());
        for(int test_case = 1; test_case <= T; test_case++) {
            int N = Integer.parseInt(in.readLine());
            StringTokenizer st = new StringTokenizer(in.readLine());
            company_y = Integer.parseInt(st.nextToken());
            company_x = Integer.parseInt(st.nextToken());
            home_y = Integer.parseInt(st.nextToken());
            home_x = Integer.parseInt(st.nextToken());
            for(int i=0; i<N; i++) {
                visit[i][0] = Integer.parseInt(st.nextToken());
                visit[i][1] = Integer.parseInt(st.nextToken());
            }
            permutation(0, N);
             
            System.out.println("#" + test_case + " " + min);
            min = 9999;
        }
    }
     
    private static void permutation(int count, int N) {
        if(count==N) {
            int sum = 0;
            int current_x = company_x, current_y = company_y;
            for(int i=0; i<N; i++) {
                sum += (Math.abs(current_y - visit[permutations[i]-1][0]) + Math.abs(current_x - visit[permutations[i]-1][1]));
                current_y = visit[permutations[i]-1][0];
                current_x = visit[permutations[i]-1][1];
                if(sum>min) return;
            }
            sum += Math.abs(home_y - current_y) + Math.abs(home_x - current_x);
            if(min > sum) min = sum;
            return;
        }
         
        for(int i=1; i<=N; i++) {
            if(isSelected[i]) continue;
            permutations[count] = i;
            isSelected[i] = true;
            permutation(count+1, N);
            isSelected[i] = false;
        }
    }
}
```
