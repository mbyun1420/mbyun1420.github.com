---
layout: post
title:  "Markdown syntax"
author: youn
categories: [ Markdown ]
image: https://upload.wikimedia.org/wikipedia/commons/4/48/Markdown-mark.svg
---

This blog has a default layout which includes the stlye of first letter having 3ea. Also it is a `gitblog` type blog on `jekyll` structure. `Mundana` is being used as one of the `jekyll` theme. 


### Post layout 포스트 레이아웃

Declare layout information on forehead of `_posts` markdown  
 _posts 게시물 머리말에 layout 관련 정보를 선언  

+ layout: post  `follow post.html layout`
+ title: "Markdown syntax" `title of this article`
+ author: youn `author identification`
+ categories: Markdown `categories this article to Markdown` 
+ image: url `specifies the image to shown in home`


```
---
layout: post
title:  "Markdown syntax"
author: youn
categories: [ Markdown ]
image: https://upload.wikimedia.org/wikipedia/commons/4/48/Markdown-mark.svg
---
```

### Contents format 본문 서식  
+ Header 제목
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

+ Blockquotes 인용
    + Output
        > quotes 
    + Syntax  
        \> quotes  
  
  
+ Font style 글자 서식  
  
  

| Syntax              | Output              |
| ---------           | ---------           |
| \*italic\*          | *italic*            |
| \_italic\_          | _italic_            |
| \**bold\*\*         | **bold**            |
| \__bold\_\_         | __bold__            |
| \~~strikethrough\~\~| ~~strikethrough~~   |
| \<u>Underline\</u>  | <u>Underline</u>    |
  
  
  
+ Ordered list 리스트 (순서)
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

+ Unordered list 리스트 (순서x)
    + Output
        * uo-list
            - uo-list
                + un-list
    + Syntax  
        \* uo-list
            \- uo-list
                \+ un-list   

### Contents sytle 문서 서식
+ Table 테이블 
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
+ Table align 테이블 정렬
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

+ Code block 코드 블록
    + Output
    ```
    Code block contents
    ```
    + Syntax  
    \```
    Code block contents
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

+ Inline code block 인라인 코드 블록 
    + Output  
    `Inline code block`
    + Syntax  
    \`Inline code block\`
+ Horizontal line 수평선
    + Output
    ---  
    ***  
    ___  
    + Syntax  
    \---  
    \***  
    \___  

+ Footnotes 각주
    + Output  
    Footnote[^id]

    [^id]: footnote explaination  

    + Syntax  
    Footnote\[^id]

    \[^id]: footnote explaination

+ Summary 요약
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

+ External link 외부 링크
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

## etc 기타 서식
+ Image 이미지
    + Output
    ![image_example_1]({{ site.baseurl }}/assets/images/8.jpg)
    ![image_example_2][image_link]

    [image_link]: {{ site.baseurl }}/assets/images/8.jpg
    + Syntax
    \![image_example_1]({{ site.baseurl }}/assets/images/8.jpg)
    \![image_example_2][image_link]

    \[image_link]: {{ site.baseurl }}/assets/images/8.jpg

+ Video 비디오 
<p><iframe style="width:100%;" height="315" src="https://www.youtube.com/embed/Cniqsc9QfDo?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe></p>


