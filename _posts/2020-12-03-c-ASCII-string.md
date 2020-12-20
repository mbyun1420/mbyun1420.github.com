---
layout: post
title:  "[C] ASCII, String 문자열"
author: software-engineer
categories: [ C ]
image: assets/images/candcplus.png
---


ASCII is easy to understand if you think of it as a code assignment table for letters. Each letter is assigned a numeric value and uses 1B (8 bit) memory. If this is expressed in hexadecimal, the character `1` can be matched as `0x31`. ASCII codes consist of alphabets, numeric characters, and control characters, and are defined in ascending order. For table of ASCII codes, refer to [Table][Linkh]. 


ASCII는 글자들의 코드 배정표라고 생각하면 쉽게 이해할 수 있다. 각각의 글자들은 숫자 값이 할당되어 있으며, 1B (8 bit) 메모리를 사용한다. 이를 16진수로 표현하면 글자 `1`의 경우 `0x31` 과 같이 대응할 수 있다. ASCII 코드는 영문, 숫자 그리고 제어문자로 이루어져 있으며 오름차순으로 정의되어 있다. ASCII 코드 표는 [Table][Linkh]를 참고하면 된다. 




```c
    #include <stdio.h>

    int main(void){
        char i='A';

        printf("%c\n", i); 
        printf("%c\n", 65); 

        return 0;
    }
                
```


```
A
A
```



The decimal number corresponding to `A` is 65. If you print this using `%c`, the `char` format specifier, you can see that `A` is output in the same way.  
`A`에 해당하는 10진수 숫자는 65이다. 이를 `char` 서식 지정자인 `%c`를 사용해서 출력하면 동일하게 `A`가 출력됨을 알 수 있다. 


In the case of a string, it is a set made of several letters, and it is an arrangement of letters. Strings are created by enumerating the letters between " ". It should be noted that in the case of strings defined in the form of " ", `NULL` characters are always included at the end. Therefore, 'A' takes up 1B of space, but "A" is defined as a string, so it takes up 2B of space, and `NULL` is included at the end.


문자열의 경우 여러 글자들이 모여 만들어진 집합이며, 글자들의 배열이다. 문자열은 " " 사이에 글자들을 열거해 만든다. 주의해야할 점은 " " 형태로 정의한 문자열의 경우 항상 마지막에 `NULL` 문자가 포함된다는 점이다. 따라서 'A' 는 1B의 용량을 차지하지만 "A" 는 문자열로 정의되었기 때문에 2B의 용량을 차지하며 마지막에 `NULL`이 포함되어 있다. 



```c
    #include <stdio.h>

    int main(void){
        
        printf("%c%c%c%c\n", 'a','b','c','d'); 
        printf("%s\n", "abcd"); 

        return 0;
    }
                
```

```
abcd
abcd

```



[Linkh]: https://dojang.io/mod/page/view.php?id=740