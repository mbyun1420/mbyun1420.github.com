---
layout: post
title:  "[C] Bubble sort, 버블 정렬"
author: software-engineer
categories: [ C ]
image: assets/images/candcplus.png
---


Bubble sorting performs sorting in the form of comparing and exchanging values of two adjacent elements with the name given to the form performing sorting like bubbling. The difference from simple sorting is that the order in which values are placed or substituted is different, but the code structure of the algorithm is the same. In the case of ascending sorting, the largest element is moved to the end through continuous substitution. The first loop of the array defines the range of the second loop and determines the range of elements to be compared, and the second loop replaces the value by comparing it with the next element.


버블정렬은 정렬을 수행하는 모양에서 붙여진 이름으로 인접한 두 요소의 값을 비교하여 교환하는 형태로 정렬을 수행한다. 단순정렬과의 차이는 값이 위치하는 순서나 치환하는 순서가 다를 뿐 알고리즘의  코드 구조는 동일하다. 오름차순 정렬의 경우 가장 큰 원소가 계속적인 치환을 통해 맨 끝으로 이동하게 된다. 배열의 첫 번째 루프는 두 번째 루프의 범위를 한정하며 비교할 요소들의 범위를 결정하며, 두 번째 루프는 바로 옆 요소와의 비교를 통해 값을 치환한다. 


```c

    #include <stdio.h>

    int a[10]={8,9,1,4,2,3,5,6,7,0};

    void BubbleSort(int N){
        int temp=0;

        for (int i=N-1; i>0; i--){
            for (int j=0; j<i; j++){
                if (a[j] > a[j+1]){
                    temp = a[j];
                    a[j]= a[j+1];
                    a[j+1]=temp;
                }
            }
        }
    }

    void PrintFunc(int N){
        for (int i=0; i<N; i++){
            printf("%d ", a[i]);
        }
    }


    int main(void){
        
        BubbleSort(10);
        PrintFunc(10);

        return 0;
    }

```

```
0 1 2 3 4 5 6 7 8 9
```