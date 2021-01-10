---
layout: post
title:  "[C] DFS(Depth First Search) 깊이 우선 탐색"
author: software-engineer
categories: [ C ]
image: assets/images/candcplus.png
---

When explaining the [graph][graph] data structure, we learned about the path. The list of vertices that goes through to move from vertex `A` to `B` may be different, and thus each may have different path lengths. Typical methods for searching a path are `DFS` and `BFS`. In this article, I will focus on depth first search. In route search, if there is one length, the number of cases will also be one, but when a selectable branch is encountered, a criterion for decision is required. Depth first search is literally a search method that goes deep first. After proceeding to the end of the search in one direction, come back and search the other way. For example, when preparing for an exam for 4 subjects, DFS is a method of studying from volume 1 to the end and moving to volume 2. This is different from the BFS method in which all four books are studied one chapter at a time.


[그래프][graph] 자료구조에 대해서 설명할 때, 경로에 대해 학습했다. 정점 `A`에서 `B`로 이동하기 위해 거쳐가는 정점들의 리스트는 각기 다를 수 있으며, 그로인해 각기 다른 경로 길이를 가질 수 있다. 경로를 탐색하기 위한 대표적인 방법은 `DFS`와 `BFS`이다. 이번 글에서는 깊이 우선 탐색에 대해 집중적으로 알아보려 한다. 경로 탐색에 있어 길이 하나라면 경우의 수 또한 하나겠지만, 선택 가능한 분기점을 만나게 되면 결정을 위한 기준이 필요하게 된다. 깊이 우선 탐색은 말 그대로 깊게 먼저 들어가보는 탐색 방법이다. 한쪽 방향으로의 탐색을 끝까지 진행한 뒤, 다시 돌아와 다른 길을 탐색한다. 시험공부로 예를 들면, 4과목의 시험을 준비함에 있어 DFS의 경우 1권부터 끝까지 공부하고 2권으로 넘어가는 방식이다. 이는 4권을 모두 1장씩 공부하는 BFS 방식과는 다르다. 


In the case of DFS, which prioritizes depth, it follows a last-in-first-out structure when implemented in code. Therefore, DFS can be implemented with stack or recursive calls. DFS is mainly implemented with recursive calls because coding based on recursive calls is relatively short rather than using the stack data structure.


깊이를 우선하는 DFS의 경우 코드로 구현시 후입선출 구조를 따르게 된다. 따라서 DFS는 Stack과 재귀호출로 구현이 가능하다. Stack 자료구조를 활용하는 것 보다 재귀호출 기반으로 코딩하는 것이 상대적으로 길이가 짧기 때문에 주로 DFS는 재귀호출로 구현된다. 



```c
#include <stdio.h>
int G[6][6];
int visit[6];			
int s_arr[100];
int top;

void DFS(int x, int V) {		
	top = -1;
	visit[x] = 1;     
	s_arr[++top] = x;

	while (top != -1) {		
		int w;

		for (w = 1; w <= V; w++) {
			if (G[x][w] == 1 && visit[w] == 0) {				
				visit[w] = 1; 
                s_arr[++top] = w;				
				x = w;
				break;
			}
		}
		if (w > V) x = s_arr[top--];
	}
}

int main() {	
    int V, E;
	scanf("%d%d", &V, &E);

	for (int i = 0; i < E; i++) {
		int u, v;
		scanf("%d%d", &u, &v);
		G[u][v] = 1;
		G[v][u] = 1;
	}

	DFS(1, V);
}
```


```c
#include <stdio.h>

int G[6][6];
int visit[6];

void DFS(int v, int n){
    visit[v]=1;
    for(int w=1; w<=n; w++){
        if(visit[w]==0 && G[v][w]==1){
            DFS(w, n);
        }
    }
}

int main(){

    DFS(2,5);
    
    return 0;
}
```


In the code implementation method, node visits are checked using the `visit` array. In the case of a search for a graph, an `if` statement is included to distinguish between visited and non-visited vertices, and a `for` statement is used to search within a range. Basically, the two DFS algorithms above are designed to search from the smallest numbered vertex. The code for searching 2D arrays with 4 directions is as follows.


코드 구현 방법을 보면 `visit` 배열을 사용하여 노드 방문을 체크한다. 그래프에 대한 탐색의 경우, 방문했던 정점과 아닌 정점을 구분하기 위해  `if`문이 포함되고 범위 내 탐색을 위해 `for` 문이 사용된다.  기본적으로 위의 2개의 DFS 알고리즘은 번호가 작은 정점부터 탐색하도록 설계되어 있다. 2D 배열에 대해 4방위 방향성을가지고 탐색하는 경우의 코드는 아래와 같다. 



```c
#include <stdio.h>

int G2[10][10];
int visit[10][10];
int dx = {1 -1 0 0};
int dy = {0 0 -1 1};

void DFS2(int x, int y){
    visit[x][y]=1;
    for(int i=0; i<4; i++){
        int nx = x + dx[i];
        int ny = y + dy[i];
        if(visit[nx][ny]==0 && G2[nx][nx] != 1 ){
            DFS2(nx,ny);
        }
    }
}

int main(){

    DFS2(0,0);
    
    return 0;
}
```


Pictures related to the graph concept will be updated in the future.


먼 훗날 graph 개념과 관련된 그림들이 업데이트 될 예정임 


[graph]: https://mbyun1420.github.io/graph/