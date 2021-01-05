---
layout: post
title:  "[C] Data Structure, 자료구조"
author: software-engineer
categories: [ C ]
image: assets/images/candcplus.png
---

Data structure in the dictionary sense is to express, store, and organize data in order to efficiently process data. In designing a software program, selecting an appropriate data structure in terms of implementation difficulty or dependence on the final result is an item that should be prioritized over others. The reason why data structures are always intensively treated in coding tests and evaluations is also based on this importance, and most languages provide basic data structures as standard libraries.


사전적인 의미의 자료구조는 자료에 대한 처리를 효율적으로 수행하기 위해 자료를 표현하고 저장하고 정리하는 것이다. 프로그램의 설계함에 있어 구현의 난이도나 최종 결과물에 대한 의존성 측면에서  적절한 자료구조를 선택하는 것은 다른 것들보다 우선시되어야할 항목이다. 코딩시험 및 평가에에서 항상 집중적으로 자료구조를 다루는 이유도 이러한 중요성에 기반하고 있으며 대부분의 언어는 기본적인 자료구조를 표준 라이브러리화하여 제공하고 있다. 


Data structures can be classified according to various criteria. For example, it can be divided into simple structure, linear structure, and non-linear structure according to the relationship between data. In addition, data structures can be divided according to implementation or type.


자료구조는 여러가지 기준으로 분류할 수 있다. 예를 들어, 자료간의 관계에 따라 단순구조, 선형구조, 비선형구조로 나눌 수 있다. 또한 구현이나 형태에 따라서도 자료구조를 나눌 수 있다. 


|Simple structure | Linear structure | Nonlinear structure |
|:---:   |:---:   | :---:   | 
| Int | Array | Tree | 
| Float | Linked List | Graph |
| Char | Queue | |
| Array | Stack | |
| | Deque | |



|단순 구조 | 선형 구조 | 비선형 구조 |
|:---:   |:---:   | :---:   | 
| 정수 | 순차 리스트 | 트리 | 
| 실수 | 연결 리스트 | 그래프 |
| 문자 | 큐 | |
| 문자열 | 스택 | |
| | 데크 | |



| Implementation view | Type view | 
|:---:   |:---:   |
| Array | Stack |
| Tuple | Queue |
| Linked list | Deque|
| Hash table | Graph |
|  | Tree |



| 구현에 따라 | 형태에 따라 | 
|:---:   |:---:   |
| 배열 | 스택 |
| 튜플 | 큐 |
| 연결 리스트 | 데크|
| 해쉬 테이블 | 그래프 |
|  | 트리 |



References 
1. https://andrew0409.tistory.com/148
2. https://ko.wikipedia.org/wiki/%EC%9E%90%EB%A3%8C_%EA%B5%AC%EC%A1%B0