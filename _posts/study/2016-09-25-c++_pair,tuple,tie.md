---
title: "[C++] Pair / Tuple / Tie"
excerpt: "[9월 25일] C++  Pair / Tuple / Tie 공부"
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - C++
  - Study


---
# Pair / Tuple / Tie

### pair
 - 두 자료형 T1과 T2를 묶을 수 있다.
 - 항상 **두 개** 를 묶는다.

```c++
  pair<int, int> p1, p2;

  p1 = make_pair(10,20);
  p2 = pair<int, int>(30,40);
  pair<int, int> p3(50,60);
```

 `Pair`를 만드는 방법 3가지이다.

### Tuple
 - Pair와 같지만 **여러 개** 를 묶을 수 있다.
 - *#include<tuple>* 에 정의되어 있다.
 - `get`이라는 메소드를 이용해 index로 접근 가능하다.

```c++
  #include <tuple>
  tuple<int, int, int> t = make_tuple(1,2,3);
  for(int i=0; i<3; i++)
      cout << get<i>t << '\n';
```

 `Tuple`을 만들고 **get** 메소드를 이용해 인자에 접근한다.

### Tie
  - 변수를 묶어는 형태이다.
  - 변수값을 무시하고 싶을 때는 **ignore** 을 넣어준다.

```c++
  auto t = make_tuple(10,20,30);

  int x = get<0>t;
  int y = get<1>t;
  int z = get<2>t;
  //위의 코드와 아래 코드는 같은 의미이다.
  tie(x,y,z) = t;
  //ignore 사용하기
  tie(x,ignore,z) = t;
```

  `Tie`을 이용해 *swap* 함수를 쉽게 구현 가능하다.
  
```c++
    tie(a,b) = make_pair(b,a);
```
