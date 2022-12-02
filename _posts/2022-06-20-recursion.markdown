---
title: "재귀"
layout: post
date: 2022.06.20
headerImage: false
tag:
- data structure
- Concept
- Back-end
category: study
author: Jina Kim
---

## 재귀 함수의 이해  

> **재귀(再歸)**  
> : 원래의 자리로 되돌아가거나 되돌아옴.      
> 
> **재귀 함수**   
자기 자신을 호출하는 함수.   
반복적인 작업을 좀 더 간결한 코드로 풀어낼 수 있다.   

### 문제를 쪼개어 생각하는 방법  

**예시)**  
자연수로 이루어진 배열를 입력받아 배열의 합을 리턴하는 메서드 `arrSum()`

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
```java
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

### 재귀함수의 장점  

1. 코드가 간결해지고, 수정이 용이하다.  
2. 변수를 여러개 사용할 필요가 없다.  

### 재귀함수의 단점  

1. 코드의 흐름을 직관적으로 파악하기 어렵다.  
2. 매서드를 반복적으로 호출하면서 지역변수, 매개변수, 반환값을 모두 process stack에 저장하게 된다.   
 -> 반복문에 비해서 더 많은 메모리를 사용.  
3. 매서드가 종료된 이후에 복귀를 위한 컨텍스트 스위칭 비용이 발생.  

### 재귀함수를 사용하기 위한 조건  

1. 문제의 크기를 점점 작은 단위로 쪼갤수 있어야 한다.
2. 재귀 호출이 종료되는 시점이 존재해야 한다.


-----
 > ### 재귀적 사고 연습하기
1. 재귀 함수의 입력값과 출력값 정의하기
2. 문제를 쪼개고 경우의 수를 나누기
3. 단순한 문제 해결하기(base case)
4. 복잡한 문제 해결하기(recursive case)
