---
layout: post
title:  "[C] Declaration of variables and functions 변수와 함수의 선언"
author: software-engineer
categories: [ C ]
image: assets/images/candcplus.png
---


When writing code based on the C language, variables or functions are used. These are declared with definitions, and they need to be understood because they have different behaviors depending on where and how they are declared. Variables can be divided into two types depending on the location of the declaration. The first is a global variable, and the other is a local variable. A global variable literally means a variable that can be referenced in all regions, and a local variable is a variable that can be referenced only in the region where the variable is declared.


C언어 기반으로 코드를 작성할 때 변수나 함수를 사용하게 된다. 이들은 정의와 함께 선언되는데, 선언되는 위치와 양식에 따라 다른 동작을 하기 때문에 이해할 필요가 있다. 변수의 경우 선언하는 위치에 따라 2가지 종류로 나눌 수 있다. 첫 번째는 전역변수이고, 다른 하나는 지역 변수이다. 전역변수는 말 그대로 전 지역에서 참조가능한 변수라는 의미이고, 지역 변수는 변수가 선언된 지역에서만 참조 가능한 변수이다. 


For example, variables defined outside the main statement are used as global variables, and all variables used in the main statement or inside functions or braces are used as local variables. If a global variable and a local variable are stored under the same variable name, when the variable is called from the declared local, the local variable is called first. If a local variable is not declared in the calling area, a search is performed to see if there is a match among global variables. In other words, if a variable with the same name exists in different layers, the activated layer value takes precedence.


예시를 들면, main 문 밖에 정의된 변수는 전역변수로 사용되고, main 문 혹은 함수나 중괄호 내부에서 사용되는 변수들은 모두 지역변수로 활용된다. 만약 전역변수와 지역변수를 같은 변수명으로 저장하게 되는 경우, 선언한 지역에서 변수를 호출하게 되면 지역변수를 우선적으로 호출하게 된다. 만약 호출하는 지역에서 지역변수가 선언되지 않았다면, 전역변수 중에 일치내역이 있는지 탐색을 수행한다. 다르게 말하면, 같은 이름의 변수가 서로다른 계층에 존재하게 된다면, 활성화 된 계층 값이 우선된다. 



```c
#include <stdio.h>

int g1;
int g2=5;

int main(){
    
    int g1=10;
    int g2=15;
    {
        int g1=20;
        printf("%d\n", g1);
        printf("%d\n", g2);
    }

    printf("%d\n",g1);

    {
        printf("%d\n",g1);
    }

    return 0;
}
```

```
20
15
10
10
```


Additionally, global variables are automatically initialized to 0 at initialization, and cannot be initialized through variable expressions (e.g. int a = b +1;). A variable expression can be used when initializing a local variable, and if an initial value is not specified, an arbitrary value is assigned.


부가적으로 전역변수는 초기화 시에 자동으로 0으로 초기화되며, 변수식을 통해 초기화 할 수는 없다 (e.g. int a = b +1;). 지역 변수는 초기화 시에 변수식을 사용할 수 있으며, 초기 값을 지정하지 않으면 임의의 값이 배정된다. 


The basic building blocks of functions are inputs, outputs, and operations. In the case of input, it means passing an argument, and the output means the return value. All other processes within the function correspond to operations. In the case of a function, input/output is not necessary, and when there is no input, it is expressed using a `void` type. On the other hand, the input can receive multiple values as arguments, but only one output should be returned (even when using the `Struct` type, one `Struct` is returned). Because it returns one output, the function follows the data type of the output.


함수의 기본적인 구성 요소는 입력, 출력, 그리고 작업이다. 입력의 경우 인수를 전달하는 행위를 의미하고 출력은 반환 값을 의미한다. 그 외 함수 내에서 이루어지는 모든 과정들이 작업에 해당한다. 함수의 경우 입/출력이 반드시 필요하지는 않고 입력이 존재하지 않을 때에는 `void` 타입을 사용하여 표현한다. 반면 입력은 여러 값을 인자로 받을 수 있지만 출력은 하나만을 반환해야한다 (`Struct` 타입을 사용하는 경우에도 하나의 `Struct`가 반환되는 것이다). 하나의 출력을 반환하기 때문에 함수는 출력의 데이터 타입을 따르게 된다. 


The writing method differs depending on where the function is defined. In principle, functions must be declared before the statement in which they are used. However, it does not have to be defined, and the type and name of the function can be specified in advance. In this case, the specified function does not need to use an exact argument. Also, arguments specified in functions operate independently even if they use the same names as arguments used in higher layers. To understand this, it is important to know that functions use the stack structure to store local variables. When a function is used, a stack frame for that function is created. All local variables used and declared are operated through this stack frame. When the function is called, the created stack frame is activated and all previous stacks are deactivated, so the active stack variable is always referenced.


함수가 정의되는 위치에 따라 작성 방식이 다르게 된다. 함수가 사용되는 구문 이전에 명시되는 것이 원칙이기 때문에, 함수는 미리 선언되어야 한다. 하지만 반드시 정의될 필요는 없으며 함수의 형태와 이름을 사전에 명시하면 된다. 이때 명시하는 함수는 정확한 인자를 사용하지 않아도 무방하다. 또한 함수에 명시된 인자는 상위 계층에서 사용하는 인자와 동일한 이름을 사용하더라도 독자적으로 작동된다. 이를 이해하기 위해서는 함수가 지역변수를 저장하는 용도로 스택구조를 활용한다는 것을 알아야한다. 함수가 사용되면 그 함수를 위한 스택 프레임이 생성된다. 사용 및 선언되는 지역변수들은 모두 이 스택 프레임을 통해 사용된다. 함수가 호출되면 만들어진 스택 프레임이 활성화되고 이전 스택들은 모두 비활성이 되어 항상 활성화된 스택의 변수가 참조된다. 


```c
#include <stdio.h>

int divide(int b, int a);

int add(int a, int b){
    int c= a + 2 * b;
    return c;
}

int main(){    
    int a=3;
    int b=5;

    printf("%d %d",add(b,a), divide(b,a));
    return 0;
}

int divide(int a, int b){
    int c = a/b;
    return c;
}
```

```
11 1
```
 
Pictures related to the stack concept will be updated in the future.


먼 훗날 stack 개념과 관련된 그림들이 업데이트 될 예정임 