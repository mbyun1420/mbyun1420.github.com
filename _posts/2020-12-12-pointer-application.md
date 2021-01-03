---
layout: post
title:  "[C] Pointer application, 포인터 활용"
author: software-engineer
categories: [ C ]
image: assets/images/candcplus.png
---

The pointer concept is simple, but the use case is confusing, so let's look at a few simple functions. The first is when you use an increment operator and a pointer together. Both `*a++` and `*++a` are processed according to the priority of the operator as described in [operation][op]. First, in the case of `*a++`, the dereferencing operation, which is a unary operator close to a, is executed, receives the value, prints it, and then increases the address of the pointer variable `a` by 1. In the case of `*++a`, the address of a is increased by 1 first, and the corresponding value is returned by riding the changed address. In the case of `(*a)++`, the dereference operation is performed first, inverses the value, and then increases the value by 1. Let's look at a simple example to help you understand.


포인터 개념은 단순하지만 사용사례가 헷갈리기 쉬우므로 몇가지 간단한 함수를 통해 알아보고자 한다. 첫번째는 증감연산자와 포인터를 함께 쓸 때이다. `*a++`, `*++a` 두 개는 [operation][op]에서 설명한 것과 같이 연산자의 우선순위에 따라 처리된다. 먼저 `*a++`의 경우 a와 가까운 단항연산자인 역참조 연산부터 수행되어, 주소를 타고 값을 받아와 출력하고 이후 포인터 변수 `a`의 주소를 1만큼 증가시킨다. `*++a`의 경우 a의 주소를 1만큼 먼저 증가시키고 변경된 주소를 타고 해당하는 값을 반환한다. `(*a)++` 의 경우에는 역참조 연산을 우선적으로 수행하여 값을 반한한 뒤 값을 1만큼 증가시킨다. 이해를 돕기 위해 만든 간단한 예제를 살펴본다. 



```c
    #include <stdio.h>

    int main(){
        char a[6]="ABCDE";
        char *p = a;

        printf("%c\n", *++p);
        printf("%c\n", *p++);
        printf("%c\n", *p);
        printf("%c\n", (*p)++);
        printf("%c\n", *p);

        return 0; 
    }
```

```
B
B
C
C
D
```


In the case of the `swap` function that changes two values, it generally receives and replaces the value, but it can also receive and replace an address in the form of a pointer variable.


두 값을 바꾸는 `swap` 함수의 경우 값을 일반적으로 받아와 바로 치환하지만, 포인터 변수 형태로 주소를 받아와 치환할 수도 있다. 


```c
    #include <stdio.h>

    void swap(int *a, int *b){
        int temp = *a;
        *a = *b;
        *b = temp;
    }


    int main(){
        int a=4;
        int b=27; 
        printf("%d %d\n", a,b);

        swap(&a,&b);

        printf("%d %d\n", a,b);

        return 0; 
    }
```

```
4 27
27 4

```


For an array of strings, we can write a simple function to get the string copy and length. In the case of string copying, if you refer through the address of the target string and the array to contain by using the while statement, you can access through the address and assign a value. When the address moves to the end of the string, the last value, `NULL`, is returned, so the while statement is automatically terminated. In the case of string length calculation, you can accurately calculate the length of the contained string by using a pointer variable expression. When you use the sizeof function to find the length of a string, not only the length including the `NULL` value is found, but if the size of the array is larger than the size of the string, the array size value is output, so the exact string length cannot be obtained (of course You can also use the `strlen` function in the `string.h` file to calculate the exact length).


문자열 배열에 대해 문자열 복사와 길이를 구하는 간단한 함수를 만들 수 있다. 문자열 복사의 경우 while문을 활용하여 대상 문자열과 담을 배열의 주소를 통해 참조하면 주소를 통해 접근하여 값을 대입할 수 있다. 문자열의 끝까지 주소가 이동하면 마지막 값인 `NULL` 값이 반환되므로 while문이 자동으로 종료된다. 문자열 길이 계산의 경우 포인터 변수식을 사용하여 들어있는 문자열 길이를 정확하게 계산할 수 있다. sizeof 함수를 사용하여 문자열의 길이를 구하게 되면, `NULL` 값이 포함된 길이가 구해질 뿐만 아니라 만약 배열의 크기가 문자열의 크기보다 큰 경우 배열 크기 값을 출력하기 때문에 정확한 문자열 길이를 구할 수 없다 (물론 `string.h` 파일 내의 `strlen` 함수를 사용해도 정확한 길이를 계산할 수 있다). 
 


```c
    #include <stdio.h>

    void copy_string(char *a, const char *b){
        while(*a++ = *b++);
    }

    int len_string(const char *a){
        int count=0;
        while(*a++) count++;
        return count; 
    }

    int main(){
        char a[6];
        char b[6]="Apple";

        copy_string(a,b);

        printf("%s\n",a);
        printf("%s\n",b);

        printf("%d", len_string(a));

        return 0; 
    }
```

```
Apple
Apple
5
```




Additionally, when the `sizeof` function is used directly on a pointer variable, it always returns a value of `4B`. This is because the size of the pointer variable represents `4B`, which is the size to represent the memory address, and it should be understood that the size of the pointer variable itself is returned regardless of the data type.
(It may appear as 8B depending on the operating system.)


추가적으로 `sizeof` 함수를 직접적으로 포인터 변수에 사용하게되는 경우 항상 `4B` 값을 반환한다. 이는 포인터 변수의 크기가 메모리 주소를 나타내기 위한 크기인 `4B`를 나타내기 때문이며, 데이터 타입과 상관없이 포인터 변수 자체의 크기를 반환함을 이해해야한다. 
(시스템 운영체제에 따라 8B로 나타나기도 한다)


```c
    #include <stdio.h>

    int main(){
        int a[10];
        int *pa = a;
        char *pb; 
        float *pc;

        printf("%d\n", sizeof(a)/sizeof(a[0]));
        printf("%d\n", sizeof(a));
        printf("%d\n", sizeof(pa));
        printf("%d\n", sizeof(pb));
        printf("%d\n", sizeof(pc));

        return 0; 
    }
```

```
10
40
8
8
8
```


[op]: https://mbyun1420.github.io/four-arithmetic-operations/