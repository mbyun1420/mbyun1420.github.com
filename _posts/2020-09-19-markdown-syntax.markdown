---
layout: post
title:  "Markdown syntax"
author: youn
categories: [ Markdown ]
image: https://images.unsplash.com/photo-1528784351875-d797d86873a1?ixlib=rb-1.2.1&auto=format&fit=crop&w=750&q=80
---

Markdown syntax; this blog default layout makes first letter has over 3ea to highlight it and this blog is a `gitblog` on `jekyll` structure. 


## Post layout | 포스트 레이아웃
Declare layout information on forehead of `_posts` markdown 
( _posts 게시물 머리말에 layout 관련 정보를 선언)
+ layout: post | follow post.html layout
+ title: "Markdown syntax" | title of this article
+ author: youn | author identification
+ categories: Markdown | categories this article to Markdown 
+ image: url | specifies the image to shown in `home`

```
---
layout: post
title:  "Markdown syntax"
author: youn
categories: [ Markdown ]
image: https://images.unsplash.com/photo-1528784351875-d797d86873a1?ixlib=rb-1.2.1&auto=format&fit=crop&w=750&q=80
---
```

## Contents format | 본문 서식
+ Header | 제목
    + Output
        # h1 
        ## h2
        ### h3
        #### h4
        ##### h5
        ###### h6
    + Syntax
    ``` 
    # h1 
    ## h2 
    ### h3
    #### h4
    ##### h5
    ###### h6
     ``` 
+ Blockquotes | 인용
    + Output
    > quotes 
    + Syntax
    \> quotes

+ | 이텔릭체
    + Output
    *이텔릭체* , _이텔릭체_
    + Syntax
+ | 두껍게 
    + Output 
    **두껍게**, __두껍게__
    + Syntax
    \**두껍게 \*\*, \__두껍게\_\_
+ | 취소선
    + Output
    ~~취소선~~
    + Syntax
    \~~취소선\~\~
+ | 밑줄 
    + Output
    <u>밑줄</u>
    + Syntax
    \<u>밑줄\</u>
+ Ordered list | 리스트 (순서)
    + Output 
    1. o-list
    1. o-list
    1. o-list
    2. o-list
    + Syntax
    \1. o-list
    \1. o-list
    \1. o-list
    \1. o-list
    \2. o-list
+ Unordered list | 리스트 (순서x)
    + Output
    * uo-list
        - uo-list
            + un-list
    + Syntax
   \* uo-list
        \- uo-list
            \+ un-list   

## | 문서 서식
+ Table | 테이블 
    + Output 
    
    Header 1 | Header 2
    --------- | ---------
    Content 1 | Content 3
    Content 2 | Content 4
    + Syntax
    ```
    Header 1  | Header 2
    --------- | ---------
    Content 1 | Content 3
    Content 2 | Content 4
    ```
+ Table align | 테이블 정렬
    + Output

    | Header 1 | Header 2 | Header 3 |
    | :-------- | :--------: | --------: |
    | Left | Center | Right |

    + Syntax
    ```
    | Header 1  | Header 2   | Header 3  |
    | :-------- | :--------: | --------: |
    | Left      | Center     | Right     |
    ```

+ Code block | 코드 블록
    + Output
    ```
    ```
    + Syntax
    \```
    Code block 
    \```
    + Code block style : c, java, xml, json 

    ```c
        void f()
        printf(%s, "이것은 c 코드 입니다");
        }
    ```
    \```c
    void f()
        printf(%s, "이것은 c 코드 입니다");
        }
    \`\`\`
+ Inline code block | 인라인 코드 블록 
    + Output 
    `Inline code block`
    + Syntax
    \`Inline code block\`
+ Horizontal line | 수평선
    + Output
    ---
    ***
    ___
    + Syntax
    \---
    \***
    \___
+ Footnotes | 각주
    + Output
    Footnote[^id]

    [^id]: footnote explaination
    + Syntax
    Footnote\[^id]

    \[^id]: footnote explaination
+ | 접기
    + Output 
    <detail><summary>Fold</summary>
    ```c
    pythonprint("hellow world!")
    ```
    </details>
    + Syntax
    \<detail><summary>Fold</summary>
    \```c
    pythonprint("hellow world!")
    \```
    \</details>


+ External link | 외부 링크
    + Output 
    [google](http://www.google.co.kr "hover:구글")
    [google][link1]
    
    [link1]: http://www.google.com/ "hover:구글"
    <mbyun1420@gmail.com/>
    + Syntax
    \[google](http://www.google.co.kr "hover:구글")
    \[google]\[link1]

        \[link1]: http://www.google.com/ "hover:구글"
    \<mbyun1420@gmail.com>

## etc | 기타 서식
+ Image | 이미지
    + Output
    ![image_example_1]({{ site.baseurl }}/assets/images/8.jpg)
    ![image_example_2][image_link]

    [image_link]: {{ site.baseurl }}/assets/images/8.jpg
    + Syntax
    \![image_example_1]({{ site.baseurl }}/assets/images/8.jpg)
    \![image_example_2][image_link]

    \[image_link]: {{ site.baseurl }}/assets/images/8.jpg

+ Video | 비티오 
<p><iframe style="width:100%;" height="315" src="https://www.youtube.com/embed/Cniqsc9QfDo?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe></p>


