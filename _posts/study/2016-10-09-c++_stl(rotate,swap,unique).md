---
title: "[C++] STL(Rotate, Swap, Unique)"
excerpt: "[10월 9일] C++ STL - Rotate & Swap & Unique 공부"
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - C++
  - Study
  - Rotate
  - Swap
  - Unique

---
# STL Algorithm

### `Rotate`
 - `rotate(begin, mid, end)` 는 **begin** 부터 **end** 까지 **mid** 을 기준으로 왼쪽으로 회전시킨다.
 - **begin** 에는 **mid** 에 있던 값이 **end-1** 에는 **mid-1** 에 있던 값이 들어간다.
 - 시간복잡도는 **O(N)** 을 가진다.

```c++
   #include <algorithm>
   vector<int> v = {0, 1, 2, 3, 4, 5};

   for(auto x : v)  cout << x << ' ';   //0 1 2 3 4 5
   rotate(v.begin(), v.begin()+2 ,v.end());
   for(auto x : v)  cout << x << ' ';   //2 3 4 5 0 1
```

```c++
  #include <algorithm>
  vector<int> v = {0, 1, 2, 3, 4, 5};

  int n = v.size();
  //왼쪽으로 회전
  for(int i=0; i<n; i++){
    rotate(v.begin(), v.begin()+1 ,v.end());
    for(auto x : v)  cout << x << ' ';
    cout << '\n';
  }
  //123450
  //234501
  //345012
  //450123
  //501234
  //012345

  //오른쪽으로 회전
  for(int i=0; i<n; i++){
    rotate(v.begin(), v.begin()+(n-1) ,v.end());
    //=rotate(v.rbegin(), v.rbegin()+1 ,v.rend());
    for(auto x : v)  cout << x << ' ';
    cout << '\n';
  }
  //501234
  //450123
  //345012
  //234501
  //123450
  //012345
```

#### 연습문제(Baekjoon)
  - [10812-바구니 순서 바꾸기](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/10812_%EB%B0%94%EA%B5%AC%EB%8B%88%20%EC%88%9C%EC%84%9C%20%EB%B0%94%EA%BE%B8%EA%B8%B0.cpp)


### `Swap`
 - `swap(a,b)`는 **a** 와 **b** 의 값을 바꿔준다.

```c++
   #include <algorithm>
   int a = 10, b =20;
   vector<int> c = {1,2};
   vector<int> d = {3,4};

    cout << a << ' ' << b << '\n';   //1 2
    swap(a,b);
    cout << a << ' ' << b << '\n';   //2 1

    cout << c[0] << ' ' << c[1] << '\n';   //1 2
    cout << d[0] << ' ' << d[1] << '\n';   //3 4
    swap(c,d);
    cout << c[0] << ' ' << c[1] << '\n';   //3 4
    cout << d[0] << ' ' << d[1] << '\n';   //1 2
```

#### 연습문제(Baekjoon)
  - [10813-공 바꾸기](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/10813_%EA%B3%B5%20%EB%B0%94%EA%BE%B8%EA%B8%B0.cpp)


### `Unique`
   - `unique(begin, end)`는 **begin** 에서 부터 **end** 까지 연속되는 같은 값을 하나를 제외하고 제거한다.
   - 좌표 압출을 할 때 많이 사용한다.
   - 실제로 컨테이너의 크기는 줄거나 제거되지는 않는다.
   - 정렬이 되어있지 않으면 붙어있는것만 정렬해준다.
   - 중복을 제거한 후의 end iterator을 리턴한다.

```c++
   #include <algorithm>
   vector<int> a = { 1,1,2,2,2,3,1,1,1,2,2,2,2 };

   //1 1 2 2 2 3 1 1 1 2 2 2 2
   for (auto x : a)	cout << x << ' ';
   cout << '\n';

   //1 2 3 1 2 3 1 1 1 2 2 2 2
   auto last = unique(a.begin(), a.end());
   for (auto x : a)	cout << x << ' ';
   cout << '\n';

   //1 2 3 1 2
   for (auto it = a.begin(); it != last; it++)
     cout << *it << ' ';
   cout << '\n';

   //1 2 3 1 2
   a.erase(last, a.end());
   for(auto x : a)  cout << x << ' ';
   cout << '\n';
```

```c++
  #include <algorithm>
  vector<int> a = { 1,1,2,2,2,3,1,1,1,2,2,2,2 };

  sort(a.begin(), a.end());
  auto last = unique(a.begin(), a.end());
  a.erase(last, a.end());
  for(auto x : a) cout << x << ' ';
  cout << '\n';
  //1 2 3
```
