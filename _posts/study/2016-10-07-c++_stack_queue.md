---
title: "[C++] Stack & Queue"
excerpt: "[10월 7일] C++ Stack & Queue 공부"
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - C++
  - Study
  - Stack
  - Queue

---
# Container Adapter

### `Stack`
 - 선형 **Container Adapter** (Stack, Queue, Priority Queue, Bitset) 중 하나이다.
 - **Stack** 은 **FILO(First In Last Out)** 또는 **LIFO(Last In First Out)** 라고 불린다.
 - 내부 구현은 **Deque** 로 되어있다.(Defalut)

```c++
  //Default인 Deque로 만들어진 Stack이다
  stack<int> s;
  //List로 Stack을 만들기
  stack<int, list<int> > s2;

  //deque를 이용해 stack을 초기화 할 수 있다.
  deque<int> d = {1,2,3,4,5};
  stack<int> s3(d);
```

```c++
  stack<int> s;
  for(int i =0; i<5; i++) s.push(i);

  cout << s.size(); //5
  //4,3,2,1,0 출력
  for(int i =0; i<5; i++) {
      cout << s.top() << '\n';
      s.pop();    
  }

```


```c++
  stack<pair<int,int>> s;
  s.push(make_pair(1,2));
  s.push({3,4});
  s.emplace(5,6);
```
> Stack에 Pair을 사용 하는 방법이다.

##### `Stack`의 주요함수
 - **push()** : stack의 원소를 추가한다.
 - **pop()** : stack의 원소를 제거한다.
 - **top()** : stack의 제일 앞의 값을 가져온다.
 - **size()** : stack의 원소의 개수를 리턴한다.
 - **empty()** : stack가 비어있는지 확인한다. 비어 있지 않으면 0을 출력한다.

#### 연습문제(Baekjoon)
 - [10828-스택](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/10828_%EC%8A%A4%ED%83%9D.cpp)

### `Queue`
  - 선형 **Container Adapter** (Stack, Queue, Priority Queue, Bitset) 중 하나이다.
  - **Queue** 은 **FIFO(First In Fist Out)** 또는 **LILO(Last In Last Out)** 라고 불린다.
  - **Stack** 은 **top()** 뿐이지만 **Queue** 는 **front()** 와 **back()** 을 이용할 수 있다.
  - 내부 구현은 **Deque** 로 되어있다.(Defalut)

```c++
   //Default인 Deque로 만들어진 Queue이다.
   queue<int> q;
   //List로 Queue 만들기
   queue<int, list<int> > q2;

   //deque를 이용해 Quque를 초기화 할 수 있다.
   deque<int> d = {1,2,3,4,5};
   queue<int> q3(d);

```

```c++
  queue<int> q;
  for(int i =0; i<5; i++) q.push(i);

  cout << q.size(); //5

  //0 4
  //1 4
  //2 4
  //3 4
  //4 4
  for(int i =0; i<5; i++) {
      cout << q.front() << ' ' << q.back() << '\n';
      q.pop();    
  }

```

```c++
   queue<pair<int,int>> q;
   q.push(make_pair(1,2));
   q.push({3,4});
   q.emplace(5,6);
```
 > Queue에 Pair을 사용 하는 방법이다.

##### `Queue`의 주요함수
  - **push()** : queue의 원소를 추가한다.
  - **pop()** : queue의 원소를 제거한다.
  - **front()** : queue의 제일 앞의 원소를 가져온다.
  - **back()** : queue의 제일 앞의 원소를 가져온다.
  - **size()** : queue의 원소의 개수를 리턴한다.
  - **empty()** : queue가 비어있는지 확인한다. 비어 있지 않으면 0을 출력한다.


#### 연습문제(Baekjoon)
 - [10845-큐](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/10845_%ED%81%90.cpp)
 - [1158-조세퍼스 문제](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/1158_%EC%A1%B0%EC%84%B8%ED%8D%BC%EC%8A%A4%20%EB%AC%B8%EC%A0%9C.cpp)
