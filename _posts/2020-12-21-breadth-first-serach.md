---
layout: post
title:  "[C] BFS(Breadth First Search) 너비 우선 탐색"
author: software-engineer
categories: [ C ]
image: assets/images/candcplus.png
---


In this article, I will focus on breadth first search. BFS is a search algorithm that proceeds in the form of an octopus when the list of vertices going from vertex `A` to `B` is different. After visiting each of the next depth vertices from the starting vertex, the adjacent vertices are visited again starting with the visited vertex. As an analogy, unlike DFS, which visits one of the city's tourist attractions and moves to the next one, it is a navigation method that goes back to the second floor of all tourist attractions after going to the first floor of every tourist attraction in the city. If the information you are looking for is the lowest level of tourist attractions, BFS is the most suitable. In other words, BFS is a very efficient search method in that it guarantees the minimum distance. BFS has a first-in-first-out structure, and because queues also have a first-in-first-out structure, BFS is implemented based on a queue.


이번 글에서는 깊이 우선 탐색에 대해 집중적으로 알아보고자 한다. BFS는 정점 `A`에서 `B`로 이동하기 위해 거쳐가는 정점들의 리스트는 각기 다를 때 문어발 형식으로 나아가는 탐색 방법이다. 시작 정점에서 다음 깊이 정점을 모두 각각 방문하고 나서, 방문했던 정점을 시작으로 다시 인접 정점을 방문한다. 비유하자면, 도시의 관광명소 한 곳을 모두 들러보고 다음 관광명소로 이동하는 DFS 와는 달리, 도시의 모든 관광명소의 1층을 각각 다녀오고나서야 다시 모든 관광명소의 2층을 다녀오는 탐색 방법이다. 만약 찾고자 하는 정보가 관광명소 중 가장 낮은 층의 관광명소를 찾고자한다면, BFS가 가장 적합하다. 즉 최소거리를 보장한다는 점에서 BFS는 굉장히 효율적인 탐색방법이다. BFS는 선입선출구조를 가지고, 큐 또한 선입선출 구조를 가지기 때문에 BFS는 큐를 기반으로 구현된다. 


The BFS implementation code queues the visited vertices in order, pulls out data one by one from the queue, and visits the next vertex. This process continues until the queue becomes empty because no data is accumulated in the queue. And it is implemented through the `while` statement, and the search scope is set through the `for` statement.


BFS 구현 코드는 방문 정점들을 순서대로 큐에 담고, 큐에서 데이터를 하나씩 꺼내어 다음 정점을 방문하게 된다. 이 과정은 큐에 데이터가 쌓이지 않아 결국 큐가 공백이 될 때까지 진행된다. 이 과정은 `while`문을 통해 구현되고 `for`문을 통해 탐색 범위를 설정하게 된다. 



```c
#include <stdio.h>
int G[6][6];
int visit[6];			
int Q[50];
int top;
int rear; 
int D[50];
int P[50];

void BFS(int v, int V) {		
    front = -1;
    rear = -1;
    Q[++rear]=v;
    visit[v]=1;
    D[v]=0;

    while(front != rear){
        v = Q[++front];

        for(int w=1; w<=V; w++){
            if(visit[w]==0 && G[v][w]==1 ){
                visit[w]=1;
                Q[++rear]=w;
                D[w]=D[v]+1;
                P[w]=v;
            }
        }
    }
}

void BFS_d(int v, int V) {		
    front = -1;
    rear = -1;
    rear++
    Q[rear]=v;
    D[rear]=0;
    visit[v]=1;    

    while(front != rear){
        front++;
        v = Q[front];
        int d = D[front];

        for(int w=1; w<=V; w++){
            if(visit[w]==0 && G[v][w]==1 ){
                visit[w]=1;
                Q[++rear]=w;
                D[++rear]= d+1;
                P[w]=v;
            }
        }
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

	BFS(1, V);
}
```


In the example code above, the arrays `D` and `P` are additionally configured. In the case of the `D` array, it is configured to contain the depth information of the vertices that have passed as the BFS search is performed. In the case of the `P` array, the path information can be saved by storing the information of the immediately preceding vertex in the index of the array. The BFS code for 2D direction search is as follows.


위 예제코드에는 `D` 와 `P` 배열이 추가적으로 구성되어있다. `D` 배열의 경우 BFS 탐색을 수행함에 따라 지나간 정점의 깊이 정보를 담기 위해 구성되었고, `P` 배열의 경우 배열의 인덱스에 직전 정점의 정보를 저장함으로써 경로 정보를 저정할 수 있다. 2D 방향탐색을 위한 BFS 코드는 아래와 같다. 


```c
#include <stdio.h>
int G[10][10];
int visit[10][10];			
int Qx[100];
int Qy[100];
int top;
int rear; 
int D[100];
int P[100];
int dx = {1 -1 0 0};
int dy = {0 0 -1 1};

void BFS2(int x, int y, int n) {		
    front = rear = -1;
    rear++;
    Qx[rear]=x;
    Qy[rear]=y;
    visit[x][y]= 1;
    D[rear]=1;

    while(front != rear){
        front++;
        x = Qx[front];
        y = Qy[front];
        int d = D[front];
        for(int w=0; w<4; w++){
            int nx = x + dx[w];
            int nx = y + dy[w];
            if(visit[nx][ny]==1) continue;
            if(G[nx][ny]==0) continue;
            if(nx >=0 && nx <n && ny >=0 && ny < n ){
                visit[nx][ny]=1;
                rear++;
                Qx[rear]=nx;
                Qy[rear]=ny;
                D[rear]=s+1;
            }
        }
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

	BFS(0, 0, 10);
}
```