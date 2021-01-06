---
layout: post
title:  "[C] Selection sort, 선택 정렬"
author: software-engineer
categories: [ C ]
image: assets/images/candcplus.png
---


Selective sorting is a sorting algorithm that replaces the largest/smallest value among the comparison targets at a specific position. In the case of ascending order, the minimum value of the array elements is put in the first position, and the minimum value of the remaining elements is substituted in the next position and proceeds to the end of the array. Looking at the algorithm, it receives an array and executes a double `for` statement. In the double `for` statement, the first loop serves to change the elements of the array, and the inner loop serves to find the minimum value among the remaining objects. Then, the sorting is performed by substituting the elements of the array.


선택정렬은 특정 위치에 비교 대상 중 가장 큰/작은 값을 치환하는 정렬 알고리즘이다. 오름차순의 경우 맨 첫 자리에 배열 요소 중 최소값을 넣고, 다음 위치에는 남은 요소 중 최소값을 치환하는 형태로 배열 끝까지 진행된다. 알고리즘을 살펴보면 배열을 입력받아 이중 `for` 문을 수행한다. 이중 `for` 문에서 첫 번째 루프는 배열 요소를 변경하는 역할을 하고 안쪽 루프는 나머지 대상 중 최소 값을 찾는 역할을 한다. 이후 배열 요소를 치환함으로써 정렬을 수행한다. 



```c
#include <stdio.h>

void selectionsort(int a[], int N){
    int temp = 0;
    int min=0;

    for(int i=0; i<N-1 ; i++){
        min=i;
        for(int j=i+1; j< N; j++ ){
            if (a[j]< a[min]) min=j;
        }
        temp = a[i];
        a[i]= a[min];
        a[min]=temp;
    }     
}

int main(){
    int a[10]= {2,9,1,4,6,3,5,7,8,0};
    int a_size = (sizeof(a))/(sizeof(a[0]));
    selectionsort(a, a_size);

    for(int i=0; i<a_size; i++){
        printf("%d ", a[i]);
    }
    return 0;
}
```

```
0 1 2 3 4 5 6 7 8 9
```