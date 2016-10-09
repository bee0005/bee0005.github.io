---
title: "[Sort] Merge Sort"
excerpt: "[10월 10일] C++ Merge Sort 공부"
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - C++
  - Sort

---
# Merge Sort

## **병합 정렬**

`Merge Sort`는 **Divide and Conquer** 알고리즘 기법이다.

## 분석
  - Merge Sort의 경우 항상 **O( N log(N) )** 의 시간복잡도를 가진다.
  - 성능은 전반적으로 **Quick Sort** 에 비해 떨어진다.
  - **Stable** 하다
  - 추가 메모리 공간(Not in-place)이 필요하다.
  - C++의 **stable_sort** 가 **Merger Sort** 로 구현되어 있다.

```c++
#include <iostream>

using namespace std;

void merge_sort(int ary[], int left, int right);
void merge(int ary[], int left, int mid, int right);

int* temp;

int main() {
	int ary[] = { 6,4,2,7,9,7,6,4,4,1,0 };
	temp = new int[11];
	for (int i = 0; i < 11; i++)
		cout << ary[i] << ' ';
	cout << endl;
	merge_sort(ary, 0,10 );
	for (int i = 0; i < 11; i++)
		cout << ary[i] << ' ';
	return 0;
}


void merge_sort(int ary[], int left, int right) {
	if (left < right) {
		int mid = (left + right) / 2;
		merge_sort(ary, left, mid);
		merge_sort(ary, mid+1, right);
		merge(ary, left, mid, right);
	}
}

void merge(int ary[], int start, int middle, int end) {
	int mid = (start + end) / 2;
	int i = start;
	int j = mid + 1;
	int k = start;
	while (i <= middle && j <= end) {
		if (ary[i] < ary[j])
			temp[k++] = ary[i++];
		else
			temp[k++] = ary[j++];
	}
	if (i > mid) {
		for (int it = j; it <= end; it++)
			temp[k++] = ary[it];

	}
	else {
		for (int it = i; it <= mid; it++)
			temp[k++] = ary[it];
	}
	for (int i = start; i <= end; i++)
		ary[i] = temp[i];
}
```
