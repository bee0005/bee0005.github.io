---
title: "[Graph] Dijkstra"
excerpt: "[11월 14일] Dijkstra's Algorithm 공부"
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - Graph
  - Dijkstra

---
# Dijkstra's Algorithm

## **깊이 우선 탐색**

`Dijkstra`는 **최단 경로 문제** 를 푸는 알고리즘 이다.

## 분석
 - 어떤 *Edge* 도 음수의 가중치를 갖지 않아야한다.
 - **Greedy Method** 를 사용한다.


```c++
  #include <iostream>
  #include <algorithm>
  #include <vector>
  #include <queue>
  #include <functional>
  #define INF 2147483647

  using namespace std;

  typedef pair<int,int> INT_PAIR;
  vector<INT_PAIR>* vertex;
  bool* visited;
  int* dis;

  void dijkstra(int start){
    priority_queue< INT_PAIR, vector<INT_PAIR>, greater<INT_PAIR> > pq;
    dis[start] = 0;
    pq.push({dis[start], start});


    while(!pq.empty()){
      INT_PAIR temp = pq.top();
      pq.pop();

      int v = temp.second;
      int w = temp.first;
      if(visited[v]) continue;
      visited[v] = true;

      for(int i=0; i< vertex[v].size(); i++){
        int to_v = vertex[v][i].first;
        int to_w = vertex[v][i].second;
        if(!visited[to_v] && dis[to_v] > dis[v] + to_w){
          dis[to_v] = dis[v] + to_w;
          pq.push({dis[to_v], to_v});
        }
      }
    }
  }

  int main(){
    int v,e,start;
    int f,t,w;
    cin >> v >> e >> start;
    vertex = new vector<INT_PAIR>[v+1];
    visited = new bool[v+1];
    dis = new int[v+1];
    fill(visited, visited+v+1, false);
    fill(dis, dis+v+1, INF);
    while(e--){
      cin >> f >> t >> w;
      vertex[f].push_back({t,w});
    }
    dijkstra(start);
    for(int i=1; i<=v; i++){
      if(dis[i] == INF)   cout << "INF\n";
      else cout << dis[i] << '\n';
    }
    return 0;
  }

```

#### 연습문제(Baekjoon)
  - [1753-최단경로](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/1260_DFS%EC%99%80%20BFS.cpp)
