---
layout: post
title:  "[C] Recursive call, 재귀호출"
author: software-engineer
categories: [ C ]
image: assets/images/candcplus.png
---


Recursive calls are calling the same function within a function, i.e. itself. Recursive calls call the same function within a function, but behave like other functions because the memory area is set differently. In general, a function that uses recursive calls sets the termination condition for recursive calls in the form of a number or condition. In order to implement this, information is transmitted mainly by declaring a variable such as `n` and passing it through a recursive call.


재귀호출은 함수 내에서 동일한 함수, 즉 자기 자신을 호출하는 것이다. 재귀호출은 함수 내에서 동일 함수를 호출하지만 메모리 영역이 다르게 설정되므로 다른 함수처럼 작동한다. 일반적으로 재귀호출을 사용하는 함수는 재귀 호출에 대한 종료 조건을 횟수나 조건 형태로 설정한다. 이를 구현하기 위해 주로 `n` 과 같은 변수를 선언하고 이를 재귀호출을 통해 넘겨줌으로써 정보를 전달한다. 
  

```c
#include <stdio.h>

void f_rec(int n,int k){
    if(n==k){
        printf("End");
        return;
    }
    else {
        printf("%d\n",n);
        f_rec(n+1, k);
    }
}

int main(){

    f_rec(0,4);

    return 0;
}
```

```
0
1
2
3
End
```


Using recursive calls, you can design various algorithms. For example, you can create an array of `0/1` by using two recursive calls at a time. This array can be interpreted as a subset algorithm because it can convey information about whether or not an element at a specific position is mathematically selected.


재귀호출을 사용하면 다양한 알고리즘을 설계할 수 있는데, 예를 들어 한번에 두 번의 재귀호출을 사용하면 `0/1`로 이루어진 배열을 만들 수 있다. 이 배열은 수학적으로 특정 위치의 원소를 선택하거나 하지 않는 정보를 전달할 수 있기 때문에 부분집합 알고리즘으로 해석할 수 있다. 


```c
#include <stdio.h>

int a[3];

void f_rec(int n,int k){
    if(n==k){
        for (int i=0; i<k ; i++){
            printf("%d",a[i] );
        }
    }
    else {
        a[n]=1;
        f_rec(n+1, k);
        a[n]=0;
        f_rec(n+1,k);
    }
}

int main(){

    f_rec(0,3);

    return 0;
}
```

```
111
110
101
100
011
010
001
000
```


The subset algorithm example is a good example to understand that recursive functions behave like `stack` data structures. Looking at the output value, it can be seen that the operation of putting `1` in the `a` array is output from the successive value. After the recursive call is performed continuously, it goes down to the end, and it can be confirmed that the next recursive function is executed. In addition, when designing a recursive function, you must write the desired execution statement at the bottom to obtain each result.


부분집합 알고리즘 예제는 재귀함수가 `stack` 자료구조처럼 작동함을 이해하기에 적절한 예재이다. 출력 값을 살펴보면 `a` 배열에 `1`을 넣는 연산이 연속적으로 이루어진 값부터 출력됨을 알 수 있다. 재귀호출이 연속적으로 수행되고 나서, 끝단까지 내려가서, 다음 재귀함수가 수행됨을 확인할 수 있다. 또한 재귀함수 설계 시 맨 하단부에 원하는 실행문을 작성해야 각각의 결과물을 얻을 수 있다. 


A simple and popular example implemented with recursive calls is the Fibonacci sequence.


재귀호출로 구현한 간단하고 유명한 예시는 피보나치수열이다. 


```c
#include <stdio.h>

int a[3];

int f_rec(int n){
    if(n<2) return n;
    else return f_rec(n-1)+f_rec(n-2);
}

int main(){

    printf("%d",f_rec(10));
    return 0;
}
```

```
55
```