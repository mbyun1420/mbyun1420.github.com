---
layout: post
title:  "[C] Numeral System 기수법"
author: software-engineer
categories: [ C ]
image: assets/images/candcplus.png
---


Before introducing the representative data types used in the C language, one thing to look at is numeral system. Numeral system is a method of expressing numbers. In addition to the decimal numbers that people use in real life, there are binary, octal, and hexadecimal numbers. The binary number is a notation method only uses 0 and 1 to represent a number. If a decimal number is expressed in binary, it is expressed as 1111(2) for 15 and 100(2) for 8. The fact that all numbers can be expressed as 0 and 1 by using the binary number is in line with the operating principle of the computer, so we need to take a closer look.  
The CPU(Central Processing Unit) of a computer is an integrated circuit composed of many transistors, and a vacuum tube, a computer before the transistor, uses 0 and 1 to express the flow of electricity and no flow. That is, if you pay attention to the fact that the state(current on/off) of the computer's HW(Hardware) can be expressed as a binary signal, the reason why the machine language consists of only 0 and 1 can be guessed.  
In order to express arbitrary data as 0 and 1, the corresponding capacity is required. The unit of the capacity is called `bit`, and it is easy to think of 0 and 1 as the number of expressible digits. One unit is called a `bit`, 4 units are called 1 `nibble`, and 8 units are called 1 `byte` or 1 `B` (8 bit = 1 byte = 1 B). For example, if 1 B = 1 bit = ㅁㅁㅁㅁㅁㅁㅁㅁ and 00000000 is set to mean 0, 11111111 means 255. That is, 2^8 states can be expressed.


C언어에서 사용하는 대표적인 Data type을 소개하기 이전에 살펴볼 것은 기수법이다. 기수법은 수를 표현하는 방법으로 사람이 일반적으로 실생활속에서 사용하는 10진수외에도 2진수, 8진수, 16진수 등이 있다. 2진수은 0과 1만을 사용하여 수를 표현하는 기수법이다. 10진수 숫자를 2진수으로 표현하면 15의 경우 1111(2), 8의 경우 100(2)와 같이 표현된다. 2진수을 활용하면 모든 숫자를 0과 1로 표현할 수 있다는 점이 컴퓨터의 작동원리와 맞닿아 있기 때문에 조금 더 살펴 볼 필요가 있다.  
컴퓨터의 CPU(Central Processing Unit)는 수 많은 트랜지스터로 이루어진 집적회로이고, 트랜지스터 이전의 컴퓨터인 진공관은 0과 1을 사용하여 전기가 흐르고, 흐르지 않고를 표현했다. 즉 컴퓨터의 HW(Hard ward)의 상태(전류 On/Off)가 이원화된 신호로 표현가능 하다는 점에 주목하면 기계어가 0과 1로만 이루어진 이유를 짐작할 수 있다.   
임의의 데이터를 0과 1로 표현하려면 그에 따른 용량이 필요한데 그 단위를 `bit`라고 하며 0과 1을 표현가능한 자리수라고 생각하면 쉽다. 하나의 단위를 `bit`, 4개 단위를 1 `nibble`, 8개 단위를 1 `byte` 혹은 1 `B` 라고 한다 (8 bit = 1 byte = 1 B). 예를 들어 1 B = 1 bit = ㅁㅁㅁㅁㅁㅁㅁㅁ 이고 00000000 에 아라비아 숫자 0을 의미하도록 설정하면, 11111111 은 255를 의미한다. 즉 2^8개의 상태를 표현할 수 있다.


When debugging through an IDE(Integrated Development Environment) such as Visual stdio, data addresses sometimes appear in hexadecimal. This is because the expression length is too long to express everything in binary numbers on a computer, so it is expressed shortly in hexadecimal by combining 4 bits each. In the case of a hexadecimal number, the numbers from 0 to 15 are expressed as a single number. 0 to 9 are used as they are, and 10 to 15 are replaced with letters from A to F. Computers use hexadecimal numbers for binary representation, not for decimal numbers, so 4 binary digits are mapped to 1 hexadecimal representation. For example, ㅁㅁㅁㅁㅁㅁㅁㅁ 8 digits of binary numbers are corresponded to a single hexadecimal number, each with 4 digits in which the range of expressions can be expressed is 16 (0~15) (11111111(2) -> FF(16) ). When hexadecimal is used, the notation '0x' is used in front of the number to distinguish it from the decimal and binary representations.  
In the case of using octal numbers, 3 bits are grouped and the state corresponding to 0 to 7 corresponds to 1 digit (100(2) -> 10(8) ). The octal representation is sometimes expressed as 010 with an indicator of 0.  
The `printf` function makes it possible to express these various notations using format specifiers. Format specifiers corresponding to each notation are shown in the table below.


Visual stdio와 같은 IDE(Integrated Development Environment)를 통해 디버깅을 수행하다보면, 데이터 저장된 주소가 16진수으로 나타난 경우가 있다. 이는 컴퓨터에서 모든 것을 2진수으로 표현하자니 표현 길이가 너무 길어 이를 4 bit 씩 묶어서 16진수으로 짧게 표현하기 때문이다. 16진수의 경우 0~15까지의 수가 하나의 수로 표현되는데 0~9까지는 그대로 사용하고 10~15까지를 A에서 F까지의 문자로 대치하여 사용한다. 컴퓨터에서는 16진수을 10진수 수 표현을 위해 사용하는 것이 아니라, 2진수 표현을 위해 사용하기 때문에 2진수 4자리를 1자리의 16진수 표현으로 대응시킨다. 예를들어 ㅁㅁㅁㅁㅁㅁㅁㅁ 2진수 수 8자리는 표현 가능한 상태범위가 16개(0~15)가 되는 4자리씩 끊어서 각각 한자리의 16진수 수로 대응된다 ( 11111111(2) -> FF(16) ). 16진수을 사용할 경우 이를 10진수, 2진수 표현과 분별하기 위해 숫자 앞에 '0x'라는 표기를 병행하기도 한다.  
8진수을 사용하는 경우에는 3bit를 묶어서 0에서 7까지에 해당하는 상태를 한 자리에 대응한다 ( 100(2) -> 10(8) ). 8진수 표현은 0이라는 지시자를 붙여 010 과 같이 표현하기도 한다.
`printf` 함수는 이런 다양한 기수법에 대해 서식 지정자를 활용해 표현 가능하게 했다. 각각의 기수법에 대응되는 서식 지정자는 아래 표와 같다. 




| Syntax |  Meaning   | 의미|
|:---:   |:---:   | :---:   |
| %d    |	Decimal Number | 10진수|
| %x	|   Hexadecimal Number| 16진수 | 
| %#x   |	Hexadecimal Number + Numeral Index | 16진수 + 기수법 |
| %o	|   Octal Number | 8진수 | 
| %#o	|   Octal Number + Numeral Index | 8진수 + 기수법|  



```c
    #include <stdio.h>

    int main(void){
        int i=427;

        printf("%d\n", i);
        printf("%x\n", i);
        printf("%X\n", i);
        printf("%#x\n", i);
        printf("%#X\n", i);
        printf("%o\n", i); 
        printf("%#o\n", i);

        return 0;
    }   
```


```
427
1ab
1AB
0x1ab
0X1AB
653
0653

```


