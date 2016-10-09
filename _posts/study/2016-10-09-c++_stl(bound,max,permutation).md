---
title: "[C++] STL(lower_bound, max, next_permutation)"
excerpt: "[10월 9일] C++ STL - lower_bound & max & next_permutation 공부"
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - C++
  - Study
  - lower_bound
  - max
  - next_permutation

---
# STL Algorithm

### `lower_bound / upper_bound`
 - `lower_bound(begin, end, value)` 는 **begin** 부터 **end** 까지 **value** 보다 작지 않은 첫 번째 iterator를 리턴해준다.
 - `upper_bound(begin, end, value)` 는 **begin** 부터 **end** 까지 **value** 보다 큰 첫 번째 iterator를 리턴해준다.
 - 내부적으로 **binary_search** 로 구현되어 있으므로 **binary_search** 의 위치를 찾고 싶을때 사용한다.
 - 정렬 되어있는 자료구조, 컨테이너 등에서 **upper_bound** - **lower_bound** 를 하면 **value** 의 개수를 알 수 있다.
 - `equal_range(begin, end, value)` 는 **upper_bound** , **lower_bound** 를 **pair** 형태로 리턴한다.

```c++
   #include <algorithm>
   vector<int> a = { 1,3,4,5,7,7,8 };

   	for (int i = 1; i < 10; i++){
   		auto l = lower_bound(a.begin(), a.end(), i);
   		auto u = upper_bound(a.begin(), a.end(), i);
   		cout << i << " : ";
   		cout << "lower_bound : " << (l - a.begin()) << ' ';
   		cout << "upper_bound : " << (u - a.begin()) << '\n';

   		//auto p = equal_range(a.begin(), a.end(), i);
   		//cout << i << " : ";
   		//cout << "lower_bound : " << (p.first - a.begin()) << ' ';
   		//cout << "upper_bound : " << (p.second - a.begin()) << '\n';
   	}
   	//1: lower_bound : 0 upper_bound : 1
   	//2: lower_bound : 1 upper_bound : 1
   	//3: lower_bound : 1 upper_bound : 2
   	//4: lower_bound : 2 upper_bound : 3
   	//5: lower_bound : 3 upper_bound : 4
   	//6: lower_bound : 4 upper_bound : 4
   	//7: lower_bound : 4 upper_bound : 6
   	//8: lower_bound : 6 upper_bound : 7
   	//9: lower_bound : 7 upper_bound : 7
```

#### 연습문제(Baekjoon)
  - [10815-숫자 카드 2](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/10816_%EC%88%AB%EC%9E%90%20%EC%B9%B4%EB%93%9C%202.cpp)


### `min / max`
 - 최소 / 최대 값을 return해준다.
 - c++11 부터 **initialize_list** 를 지원해준다. 초기화 리스트를 사용해 2개 이상도 구할 수 있다.
 - **cmp** 함수를 정의 할 수 있다.
 - `minmax`는 **pair** 형태로 return 해준다.
 - `min_element(begin, end) / max_element(begin, end)` 는 **begin** 부터 **end** 까지 최소, 최대를 구해 iterator를 return해주낟.
 - `minmax_element` 는 **pair** 형태로 return 해준다.

```c++
   #include <algorithm>

 	 int a = 10, b = 20, c = 30;
 	 cout << max({ a,b,c }) << '\n';	//30
 	 cout << min({ a,b,c }) << '\n'; //10
 	 cout << minmax({ a,b,c }).second << '\n'; //10
 	 cout << minmax({ a,b,c }).first << '\n'; //30

 	 string u = "long string";
 	 string v = "short";
 	 //short
 	 cout << min(u, v, [](string u, string v) {
 		  return u.size() < v.size();		
 	  }) << '\n';			
```

```c++
  vector<int> a = { 4, 2, 1, 5, 7, 3 };

  auto it1 = min_element(a.begin(), a.end());
  auto it2 = max_element(a.begin(), a.end());
  auto it3 = minmax_element(a.begin(), a.end());

  //최소 : 1 위치 : 2
  //최대 : 7 위치 : 4
  cout << "최소 : " << *it1 << " 위치 : " << (it1 - a.begin()) << '\n';
  cout << "최대 : " << *it2 << " 위치 : " << (it2 - a.begin()) << '\n';
  //최소 : 1 위치 : 2
  //최대 : 7 위치 : 4
  cout << "최소 : " << *it3.first  << " 위치 : " << (it3.first - a.begin()) << '\n';
  cout << "최대 : " << *it3.second << " 위치 : " << (it3.second - a.begin()) << '\n';
```

#### 연습문제(Baekjoon)
  - [1087-세 수](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/10817_%EC%84%B8%20%EC%88%98.cpp)


### `next_permutation`
   - `next_permutation(begin, end)`는 **begin** 에서 **end** 까지를 순열이라고 생각했을 때, 사전 순으로 다음에 오는 순열을 만든다.
   - 마지막 순열이면 **False** 를 return 해준다.
   - 알고리즘 문제에서 *do{} while()* 문을 쓰는 거의 유일한 경우이다.

```c++
   #include <algorithm>

    vector<int> a = { 3,1,2 };
   	sort(a.begin(), a.end());

   	//1 2 3
   	//1 3 2
   	//2 1 3
   	//2 3 1
   	//3 1 2
   	//3 2 1
   	do {
   		for (auto x : a)	cout << x << ' ';
   		cout << '\n';
   	} while (next_permutation(a.begin(), a.end()));
```


#### 연습문제(Baekjoon)
  - [1089-차이를 최대로](https://github.com/bee0005/TIL/blob/master/Algorithm/BaekJoon/10819_%EC%B0%A8%EC%9D%B4%EB%A5%BC%20%EC%B5%9C%EB%8C%80%EB%A1%9C.cpp)
