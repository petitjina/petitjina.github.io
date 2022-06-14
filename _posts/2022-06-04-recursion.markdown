## 재귀 함수의 이해
### 문제를 쪼개어 생각하는 방법

어떤 문제를 해결할 때, 동일한 구조의 더 작은 문제를 해결함으로써 주어진 문제를 해결하는 방법(자기참조)을 재귀(recursion)라고 한다.

```
예시) 자연수로 이루어진 배열를 입력받아 배열의 합을 리턴하는 메서드 `arrSum` 을 작성
```
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
arrSum([7, 5, 4, 2]) = 7 + arrSum([5, 4, 2]);
arrSum([5, 4, 2]) = 5 + arrSum([4, 2]);
arrSum([4, 2]) = 4 + arrSum([2]);
arrSum([2]) = 2 + arrSum([]);
arrSum([]) = 0;// <-- 문제가 더는 작아지지 않는 순간
// 가장 작은 경우의 해결책을 적용한다.
```

코드 가장 작은 단위부터 arrSum을 적용하여 문제를 풉니다.
```
/*
 * 1. arr이 빈 배열인 경우 = 0
 * 2. 그 외의 경우 = arr[0] + arrSum(arr2)
 *   (arr2는 arr의 첫 요소를 제외한 나머지 배열)
 */
arrSum(arr);
```
