---
layout: post
title:  "[C] Simple sort, 단순 정렬"
author: software-engineer
categories: [ C ]
image: assets/images/candcplus.png
---

Of the various algorithms for sorting elements in an array, `Simple sort` is the simplest. `Simple sort` is in principle the same as `Bubble sort`. Basically, it is implemented through a double `for` loop, the outer `for` loop moves the position to be sorted, and the inner `for` loop searches for the comparison target. In ascending order, it compares the first array value with all remaining values and replaces each time a small value is displayed, and compares the second array value with the remaining values and replaces each time a small value appears. Because it is implemented through a double `for` statement, it has a time complexity of O(n^2).


배열 내 요소를 정렬하는 다양한 알고리즘 중 단순 정렬에 대해 소개한다. 단순 정렬은 원리적으로 거품 정렬과 동일하다. 기본적으로 이중 for 문을 통해 구현하고 바깥 for 문은 정렬 대상 자리를 이동시키는 역할을 하며, 안쪽 for 문은 비교 대상을 탐색하는 역할을 한다. 오름 차순을 기준으로 첫 번째 배열 값과 나머지 모든 값을 비교하여 작은 값이 나타낼 때마다 치환하고, 다시 두 번째 배열 값과 나머지 값들을 비교하여 작은 값이 나타낼 때마다 치환하는 형식이다. 이중 for 문을 통해 구현하기 때문에 O(n^2)의 시간복잡도를 가진다. 



```c

    #include <stdio.h>

    int a[10]={8,9,1,4,2,3,5,6,7,0};

    void SimpleSort(int N){
        int temp=0;

        for (int i=0; i<N-1; i++){
            for (int j=i+1; j<N; j++){
                if (a[i] < a[j]){
                    temp = a[i];
                    a[i] = a[j];
                    a[j] = temp;
                }
            }
        }
    }


    void PrintFunc(int N){
        for (int i=0; i<N; i++){
            printf("%d", a[i]);
        }
    }


    int main(void){
        
        SimpleSort(sizeof(a)/sizeof(a[0]));
        PrintFunc(sizeof(a)/sizeof(a[0]));

        return 0;
    }

```


Ascending and descending order only need to be reversed in the `for` loop, so I will not mention it separately. Additionally, the innermost statement in the SimpleSort function is an element substitution statement, so it can be useful if you remember it.


오름차순과 내림차순은 `for` 문 내 부호만 반대로 바꾸면 되므로 따로 언급하지는 않겠다. 부가적으로 SimpleSort 함수 내 가장 안쪽의 구문은 요소 치환 구문이므로 기억해두면 유용하게 사용할 수 있다. 