---
title: "[C++] STL(Count, Find, Fill, Reverse)"
excerpt: "[10월 9일] C++ STL - Count & Find & Fill & Reverse 공부"
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - C++
  - Study
  - Count
  - Find
  - Fill
  - Reverse

---
# STL Algorithm

### `Count`
 - `count`는 **begin** 에서 부터 **end** 사이에 들어있는 원소중에서 **value** 같은 값을 찾는 알고리즘이다.
 - **begin** 은 포함되어 있고 **end** 는 포함되어 있지 않다.
 - 시간복잡도는 **O(N)** 을 가진다.
 - `count_if`는 조건 **p** 에 해당하는 것을 찾는다.

```c++
   #include <algorithm>
   vector<int> v = {1,2,3,1,2,1,4};
   for(int i = 1; i <= 5; i++)
     cout << i << "의 개수 : " << count(v.begin(), v.end());
     //1의 개수 : 3
     //2의 개수 : 2
     //3의 개수 : 1
     //4의 개수 : 1
     //5의 개수 : 0
```

```c++
     vector<int> a = { 1,2,1,2,3,4,5,6,7,8 };
     int even = count_if(a.begin(), a.end(), [](int x) {
       return x % 2 == 0;
     });
     int odd = count_if(a.begin(), a.end(), [](int x) {
       return x % 2 == 1;
     });
     cout << even << '\n';  //5
     cout << odd << '\n';   //5
```

#### 연습문제(Baekjoon)
  - [2743-개수 세기](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/10807_%EA%B0%9C%EC%88%98%20%EC%84%B8%EA%B8%B0.cpp)
  - [10808-알파벳 개수](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/10808_%EC%95%8C%ED%8C%8C%EB%B2%B3%20%EA%B0%9C%EC%88%98.cpp)


### `Find`
 - `find`는 **begin** 에서 부터 **end** 사이에 들어있는 원소중에서 **value** 의 iterator를 return해준다.
 - 여러개가 있다면 첫번째 iterator를 return해준다.
 - **begin** 은 포함되어 있고 **end** 는 포함되어 있지 않다.
 - 시간복잡도는 **O(N)** 을 가진다. 모두 순회하기 때문이다.
 - `find_if`는 조건 **p** 에 해당하는 것의 iterator를 return해준다. 만약 못 없다면 **end** 를 return해준다.

```c++
   #include <algorithm>
   vector<int> a = {1,4,1,2,4,2,4,2,3,4,4};

   for(int i = 1; i <= 5; i++){
     auto it = find(a.begin(), a.end(), i);
     cout << i << "의 위치 :";

     if(it == a.end())  cout << "찾을 수 없다."
     else               cout << (it-a.begin());
   }

     //1의 위치 : 0 (0번째 index)
     //2의 개수 : 3
     //3의 개수 : 8
     //4의 개수 : 1
     //5의 개수 : 찾을 수 없다.
```

```c++
    vector<int> a = {1,4,1,2,4,2,4,2,3,4,4};
    auto even = find_if(a.begin(), a.end(), [](int x){
        return x % 2 == 0;
    };
    auto odd = find_if(a.begin(), a.end(), [](int x){
        return x % 2 == 1;
    };

     cout << (even - a.begin()) << '\n';  //1(첫 번째 홀수)
     cout << (odd - a.begin()) << '\n';   //0(첫 번째 짝수)
```

#### 연습문제(Baekjoon)
  - [10808-알파벳 찾기](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/10809_%EC%95%8C%ED%8C%8C%EB%B2%B3%20%EC%B0%BE%EA%B8%B0.cpp)


### `Fill`
   - `Fill`는 **begin** 에서 부터 **end** 까지 **value** 로 채운다.
   - cstring의 **memset** 함수는 주로 0, -1로 초기화 할 때 사용(다른 값은 오류 발생할 수도 있다)
   - 모든 값에서 올바르게 동작하므로 memset보다 fill이 좋다.
   - 시간복잡도는 **O(N)** 을 가진다. 모두 순회하기 때문이다.

```c++
   #include <algorithm>
   vector<int> a = {1,2,3,4,5};

   for(auto x : a)  cout << x << ' ';   //1 2 3 4 5
   fill(a.begin(), a.end(), 7);
   for(auto x : a)  cout << x << ' ';   //7 7 7 7 7
```

#### 연습문제(Baekjoon)
  - [10810-공 넣기](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/10810_%EA%B3%B5%EB%84%A3%EA%B8%B0.cpp)


### `Reverse`
   - `Reverse`는 **begin** 에서 부터 **end** 까지 순서를 역순으로 만든다.
   - 시간복잡도는 **O(N)** 을 가진다.

```c++
    vector<int> a = {1, 4, 1, 2, 4, 2, 4, 2, 3, 4, 4};

    for (int x : a)   cout << x << ' '; //1 4 1 2 4 2 4 2 3 4 4
    cout << '\n';
    reverse(a.begin(), a.end());
    for (int x : a)   cout << x << ' '; //4 4 3 2 4 2 4 2 1 4 1
    cout << '\n';
```

#### 연습문제(Baekjoon)
  - [10811-바구니 뒤집기](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/10811_%EB%B0%94%EA%B5%AC%EB%8B%88%20%EB%92%A4%EC%A7%91%EA%B8%B0.cpp)
