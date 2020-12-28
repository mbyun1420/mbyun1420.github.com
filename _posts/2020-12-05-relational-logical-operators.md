---
layout: post
title:  "[C] Relational, logical, and ternary operators 관계, 논리, 그리고 삼항연산자"
author: software-engineer
categories: [ C ]
image: assets/images/candcplus.png
---


In `c` language, `True / False` corresponds to non-zero and zero, respectively. Conditional expressions that judge `true/false` through operators are mainly used in `if`, `for`, and `while` statements, and are expressed through relational and logical operators. In the case of logical operators, it is mainly used to express the relationship between conditional expressions and comparison operators are used to compare values or to check whether they match. 


`c` 언어에서 `참/거짓`은 각각 0이 아닌 값과 0에 대응된다. 연산자를 통해 `참/거짓`을 판단하는 조건 식은 주로 `if`, `for`, `while` 문에서 활용되며, 관계 및 논리 연산자를 통해 표현된다. 비교 연산자는 값의 크기를 비교하거나 값의 일치 여부를 확인하기 위해 사용되고, 논리 연산자의 경우 조건 식 간의 관계를 표현하기 위해 주로 활용된다. 



|Operation | Syntax |
|:---:   |:---:   | 
| Equal to | ==    |
| Not equal|  !=     |
| Greater than or equal to  | >= |
| Greater than | >      |
| Less than or equal to  | <=      |
| Less than   |  <       |
 

|Operation | Syntax |
|:---:   |:---:   | 
| And | &&   |
| Or |  \|\|  |
| Not  | ! |


Ternary operators are classified as conditional expressions in the `c` language and are used for various purposes, and are mainly used when writing simple conditional expressions. The ternary operator consists of a conditional expression and two execution statements, and can be understood as a simple `if-else` statement.


삼항연산자는 `c` 언어에서 조건 식으로 분류되어 다양한 용도로 활용되며, 주로 간단한 조건식을 작성할때 사용된다. 삼항연산자는 조건식과 두개의 실행문으로 구성되어 있으며, 간단한 형태의 `if-else` 문으로 이해할 수 있다. 




```c
    #include <stdio.h>

    int main(){
        int win==1;
        int nc = (win==1)? 2: 0 ;
        printf("%d",nc);

        return 0;
    }


```

```
2
```