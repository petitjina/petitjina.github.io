---
title: "재귀"
layout: post
date: 2022.06.20
headerImage: false
tag:
- Java
- Concept
- Back-end
category: study
author: Jina Kim
---

## 재귀 함수의 이해
### 문제를 쪼개어 생각하는 방법

어떤 문제를 해결할 때, 동일한 구조의 더 작은 문제를 해결함으로써 문제를 해결하는 방법을(자기참조) 재귀(recursion)라고 한다.


**예시)**  
자연수로 이루어진 배열를 입력받아 배열의 합을 리턴하는 메서드 arrSum()

```java
//일반 코드로 푸는 방법
public int arrSum(int[] arr) {
	int sum = 0;
	for(int i = 0; i < arr.length; i++) {
		sum += arr[i];
	}
	return sum;
}
```
```java
// 재귀 사용
public int arrSum(int[] arr) {
//Base Case : 문제를 더 이상 쪼갤 수 없는 경우 (재귀의 기초)
	if(arr.length == 0) return 0;
 /*
  * Recursive Case : 그렇지 않은 경우
  * head: 배열의 첫 요소
  * tail: 배열의 첫 요소만 제거된 배열
  */
	int head = arr[0]
	int[] tail = Arrays.copyOfRange(arr, 1, arr.length);
	return head + arrSum(tail)
}
```
```
arrSum([7, 5, 4, 2]) = 7 + arrSum([5, 4, 2]);
arrSum([5, 4, 2]) = 5 + arrSum([4, 2]);
arrSum([4, 2]) = 4 + arrSum([2]);
arrSum([2]) = 2 + arrSum([]);
arrSum([]) = 0;// <-- 문제가 더는 작아지지 않는 순간
// 가장 작은 경우의 해결책을 적용한다.
```

**재귀를 사용하는 상황**  

1. 주어진 문제를 비슷한 구조의 더 작은 문제로 나눌 수 있는 경우  
2. 중첩된 반복문이 많거나 중첩 횟수를 예측하기 어려운 경우  


모든 재귀 함수는 반복문으로 표현할 수 있지만, 재귀를 사용하면 코드가 간결하고 이해하기 쉽다.

-----
 > ### 재귀적 사고 연습하기
1. 재귀 함수의 입력값과 출력값 정의하기
2. 문제를 쪼개고 경우의 수를 나누기
3. 단순한 문제 해결하기(base case)
4. 복잡한 문제 해결하기(recursive case)
