---
layout: post
title:  "[C] Data Type 자료형"
author: software-engineer
categories: [ C ]
image: assets/images/candcplus.png
---

Data type means the type of variables. Variables refer to an object to transfer or store a value as the code proceeds. In particular, since C is a programming language that can access memory addresses, it is important to set an appropriate type according to the type of data for efficient coding. Data types mainly used in C language are as follows.


자료형은 변수의 종류를 의미한다. 변수란 코드가 순차적으로 진행됨에 따라 값을 전달 혹은 저장하기 위한 객체를 의미한다. 특히 C언어의 경우 메모리 주소까지 접근 가능한 프로그래밍 언어이기 때문에 효율적인 코딩을 위해 데이터의 종류에 따라 적합한 타입을 설정하는 것이 중요하다. C언어에서 주료 사용하는 자료형은 다음과 같다. 



|Data Type | Volume(B) | Min Value | Max Value |
|:---:   |:---:   | :---:   | :---:   |
|char | 1 | 0 | 127 |
|signed char | 1 | -128 | 127 |
|unsigned char | 1 | 0 | 255 |
|signed short | 2 | -32768 | 32767 |
|unsigned short |2 | 0 | 65535 |
| (signed) int | 4 | -2147483648 | 2147483647 |
|unsigned int | 4 | 0 | 4294967295 |
|signed long | 4 | -2147483648 | 2147483647 |
|unsigned long | 4 |0 | 4294967295 |
|signed long long | 8 | -9223372036854775808 | 9223372036854775808 |
|unsigned long long | 8 | 0 | 18499744073709551615 |




|Data Type | Volume(B) | Min Value | Max Value |
|:---:   |:---:   | :---:   | :---:   |
| float | 4 | 3.4e-37 | 3.4e+38 |
| double | 8 | 1.7e-307 | 3.4e+308 |



The real data cannot be used in octal or hexadecimal format, and only decimal representation is allowed. Also, the real data is signed without the concept of unsigned. The basic type of integer is `signed int`, the basic type of character is `char`, and the basic type of real is `double`. I/O format specifier without a predetermined data type is recognized as a default data type. The corresponding format specifiers are as follows.


실수 자료형은 8진수나 16진수 형태로 사용할 수 없으며 10진수 표현만 허용한다. 또한 실수 자료형은 unsigned 개념 없이 signed만 존재한다. 정수 자료형의 기본 타입은 `signed int`, 문자 자료형 기본 타입은 `char`, 실수 자료형의 기본 타입은 `double` 이다. 정해지지 않은 입/출력은 default data type으로 인식된다. 이에 해당하는 서식 지정자는 아래와 같다. 



| Format Specifier | Data Type   |
|:---:   |:---:   | 
| %d | int, short | 
| %ld | long |
| %lld | long long int |
| %u | unsigned int |
| %f | float
| %lf | long double, double|
| %c | char|
| %s | string|
| %p | pointer| 



The last `%p` is a format specifier to the address of the variable. Also, the `%s` format specifier means a string.  
In the code below, `int i=427` means that the type of `i` is defined as `int`, and an integer 427 is assigned to this variable. Since the integer data type was used, the `i` variable allocates and uses the 4B memory area.

마지막 `%p` 의 경우 해당 변수의 주소 값을 입력/출력 하기 위한 서식 지정자이다. 또한 `%s` 서식 지정자는 문자열을 의미한다. 
아래 코드에서 `int i=427` 이라는 뜻은 `i` 의 자료형을 `int` 로 정의하며, 이 변수에 정수 427를 할당하겠다는 의미히다. 정수 자료형을 사용했기 때문에 `i` 변수는 4B의 메모리 영역을 할당 및 사용하고 있다. 




```c
    #include <stdio.h>

    int main(void){
        int i=427;
        double a=427.427427427427;

        printf("%d\n", i);
        printf("%f\n", a);
        printf("%lf\n", a);


        return 0;
    }   
```


```
427
427.427427
427.427427

```
