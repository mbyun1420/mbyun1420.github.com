---
layout: post
title:  "Markdown mathematic formulars 마크다운 수식"
author: software-engineer
categories: [ Markdown ]
image: https://upload.wikimedia.org/wikipedia/commons/4/48/Markdown-mark.svg
---

In articles which follow the Markdown format, mathematical formulars are expressed within the text or in block form. The basic form of expressing formulars are to place them between two dolor tags or between squre brackets. However, in the `post` template of this blog, the `$` tag is recognized as an expression. So, in the inline formular of the expression in the text, the `$` tag is applied to the thhe expression as in $\sqrt{3x-1}+(1+x)^2$. 


Markdown 형식을 따르는 글에서 수식 표현은 글 내에서 이루어지거나 블록 형태로 표현된다. 수식을 표현하는 기본 형태는 두개의 달러기호 사이 혹은 대괄호 사이에 입력하는 것이다. 반면, 하나의 달러기호로 수식을 표현하는 것은 본문 내 달러기호와의 혼용을 피하기 위해 지양된다. 하지만 이 블로그의 `post` template에서는 `$` 기호가 수식표현으로 인식된다. 그래서 본문 내 인라인 형태의 수식 표현은 $\sqrt{3x-1}+(1+x)^2$ 과 같이 수식 표현에 `$` 태그를 적용한다.


$$
\sqrt{3x-1}+(1+x)^2
$$


### Greek letters 그리스 문자

Syntax 입력에 있어서 태그는 생략한다  



| Output               | Syntax              | Output               | Syntax              |  
|:---:                 |:---:                |:---:                 |:---:                |  
| $A$	               | A                   | $B$	                | B                   |  
| $\alpha$	           | \alpha              | $\beta$	            | \beta               |  
| $\gamma$	           | \gammma             | $\Gamma$             | \Gamma              |  
| $\pi$                | \pi                 | $\Pi$	            | \Pi                 |  
| $\phi$               | \phi                | $\Phi$	            | \Phi                |  
| $\varphi$	           | \varphi             | $\theta$	            | \theta              |  



### Sinesoidal function 삼각함수


| Output | Syntax    | Output | Syntax   |  
|:---:   |:---:   |:---:   |:---:     |  
| $\cos$ | \cos | $\sin$ | \sin |  


### Mathematical symbols 수학 기호 

| Output | Syntax    | Output | Syntax   |
|:---:   |:---:   |:---:   |:---:     |
| $\lim$ | \lim | $\exp$ | \exp |
| $\to$ | \to | $\infty$ | \infty |
| $\equiv$ | \equiv | $\bmod$ | \bmod |
| $\times$ | \times | $\sum$ | \sum |
| $\prod$ |	\prod | $\coprod$ |	\coprod |
| $\bigoplus$ |	\bigoplus | $\bigotimes$ | \bigotimes |
| $\bigodot$ | \bigodot | $\bigcup$ |	\bigcup |
| $\bigcap$ | \bigcap | $\biguplus$ |	\biguplus |
| $\bigsqcup$ | \bigsqcup | $\bigvee$ |	\bigvee |
| $\bigwedge$ |	\bigwedge | $\int$ | \int |
| $\oint$ |	\oint | $\iint$	| \iint |
| $\iiint$ | \iiint | $\idotsint$ |	\idotsint |
| $a’$ | a` | $a^{\prime}$ | a^{\prime} |
| $a’’$ | a’’ | $\hat{a}$ |	hat{a} |
| $\bar{a}$ | \bar{a} | $\grave{a}$ | \grave{a} |
| $\acute{a}$ |	\acute{a} | $\dot{a}$ | \dot{a} |
| $\ddot{a}$ | \ddot{a} | $\not{a}$ | \not{a} |
| $\mathring{a}$ | \mathring{a} | $a’’’$ | a’’’ |
| $\overline{aaa}$	| \overline{aaa} | $\check{a}$ | \check{a} |
| $\vec{a}$ |	\vec{a} | $\underline{a}$ |	\underline{a} |
| $\overleftarrow{AB}$ | \overleftarrow{AB} |$\overrightarrow{AB}$ | \overrightarrow{AB} |
| $\pm$ |	\pm | $\mp$	 | \mp | 
| $,$	| , | $:$ |	: |
| $;$ |	; | $!$ |	! |
| $\dots$ |	\dots | $\ldots$ |	\ldots |
| $\cdots$ |	\cdots |$\vdots$ |	\vdots |
| $\ddots$ |	\ddots |$\color{red}x$ |	\color{red}x |


### Mathematical expression 수식

| Output | Syntax    | Output | Syntax   |
|:---:   |:---:   |:---:   |:---:     |
| $k_{n+1}$ | k_{n+1} | $n^2$ |	n^2 |
| $k_n^2$ |	k_n^2 | $\frac{n!}{k!(n-k)!}$ |	\frac{n!}{k!(n-k)!} |
| $\binom{n}{k}$ | \binom{n}{k} | $\frac{\frac{x}{1}}{x - y}$ | \frac{\frac{x}{1}}{x - y} |
| $^3/_7$ | ^3/_7 | $\sqrt{k}$ | \sqrt{k} |
| $\sqrt[n]{k}$ | \sqrt[n]{k} | $\sum_{i=1}^{10} t_i$ | \sum_{i=1}^{10} t_i |
| $\int y, \mathrm{d}x$	| \int y, \mathrm{d}x |$\int y \mathrm{d}x$ |	\int y \mathrm{d}x |
| $\int\limits_a^b$	 | \int\limits_a^b | $\int_0^\infty \mathrm{e}^{-x},\mathrm{d}x$ | \int_0^\infty \mathrm{e}^{-x},\mathrm{d}x | 
| $\sum_{\substack{0<i<m , 0<j<n}} P(i, j)$ | \sum_{\substack{0<i<m\0<j<n}} P(i, j) |  


### Brackets 

| Output | Syntax    | Output | Syntax   |
|:---:   |:---:   |:---:   |:---:     |
| $(a)$ |	(a) | $[a]$	| [a] |
| ${a}$	| {a} | $\langle f \rangle$ |	\langle f \rangle |
| $\lfloor f \rfloor$ |	\lfloor f \rfloor | $\lceil f \rceil$	| \lceil f \rceil |
| $\ulcorner f \urcorner$ |	\ulcorner f \urcorner |


### Reference

https://csrgxtu.github.io/2015/03/20/Writing-Mathematic-Fomulars-in-Markdown/