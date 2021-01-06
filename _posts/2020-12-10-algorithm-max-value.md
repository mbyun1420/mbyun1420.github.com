---
layout: post
title:  "[C] Fining max value, 알고리즘 : 최대 값 찾기"
author: software-engineer
categories: [ C ]
image: assets/images/candcplus.png
---

To find the maximum value in an array, you can directly find the maximum value or return the index where the maximum value of the array is located. Since the maximum value in the array can be accessed by knowing the index where the maximum value is located, in most cases, an algorithm to find the index is implemented. A simple algorithm is to update the index at that time to a variable such as `max_id` when an arbitrary index `i` circulating in the for statement searches the entire array and finds a large value.


배열 내에 최대 값을 찾기 위해서는 최대 값을 바로 찾거나, 배열 최대 값이 위치한 인덱스를 반환하면 된다. 최대 값이 위치한 인덱스를 알면 배열 내 최대 값에 접근 가능하기 때문에 대부분의 경우에는 인덱스를 찾는 알고리즘을 구현한다. 간단한 알고리즘은 for 문 내에서 순환하는 임의의 인덱스 `i` 가 배열 전역을 탐색하면서 큰 값을 발견하면 그때의 인덱스를 `max_id` 와 같은 변수에 갱신하면 된다. 



```c

    #include <stdio.h>

    int main(void){
        int a[10]={0,};
        int max_id=0;

        for(int i=0; i< sizeof(a)/sizeof(a[0]); i++){
            if (a[max_id] < a[i]) max_id = i; 
        }

        int max_value=0;

        for(int i=0; i< sizeof(a)/sizeof(a[0]); i++){
            if (max_value < a[i]) max_value = a[i];
        }

    return 0;
    }

```
