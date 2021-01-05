---
layout: post
title:  "[C] Structure, 구조체"
author: software-engineer
categories: [ C ]
image: assets/images/candcplus.png
---

Structures are mainly used when you want to collect and deal with various data types from declaring and using data types one by one. Structures are derived types created by combining basic data types, and have the same characteristics as they are classified as data types such as `int`, `char`, and `float`. Structures must first declare their shape/form, and this is called a `template`. After the `template` is created, the structure variable is declared using it. There are several ways to declare a structure and initialize variables. There are cases where only the template is defined and the initial value is defined later, the template and initialization are performed at once, and the anonymous structure is used without the name of the template. Initializers of all structures, including anonymous structures used with `typedef` functions, can be used only at the beginning, and after that, each element must be accessed and modified individually.


자료형을 하나씩 선언하여 사용하는 것에서 더 나아가 여러가지 데이터 타입을 모아서 다루고자 할때 구조체를 주로 사용한다. 구조체는 기본 자료형을 조합하여 만든 파생형이며 `int`, `char`, `float` 와 같이 자료형으로 분류되어 동일한 특성을 가진다. 구조체는 모양 / 양식을 우선적으로 선언해야하며 이를 `템플릿이`라고 부른다. `템플릿이` 만들어지면 이후 이를 이용하여 구조체 변수를 선언한다. 구조체를 선언하고 변수를 초기화하는 방법이 몇가지가 있다. 템플릿만 정의하고 초기값을 나중에 정의하는 경우, 템플릿과 초기화를 한번에 수행하는 경우, 템플릿의 이름없이 익명 구조체를 사용하는 경우가 존재한다. `typedef` 함수와 함께 사용되는 익명 구조체를 포함하여 모든 구조체의 초기화자는 맨 처음에만 사용 가능하며, 그 이후에는 각 요소에 개별로 접근하여 수정해야 한다. 


```c
#include <stdio.h>
struct s_a{
    int a; 
    char b;
};

struct s_b{
    int a;
    char b;
} x = {2, 'B'};

int main(){
    struct s_a y={1,'A'}; 

    printf("%d %c\n", y.a, y.b );
    printf("%d %c\n", x.a, x.b);
    
    return 0; 
}
```

```
1 A
2 B
```


Since structures have the same properties as data types, both the `*` operator and the `[]` array type can be used. In particular, when using the `*` operator to access an element in a structure, it can be accessed through the `->` operator.


구조체는 자료형과 동일한 성질을 가지기 때문에 `*` 연산자와 `[]` 배열형태 모두 사용가능하다. 특히 `*`연산자를 사용하여 구조체 내의 요소에 접근할 때에는 `->` 연산자를 통해 접근 가능하다. 


```c
#include <stdio.h>
struct s_a{
    int a; 
    int b;
} x={1,2};

int main(){
    
    struct s_a *p;
    struct s_a q[4];

    p = &x;
    
    (*p).a = 4;
    printf("%d\n",p.b);

    p->a = 27;
    printf("%d\n",p.b);

    printf("%d\n",q[3].b);
    q[3].b=27;
    printf("%d\n",q[3].b);

    return 0; 
}

```

```
4
27
0
27
```


Additionally, `typedef` are often used when using structures. It acts as a preprocessor and is easy to understand if you think of it as a nickname. It is mainly used when defining anonymous structures.

추가적으로 구조체를 사용할 때 `typedef`를 자주 사용한다. 선행처리기로써 역할하며 별명을 정한다고 생각하면 쉽게 이해할 수 있다. 익명구조체를 정의할 때 주로 사용된다. 


``` c
#include <stdio.h>
typedef struct
{
    int a;
    char b;
} s_e;


int main(){

    s_e st={4,'M'};

    printf("%d %c", st.a, st.b);

    return 0;
}

```

```
4 M
```