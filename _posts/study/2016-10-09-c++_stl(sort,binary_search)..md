---
title: "[C++] STL(Sort, Stable Sort, Binary Search)"
excerpt: "[10월 9일] C++ STL - Sort & Stable Sort & Binary Search 공부"
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - C++
  - Study
  - Sort
  - Stable Sort
  - Binary Search

---
# STL Algorithm

### `Sort`
 - `sort(begin, end)` 는 **begin** 부터 **end** 까지 **<** 을 기준으로 정렬해준다(오름차순).
 - STL Algorithm 중에 가장 많이 사용하는 함수 중 하나이다.
 - 비교함수를 만들어 사용하는 경우도 많다. 그 경우에는 **cmp** 라는 비교함수를 만들어 준다.
 - 비교함수는 **bool** 형태로 되어있고 return 값은 **true** , **false** 이다.

```c++
   #include <algorithm>
   #include <functional>
   vector<int> v = {5, 3, 2, 1, 4};

   sort(v.begin(), v.end());
   for(auto x : v)  cout << x << ' ';   //1 2 3 4 5

   //내린 차순 정렬 3가지 방법
    bool cmp(const int &u, const int &v){
      return u > v;
    }

   sort(v.begin(), v.end(), greater<int>());
   sort(v.begin(), v.end(), cmp);
   sort(v.begin(), v.end(), [](int u, int v){
     return u > v;
   });
   for(auto x : v)  cout << x << ' ';   //5 4 3 2 1
```

#### 연습문제(Baekjoon)
  - [1181-단어 정렬](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/1181_%EB%8B%A8%EC%96%B4%20%EC%A0%95%EB%A0%AC.cpp)
  - [10825-국영수](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/10825_%EA%B5%AD%EC%98%81%EC%88%98.cpp)
  - [10814-나이순 정렬](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/10814_%EB%82%98%EC%9D%B4%EC%88%9C%20%EC%A0%95%EB%A0%AC(sort).cpp)
  - [11650-좌표 정렬하기(struct)](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/11650_%EC%A2%8C%ED%91%9C%20%EC%A0%95%EB%A0%AC%ED%95%98%EA%B8%B0(struct).cpp)
  - [11650-좌표 정렬하기(pair)](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/11650_%EC%A2%8C%ED%91%9C%20%EC%A0%95%EB%A0%AC%ED%95%98%EA%B8%B0(pair).cpp)
  - [11650-좌표 정렬하기(overloading)](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/11650_%EC%A2%8C%ED%91%9C%20%EC%A0%95%EB%A0%AC%ED%95%98%EA%B8%B0(overloading).cpp)
  - [11651-좌표 정렬하기2(pair)](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/11650_%EC%A2%8C%ED%91%9C%20%EC%A0%95%EB%A0%AC%ED%95%98%EA%B8%B02(struct).cpp)
  - [11651-좌표 정렬하기2(struct)](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/11650_%EC%A2%8C%ED%91%9C%20%EC%A0%95%EB%A0%AC%ED%95%98%EA%B8%B02(pair).cpp)

### `Stable Sorting`
 - `stable_sort(begin, end)`가 `sort` 와 다른 점은 **value** 가 같은 경우에는 입력이 *주어진 순서* 를 유지한다.
 - 순서를 유지하지 않으면 **Unstable** 하다고 한다
 - **Stable Sort** 의 대표적인 예는 `Merge Sort` 와 `Bubble Sort` 가 있다.

#### 연습문제(Baekjoon)
  - [10814-나이순 정렬](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/10814_%EB%82%98%EC%9D%B4%EC%88%9C%20%EC%A0%95%EB%A0%AC(stable_sort).cpp)


### `Binary Search`
   - `binary_search(begin, end, value)`는 **begin** 에서 부터 **end** 까지 **Value** 를 찾으면 *true* , 못 찾으면 *false* 를 return 한다.
   - 이분 탐색 알고리즘 이다.
   - 전제는 정렬이 되어 있어야 한다.
   - 어떤 값이 존재하는지 존재하지 않는지를 알 수 있다. 위치는 정확이 알 수 없다.
   - 위치를 알고 싶을때는 **lower_bound / upper_bound** 를 사용하면 좋다.

```c++
   #include <algorithm>
   vector<int> a = { 1,5,6,7,9,10 };

   for(int i = 1; i<=10; i++){
      cout << i << " : ";
      cout << binary_search(a.begin(), a.end(), i) << '\n';
   }
   //1 : 1
   //2 : 0
   //3 : 0
   //4 : 0
   //5 : 1
   // ...
```
