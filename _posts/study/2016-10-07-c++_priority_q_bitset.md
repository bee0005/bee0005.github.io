---
title: "[C++] Priority Queue & Bitset"
excerpt: "[10월 7일] C++ Priority Queue & Bitset 공부"
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - C++
  - Study
  - Priority Queue
  - Bitset

---
# Container Adapter

### `Priority Queue`
 - 선형 **Container Adapter** (Stack, Queue, Priority Queue, Bitset) 중 하나이다.
 - **priority_queue** 는 우선순위가 높은것부터 나온다(정수는 최대값이 먼저 나온다 - 내림차순)
 - 대표적으로 최대 **Heap** 이 있다.

```c++
  vector<int> a = {5,2,4,1,3};
  priority_queue<int> q1;

  for(int x : a) q1.push(x);
  while(!q1.empty()){
    cout << q1.top();
    q1.pop();
  }
  //5 4 3 2 1 출력(내림차순)
```

> 최대 힙을 최소 힙으로 바꾸고 싶을때
1. -을 붙여준다.
2. greater<int> 을 붙여준다.(functional include 할 것 )

```c++
  vector<int> a = {5,2,4,1,3};
  priority_queue<int> q1;

  for(int x : a) q1.push(-x);
  while(!q1.empty()){
    cout << -q1.top();
    q1.pop();
  }
```

-을 붙여 최대 힙을 최소 힙으로 바꿀때는 주의 사항이 있다.
-2^31인 경우 if( x == -x) 는 True가 된다.


```c++
  #include <functional>
  vector<int> a = {5,2,4,1,3};

  //int형, 내부 container을 무엇으로, 정렬방법
  priority_queue<int, vector<int>, greater<int> > q1;  

  for(int x : a) q1.push(x);
  while(!q1.empty()){
    cout << q1.top();
    q1.pop();
  }
  //0123456789 출력(오름차순)
```
> Stack에 Pair을 사용 하는 방법이다.

##### `Priority Queue`의 주요함수
 - **push()** : 원소를 추가한다.
 - **pop()** : 원소를 제거한다.
 - **top()** : 제일 앞의 값을 가져온다.
 - **size()** : 원소의 개수를 리턴한다.
 - **empty()** : 비어있는지 확인한다. 비어 있지 않으면 0을 출력한다.

```
   연습문제(Baekjoon)
     1927_최소합
```


### `Bitset`
  - 선형 **Container Adapter** (Stack, Queue, Priority Queue, Bitset) 중 하나이다.
  - **Bitset** 은 **vector<bool>** 형을 생각하면 된다. 단, Bool은 True/False를 저장하는데 1byte를 사용한다.
  - **Bitset** 은 **1bit** 만을 이용하기 때문에 효율적이다.
  - **Bitset** 은 *and, or, not* 등의 연산이 가능하다.
  - **Bitset** 에서 중요한 것은 *bitset<변수>* 는 안된다. 정확한 값이 들어가야 한다.

맨 처음 반드시 **bit** 의 크기를 명시해야 한다.

```c++
  #include <bitset>
  bitset<8> b1;            //0,0,0,0,0,0,0,0
  //88을 2진수로 바꿔준다.
  bitset<10> b2(88);       //0,0,0,1,0,1,1,0,0,0
  bitset<8> b3("10110");   //0,0,0,1,0,1,1,0

  //bitset도 container이기 때문에 [] 접근 가능
  for(int i = 0; i < b2.size(); i++)
    cout << b2[i];       //0,0,0,1,0,1,1,0,0,0
  //test 메소드는 []와 같은 의미이다
  for(int i = 0; i < b2.size(); i++)
      cout << b2.test(i);       //0,0,0,1,0,1,1,0,0,0
```

>bitset은 2진수와 비슷해서 &(and,or), ^(xor), ~(not), >>/<<(shift)가 가능하다.

```c++
  #include <bitset>
  bitset<10> b1(88);    //0,0,0,1,0,1,1,0,0,0
  bitset<10> b2(47);    //0,0,0,0,1,0,1,1,1,1

  cout << (b1 & b2);    //0,0,0,0,0,0,1,0,0,0
  cout << (b1 | b2);    //0,0,0,1,1,1,1,1,1,1
  cout << (b1 ^ b2);    //0,0,0,1,1,1,0,1,1,1
  cout << ~(b2);        //1,1,1,1,0,1,0,0,0,0    

  cout << (b1 << 2);    //0,1,0,1,1,0,0,0,0,0  
  cout << (b2 >> 2);    //0,0,0,0,0,0,1,0,1,1
```

>bitsetd는 set,reset, flip, test, all, any, none, count 함수가 존재한다.

```c++
  #include <bitset>
  bitset<10> b1(88);    //0,0,0,1,0,1,1,0,0,0
  cout << b1.test(4);   //1
  cout << b1.test(5);   //0

  b1.set(0);
  cout << b1;           //1,0,0,1,0,1,1,0,0,0
  b1.reset(1);
  cout << b1;           //0,0,0,1,0,1,1,0,0,0
  b1.flip(2);
  cout << b1;           //0,1,0,1,0,1,1,0,0,0

  b1.flip();
  cout << b1;           //1,0,1,0,1,0,0,1,1,1
  b1.set();
  cout << b1;           //1,1,1,1,1,1,1,1,1,1
  b1.reset();
  cout << b1;           //0,0,0,0,0,0,0,0,0,0

  bitset<10> b2(88);    //0,0,0,1,0,1,1,0,0,0
  cout << b2.all();     //False
  cout << b2.any();     //True
  cout << b2.none();    //False
  cout << b2.count();   //3
```

##### `Bitset`의 주요함수
  - **test()** : bit를 확인해준다.
  - **set()** : 0bit를 1bit로 바꿔준다. 인자를 주지 않으면 전체 bit에 적용
  - **reset()** : 무조건 0bit로 바꿔준다. 인자를 주지 않으면 전체 bit에 적용
  - **flip()** : 0bit는 1bit로 1bit는 0bit로 바꿔준다. 인자를 주지 않으면 전체 bit에 적용
  - **all()** : 모든 비트가 1인지 아닌지 출력한다. 1이 아니면 False
  - **any()** : 비트가 1인게 하나 이상인지 확인한다. 1개 이상이면 True
  - **none()** : 모든 비트가 0인지 아닌지 출력한다. 1개라도 존재하면 False
  - **count()** : 비트가 1인 것의 갯수를 출력한다.

#### 연습문제(Baekjoon)
 - [12813-이진수 연산](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/12813_%EC%9D%B4%EC%A7%84%EC%88%98%20%EC%97%B0%EC%82%B0.cpp)
