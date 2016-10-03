---
title: "[Sort] Selection & Insertion"
excerpt: "[9월 17일] C++ Selection & Insertion 공부"
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - C++
  - Sort

---
# Selection / Insertion Sort

## **선택 정렬**

 - `Selection Sort`는 단순한 정렬 알고리즘 중 하나이다.
 - 배열의 첫 번째 원소에서 시작하여 배열 전체를 훑으면서 가장 작은(큰) 값을 찾아 첫 번째 원소와 바꿔준다.
 - 이 작업을 (배열의 길이-1) 만큼 진행한다.

## 분석
 1. 효율
  - 선택 정렬은 Best, Average, Worst Case 모두 **O(N^2)** 의 효율이다.

 2. 장점
   - *원소를 바꾸는 횟수가 최대 n-1 이다.* 즉, 원소를 바꾸는 과정에서 많은 비용이 드는 경우 효율적일 수 있다.

 3. 단점
  - 선택 정렬은 다른 알고리즘에 비해 효율이 좋지 않다.
  - Stable을 만족하지 않는다.


```c++
 #include <iostream>

 using namespace std;

 void selection_sort(int data[], int size);
 void swap(int& a, int& b);

 int main() {
   	int data[] = {3,7,9,4,5,1,3,4,6,9};
   	selection_sort(data,10);
   	for (int i = 0; i < 10; i++) cout << data[i] << " ";
   	return 0;
 }

 void selection_sort(int data[], int size) {
   	for (int i = 0; i < size - 1; i++) {
   		int min = i;
   		for (int j = i + 1; j < size; j++) {
   			if (data[min] > data[j]) min = j;
   		}
   		swap(data[min], data[i]);
   	}
 }

 void swap(int& a, int& b) {
   	int temp = a;
   	a = b;
   	b = temp;
 }
```

## **삽입 정렬**

   `Insertion Sort`는 단순한 정렬 알고리즘 중 하나이다. 한번의 한 원소씩 이미 정렬된 다른 원소들과 비교하여 올바른 위치에 삽입하는 정렬이다.

## 분석
  1. 효율
     - 삽입 정렬은 이미 정렬되어 있을때 **O(N)** 의 효율이다.(Best Case)
     - Average, Worse Case의 경우 **O(N^2)** 이다.
     - Bubble Sort에서 발전된 형태이다.(비교 횟수를 줄였다)

  2. 장점
      - *소량의 데이터를 처리할때 좋다.*
      - Stable 하다.

  3. 단점
     - 무작위로 정렬된 많은 데이터의 효율이 매우 안좋다.



```c++
 #include <iostream>
 
 using namespace std;
 
 void insertion_sort(int data[], int size);
 
 int main() {
     int data[] = {3,7,9,4,5,1,3,4,6,9};
     insertion_sort(data,10);
     for (int i = 0; i < 10; i++) cout << data[i] << " ";
     return 0;
 }
 
 void insertion_sort(int data[], int size) {
     for (int i = 1; i < size; i++) {
         int temp = data[i];
         int j = i - 1;
         while (j >= 0 && data[j] > temp) {
             data[j+1] = data[j];
             j--;
         }
         data[j+1] = temp;
     }
 }
```
