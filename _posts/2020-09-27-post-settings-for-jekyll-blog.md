---
layout: post
title:  "Post settings for jekyll blog 지킬 블로그 게시글 설정"
author: software-engineer
categories: [ Jekyll ]
image: assets/images/jekyll-logo.png
tags: [sticky, featured]
---

Jekyll theme blog declares prior information about the article at the heading of the document. The pre-declaration information includes `layout`, `title`, `author`, `categorie`s, and representative `image`. In addition, the position of the first screen of the post can be assigned with the `tag` information provided by this blog theme `Mundana Jekyll Theme`.

지킬 테마 블로그는 문서의 머리말에 글에 대한 사전정보를 선언한다. 사전 정보에는 레이아웃, 제목, 저자, 카테고리, 대표이미지 등이 포함된다. 또한 이 블로그 테마 `Mundana Jekyll Theme`에서 제공하는 `tag` 정보로 게시글의 첫 화면 위치를 할당할 수 있다. 


```
---
layout: Type of article 글의 종류
title:  "Title displayed 보여지는 제목"
author: author name 저자 이름
categories: [ category 1, category 2 ]
image: url 주소
tag: tag information 태그 정보
---
```


The `featured` tag is a mark for the article highlighted on the blog, and the `sticky` tag is the assignment for the central post on the first screen.  
`featured` 태그는 블로그에서 강조하는 글에 대한 표식이며 `sticky` 태그는 첫 화면 중앙 게시글에 대한 할당이다. 

### Example  
```
---
layout: post
title:  "Post settings for jekyll blog 지킬 블로그 게시글 설정"
author: youn
categories: [ Jekyll ]
image: assets/images/jekyll-logo.png
---

---
layout: post
title:  "Powerful things you can do with the Markdown editor"
author: jane
categories: [ Jekyll, tutorial ]
image: https://images.unsplash.com/photo-1528784351875-d797d86873a1?ixlib=rb-1.2.1&auto=format&fit=crop&w=750&q=80
tags: [summer]
---

---
layout: post
title:  "The first mass-produced book to deviate from a rectilinear format"
author: sal
categories: [ tutorial ]
image: assets/images/17.jpg
tags: [featured]
---

---
layout: post
title:  "Markdown Example"
author: jane
categories: [ Jekyll, tutorial ]
image: assets/images/6.jpg
tags: featured
---

---
layout: post
title:  "Could we reinvent the charm of old cities"
author: jane
categories: [ Jekyll, tutorial ]
image: assets/images/home.jpg
tags: [sticky]
---
```
