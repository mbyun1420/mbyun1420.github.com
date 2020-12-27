---
layout: post
title:  "[C] Four arithmetic operations 사칙연산"
author: software-engineer
categories: [ C ]
image: assets/images/candcplus.png
---

In order to correctly perform the four arithmetic operations in the `c` language, it is necessary to understand the data types, operators, and operation precedence. Data types were discussed in [Data Type][Data Type]. Among the four arithmetic operations, the value and operation differ depending on the data type for division. In the case of the division operator, the operation between `float` is the same as the general division operation. However, when using the division operator for `int`, only the quotient is taken. In addition, `%` sign performs modulus operation, discarding the quotient and taking only the remainder, and only `int` can be used.


c언어에서의 사칙연산을 올바르게 수행하기 위해서는 자료형, 연산자, 그리고 연산 우선순위에 대한 이해가 필요하다. 자료형에 대해서는 앞선 [Data Type][Data Type] 에서 다루었다.  
사칙연산 중 나눗셈에 대해서 자료형에 따라 그 값과 연산이 달라지게 되는데, 나눗셈 연산자의 경우 실수 간 연산은 일반적인 나눗셈 연산과 동일하다. 하지만 정수 자료형에 나눗셈 연산자를 사용할 경우 몫만 취한다. 추가적으로 % 기호가 Modulus 연산을 수행하며 몫을 버리고 나머지만 취하게 되며 정수 자료형만 사용가능하다. 



|Operation | Syntax |
|:---:   |:---:   | 
|Addition | +    |
|Subtraction| -     |
| Multiplication | * |
| Division | /      |
| Modulus | %       |



Operator precedence 
- Among the unary and binary operators, the unary operator takes precedence. 
- Among the unary operators, they are calculated in the order close to the variable.
- Among the binary operators, multiplication and division take precedence over addition and subtraction, and are calculated from left to right.
    (cf. `=` direction of assignment through calculation is right->left)


연산자의 우선순위는 종류에 따라 달라지는데, 
- 단항 연산자와 이항 연산자 중에서는 단항연산자가 우선으로 작용한다 (Ex. sizeof(a), &a >> a*b, a/b, a%b). 
- 단항 연산자 중에서는 피연산자에 가까운 순서로 계산된다.
- 이항 연산자 중에서는 곱셈, 나눗셈이 덧셈, 뺄셈보다 우선되며, 좌에서 우로 계산된다. 
    (cf. `=` 연산을 통한 대입 연산 방향은 우->좌 )


The complex substitution operator follows the binary operator format, and itself becomes the operand.    
복합대입연산자는 이항연산자 형식을 따르며, 자기 자신이 피연산자가 된다.  
(a=a+1) == (a+=1) == (a++)



```
a *= b + 1 
a  = a * ( b + 1 )

a *= b += 1 
a  = a* (b+=1) = a * ( b = b + 1 )
```


The result of the operation varies depending on whether the increment/decrement operator is placed before or after. If it is located in the front, it first increments 1, and if it is located after, it performs the specified operation and then increments 1.  
증가 / 감소 연산자가 앞 / 뒤에 위치하느냐에 따라 연산의 결과가 달라진다. 앞에 위치하는 경우 먼저 1을 증가시키고 이후 연산을 수행하고 뒤에 위치하는 경우 지정 연산을 수행한 뒤 1을 증가시킨다.



```c
    #include <stdio.h>

    int main(){
        int a=10;

        printf("%d\n",a);
        printf("%d\n",a++);
        printf("%d\n",a);
        printf("%d\n",++a);
        

        return 0;
    }


```


```
10
10
11
12

```




[Data Type]: https://mbyun1420.github.io/b-data-type/