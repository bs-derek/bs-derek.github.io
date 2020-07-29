---
layout: post
title:  "[SWEA] 7272. 안경이 없어!"
# subtitle: 
categories: algorithm
tags: 알고리즘 SWEA Java
comments: true
# 공개여부:
published : true
---

## SW Expert Academy - 7272. 안경이 없어!

사용 언어 : Java

```java
import java.util.Scanner;
 
class Solution
{
    public static void main(String args[]) throws Exception
    {
           Scanner sc = new Scanner(System.in);
        int T;
        T=sc.nextInt();
        char[][] map = new char[20][20];
        for(int test_case = 1; test_case <= T; test_case++) {
            int H = sc.nextInt();
            int W = sc.nextInt();
            int x_pos=0, y_pos=0;
            char current_dir = ' ';
            for(int y=0; y<H; y++) {
                String s = sc.next();
                for(int x=0; x<W; x++) {
                    map[y][x] = s.charAt(x);
                    if(map[y][x] == '>' || map[y][x] == '<' || map[y][x] == '^' || map[y][x] == 'v') {
                        y_pos = y;
                        x_pos = x;
                        current_dir=map[y][x];
                    }
                }
            }
             
            int N = sc.nextInt();
            String order = sc.next();
             
            for(int i=0; i<N; i++) {
                if(order.charAt(i) == 'U') {
                    current_dir = '^';
                    map[y_pos][x_pos] = current_dir;
                    if(y_pos - 1 >= 0 && map[y_pos-1][x_pos] == '.') {
                        map[y_pos--][x_pos] = '.';
                        map[y_pos][x_pos] = current_dir;
                    }
                }
                else if(order.charAt(i) == 'D') {
                    current_dir = 'v';
                    map[y_pos][x_pos] = current_dir;
                    if(y_pos + 1 < H && map[y_pos+1][x_pos] == '.') {
                        map[y_pos++][x_pos] = '.';
                        map[y_pos][x_pos] = current_dir;
                    }
                }
                else if(order.charAt(i) == 'L') {
                    current_dir = '<';
                    map[y_pos][x_pos] = current_dir;
                    if(x_pos - 1 >= 0 && map[y_pos][x_pos - 1] == '.') {
                        map[y_pos][x_pos--] = '.';
                        map[y_pos][x_pos] = current_dir;
                    }
                }
                else if(order.charAt(i) == 'R') {
                    current_dir = '>';
                    map[y_pos][x_pos] = current_dir;
                    if(x_pos + 1 < W && map[y_pos][x_pos + 1] == '.') {
                        map[y_pos][x_pos++] = '.';
                        map[y_pos][x_pos] = current_dir;
                    }
                }
                else {
                    int bullet_y_pos = y_pos;
                    int bullet_x_pos = x_pos;
                    if(current_dir == '^') {
                        while(bullet_y_pos>0) {
                            if(map[--bullet_y_pos][bullet_x_pos]=='*') {
                                map[bullet_y_pos][bullet_x_pos] = '.';
                                break;
                            }
                            else if(map[bullet_y_pos][bullet_x_pos] == '#') break;
                            else continue;
                        }
                    }
                    else if(current_dir == 'v') {
                        while(bullet_y_pos<H-1) {
                            if(map[++bullet_y_pos][bullet_x_pos]=='*') {
                                map[bullet_y_pos][bullet_x_pos] = '.';
                                break;
                            }
                            else if(map[bullet_y_pos][bullet_x_pos] == '#') break;
                            else continue;
                        }
                    }
                    else if(current_dir == '<') {
                        while(bullet_x_pos>0) {
                            if(map[bullet_y_pos][--bullet_x_pos]=='*') {
                                map[bullet_y_pos][bullet_x_pos] = '.';
                                break;
                            }
                            else if(map[bullet_y_pos][bullet_x_pos] == '#') break;
                            else continue;
                        }
                    }
                    else {
                        while(bullet_x_pos < W-1) {
                            if(map[bullet_y_pos][++bullet_x_pos]=='*') {
                                map[bullet_y_pos][bullet_x_pos] = '.';
                                break;
                            }
                            else if(map[bullet_y_pos][bullet_x_pos] == '#') break;
                            else continue;
                        }
                    }
                }
            }
            System.out.print("#" + test_case + " ");
            for(int y=0; y<H; y++) {
                for(int x=0; x<W; x++) {
                    System.out.print(map[y][x]);
                }
                System.out.println();
            }
        }
    }
}
```
