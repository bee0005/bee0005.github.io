---
title: "[Sort] Quick Sort"
excerpt: "[9월 13일] C++ Quick Sort 공부"
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - C++
  - Sort

---
# Quick Sort

## **퀵 정렬**

1. `Quick Sort`는 데이터내의 Pivot 값을 정하고 그 기준으로 두 개의 부분집합으로 나눈다.
2. 한쪽은 Pivot보다 작은 값을 다른 한쪽은 Pivot보다 큰 값으로 나눈다.
3. 더 이상 쪼갤 부분집합이 없을 때까지 재귀적으로 진행한다.

## 분석
 1. 효율
  - Quick Sort는 어떤 Pivot 값을 고르는지에 따라 성능이 결정된다. 가장 이상적인 Pivot은 전체 데이터를 절반씩 쪼갤 수 있어야 한다. 이 경우 **O(N log(n))** 의 복잡도를 가진다.
  - 최악으 경우는 집합의 최소(최대) 값을 Pivot으로 고른 경우이다. 그러면 한쪽의 부분집합은 비어있고, 다른 한쪽은 n-1개의 원소가 있다(pivot 제외). 이 경우 재귀호출 횟수가 O(N)이며, 최악의 경우 **O(N^2)** 의 복잡도를 가진다.
  - 하지만 평균적으로 **O(N log(n))** 의 복잡도를 가진다.
  - 정렬되어 있다면 가운데 값을 Pivot으로 고르는 것이 효과적이다.

 2. 장점
   - *원소를 바꾸는 횟수가 최대 n-1 이다.* 즉, 원소를 바꾸는 과정에서 많은 비용이 드는 경우 효율적일 수 있다.

 3. 단점
  - Stable을 만족하지 않는다.


```c++
   #include <iostream>
  
   using namespace std;
  
   void quick_sort(int ary[], int left, int right);
   void swap(int& a, int& b);
  
   void quick_sort(int ary[], int left, int right) {
   	int i = left;
   	int j = right;
   	int pivot = left;
   	if (i < j)
   	{
   		while (i < j)
   		{
   			while (ary[pivot] < ary[j]) j--;
   			while (ary[pivot] >= ary[i] && i < j) i++;
   			swap(ary[i], ary[j]);
   		}
   		swap(ary[i], ary[left]);
   		quick_sort(ary, left, i - 1);
   		quick_sort(ary, i + 1, right);
   	}
  
   }
   void quickSort(int arr[], int left, int right) {
   	int i = left;
    int j = right;
   	int pivot = (left + right) / 2;
   	if (i < j) {
   		while (i <= j) {
   			while (arr[i] < arr[pivot])i++;
   			while (arr[j] > arr[pivot])j--;
   			if (i <= j) {
   				swap(arr[i++], arr[j--]);
   			}
   		};
   		quickSort(arr, left, j);
   		quickSort(arr, i, right);
   	}
   }
   int main() {
   	int data[] = {3,7,9,4,5,1,3,4,6,9};
   	//quick_sort(data,0,9);
   	quickSort(data, 0, 9);
   	for (int i = 0; i < 10; i++) cout << data[i] << " ";
   	return 0;
   }
  
  
   void swap(int& a, int& b) {
   	int temp = a;
   	a = b;
   	b = temp;
   }

```
