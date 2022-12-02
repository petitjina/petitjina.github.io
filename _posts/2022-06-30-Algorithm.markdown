---
title: "알고리즘"
layout: post
date: 2022.06.30
headerImage: false
tag:
- data structure
- Concept
- Back-end
category: study
author: Jina Kim
---


## Algorithm  

알고리즘은 문제를 해결하는 최선의 선택.  

최선인 경우의 수는 무엇일까?  
컴퓨터를 이용해 문제를 해결할 때에는, 많은 방법을 시도할 수 있다.  
모든 경우의 수를 하나씩 비교해서 그 중 최선을 골라낼 수 있다.  
또, 하나씩 비교하지 않더라도 가장 좋아 보이는 것을 먼저 찾아냈다면, 뒤쪽의 경우의 수를 그냥 무시하는 경우도 있다.   
컴퓨터가 데이터를 비교하고 연산하는 속도가 너무 빠르기 때문에, 이 과정을 보는 사람들에게는 컴퓨터가 그저 입력과 동시에 결과를 출력하는 걸로 보인다.  

-----
## Pseudocode

>**의사 코드(Pseudocode)**  
프로그래밍 언어로 코드를 작성하기 전, 일상 언어로 먼저 작성하는 것.  

### 의사코드 장점  

**1. 시간이 단축**  
처음부터 코드를 작성하면 문제가 복잡하거나 코드 양이 길어진 경우, 시간이 지나면서 로직이 기억나지 않을 것이다.  
-> 결국 작성하는 시간보다 헤매는 시간이 더 길어질 가능성이 크다.   

**2. 디버깅에 용이**  
테스트를 했을 때, 오류가 발생하면 디버깅을 시작할 것이다.  
어느 부분에 오류가 났는지 확인 할때 유용하다.  
-> 로직에 신경 쓸 수 있기 때문에 원인 파악이 쉽다.  

**3. 비개발자와 소통**  
비개발자도 수도 코드를 보며 로직을 이해하는 데 도움이 될 수 있다.  

### 구체적인 의사코드  

사람은 컴퓨터가 가지고 있지 않은 상상력이 있다.  
-> 구체적이지 않은 코드를 작성하면 컴퓨터는 이해하지 못 한다.  

```
예시) 일상생활에서 사람이 쉽게 접할 수 있는 마스크 쓰는 법 

- 사람  
"마스크로 코와 입을 덮고 턱 아래, 얼굴 측면에 밀착시켜서 착용 하세요"라고 말하기.    

- 컴퓨터
1. 마스크를 꺼낸다.  
2. 마스크 날개를 펼치고 날개 끝을 잡아 오므린다.  
3. 고정심 부분을 위로 잡고 턱에서 시작하여 코와 입을 완전히 가린다.  
4. 만약 귀걸이 마스크일 경우, 왼쪽 귀와 오른쪽 귀에 걸어준다.  
5. 만약 귀걸이 마스크가 아니라면 마스크를 머리 뒤쪽으로 걸어준다.  
6. 고정심을 코에 밀착되도록 누른다.  
7. 양 손으로 마스크 전체를 누르며 공기 누설이 있는지 체크한다.  
8. 만약 공기 누설이 있다면, 5번으로 돌아간다.  
9. 공기 누설이 없다면 마스크 착용 완료.   
```

### 의사코드를 쓰는 양식  

1. 다른 사람도 이해할 수 있는 자연어만 사용   
(영어나 한국어처럼 일상에서 사용되는 언어)   

2. 자연어와 프로그램 언어의 조합을 사용   

-----
## Time Complexity  

![](https://velog.velcdn.com/images/wlsk124/post/72713a7f-bc44-43bf-b6d8-09133e70c192/image.png)

>**시간 복잡도(Time Complexity)**  
문제를 해결하는데 걸리는 시간과 입력의 함수 관계.  
주로 **빅-오 표기법** 을 사용해 나타낸다.

효율적인 알고리즘을 구현한다.  
= 입력값이 커짐에 따라 증가하는 시간의 비율을 최소화한 알고리즘을 구성했다.  

### Big-O 표기법  

프로그램이 실행되는 과정에서 소요되는 최악의 시간까지 고려한다.  

**시간 복잡도를 표기하는 방법**  
- **Big-O(빅-오)**
- Big-Ω(빅-오메가)
- Big-θ(빅-세타)  

세 가지 표기법은 각각 최악, 최선, 평균의 경우에 대하여 나타내는 방법이다.   
이 중에서 Big-O 표기법이 가장 자주 사용된다.   

**- Big-Ω(빅-오메가)를 사용할 경우**  

결과를 반환하는 데 최선의 경우 1초, 평균 1분, 최악의 경우 1시간이 걸리는 알고리즘을 구현했고,   
최선의 경우를 고려한다고 가정했다.    
이 알고리즘을 100번 실행한다면, 최선의 경우 100초가 걸립니다.   
만약 실제로 걸린 시간이 1시간을 훌쩍 넘겼다면, 어디서 문제가 발생한 건지 의문이 생긴다.    
이때, 어디에서 문제가 발생했는지 알아내기 위해 문제를 파악하는 데 많은 시간이 필요하다.  

**- Big-θ(빅-세타)를 사용할 경우**  

알고리즘을 100번 실행할 때 100분의 시간이 소요된다고 생각했는데,  최악의 경우가 몇 개 발생하여 300분이 걸렸다면 최선의 경우를 고려한 것과 같은 고민을 하게 된다.  

따라서 다른 표기법보다 `Big-O 표기법`을 많이 사용한다.  

### Big-O 표기법의 종류  

**O(1) - constant complexity**  

![](https://velog.velcdn.com/images/wlsk124/post/03698f64-ed18-409f-9f46-126d89be6741/image.png)
 
입력값이 증가하더라도 시간이 늘어나지 않는다.  
-> 입력값의 크기와 관계없이, 즉시 출력값을 얻어낼 수 있다는 의미.  
```java
// O(1)의 시간 복잡도 예시 
public int O_1(int[] arr, int index) {
  return arr[index];
}

int[] arr = new int[]{1,2,3,4};
int index = 1;
int result = O_1(arr, index);
System.out.println(result); // 2
```

위 예시에선 입력값의 크기가 아무리 커져도 즉시 출력값을 얻어낼 수 있다.  
-> arr의 길이가 100이라도, 즉시 해당 index에 접근해 값을 반환할 수 있다.  

**O(n) - linear complexity**  

![](https://velog.velcdn.com/images/wlsk124/post/9f6e4b1d-44bd-4cb7-adbb-9435a5779196/image.png)


입력값이 증가함에 따라 시간 또한 같은 비율로 증가하는 것을 의미.  

```java
//O(n)의 시간 복잡도 예시 
public void O_n(int n) {
	for(int i = 0; i < n; i++) {
	// do something for 1 second
	}
}

public void another_O_n(int n) {
	for(int i = 0; i < n * 2; i++) {
	// do something for 1 second
	}
}
```

`O_n` 함수에선 입력값(n)이 1 증가할 때마다 실행 시간이 1초씩 증가한다.  
-> 입력값이 증가함에 따라 같은 비율로 걸리는 시간이 늘어난다.  

`another_O_n` 에선 입력값(n)이 1 증가할 때마다 실행 시간이 2초씩 증가한다.  
이 알고리즘을 O(2n)으로 표현한다고 생각할 수 있지만, Big-O 표기법으로는 O(n)으로 표기힌다.   
-> 입력값이 커지면 커질수록 계수의 의미(영향력)가 점점 퇴색되기 때문에,  
같은 비율로 증가하고 있다면 O(n)으로 표기한다.  

**O(log n) - logarithmic complexity**  

![](https://velog.velcdn.com/images/wlsk124/post/dc6743e4-6a4c-4ee7-9798-11123ccbbe94/image.png)

Big-O표기법중 O(1) 다음으로 빠른 시간 복잡도를 가진다.  
BST(Binary Search Tree)는 O(log n)의 시간 복잡도를 가진 알고리즘이다.   
-> 값을 탐색할 때, 노드를 이동할 때마다 경우의 수가 절반으로 줄어든다.  
-> 예시로는 up & down 게임이 있다.(BST와 같은 로직)   

**O(n^2) - quadratic complexity**  

![](https://velog.velcdn.com/images/wlsk124/post/24594f25-c636-4163-99fd-4d40290f18a7/image.png)

입력값이 증가함에 따라 시간이 n의 제곱수의 비율로 증가하는 것을 의미한다.  

```java
//O(n^2)의 시간 복잡도 예시 
public void quadratic(int n) {
	for(int i = 0; i < n; i++) {
		for(int j = 0; j < n; j++) {
			// do something for 1 second
		}
	}
}

public void another_quadratic(int n) {
	for(int i = 0; i < n; i++) {
		for(int j = 0; j < n; j++) {
			for(int k = 0; k < n; k++) {
				// do something for 1 second
			}
		}
	}
}
```

반복문의 수가 늘어날수록 n제곱의 수는 늘어난다.  
-> 함수 quadratic는 O(n^2)이고 , another_quadratic는 O(n^3)이다.  

2n, 5n 을 O(n)이라고 표현하는 것처럼, n^3과 n^5 도 O(n^2)로 표기한다.  

**O(2^n) - exponential complexity**   

![](https://velog.velcdn.com/images/wlsk124/post/d9d65b49-b879-4040-bf01-7a7e109d0f3a/image.png)

Big-O 표기법 중 가장 느린 시간 복잡도를 가진다.  
시간 복잡도가 O(2^n)이라면 다른 접근 방식을 고민하는게 좋다.  


```java
//O(2^n)의 시간 복잡도 예시 
public int fibonacci(int n) {
	if(n <= 1) {
		return 1;
	}
	return fibonacci(n - 1) + fibonacci (n - 2);
}
```

재귀로 구현한 피보나치 수열은 O(2^n)의 시간 복잡도를 가진 대표적인 알고리즘이다.  

n을 40으로 두어도 수초가 걸리는 것을 확인할 수 있으며,  
n이 100 이상이면 평생 결과를 반환받지 못할 수도 있다.

-----
## Greedy 

>Greedy - 탐욕스러운, 욕심 많은  
>
**Greedy Algorithm(탐욕 알고리즘)**  
 : 선택의 순간마다 당장 최적의 상황만을 쫓아 해답에 도달하는 방법.   

탐욕 알고리즘은 문제를 해결하는 과정에서 매 순간, 최적이라 생각되는 해답(locally optimal solution)을 찾으며,  
이를 토대로 최종 문제의 해답(globally optimal solution)에 도달하는 문제 해결 방식이다.


**Greedy로 문제 해결 방법**  

선택 절차(Selection Procedure) : 현재 상태에서의 최적의 해답을 선택.  
적절성 검사(Feasibility Check) : 선택된 해가 문제의 조건을 만족하는지 검사.  
해답 검사(Solution Check) : 원래의 문제가 해결되었는지 검사하고, 해결되지 않았다면 선택 절차로 돌아가 위의 과정을 반복.

### 일상 속 예시 1  

>영희은 편의점에서 아르바이트하고 있다.  
손님으로 온 철수는 과자와 음료를 계산기 위해 카운터에 갔다.  
물건 가격은 총 4,040원이 나왔고, 철수는 5,000원을 냈다.  
철수는 거스름돈으로 동전 개수를 최소한으로 하여 거슬러 달라고 했다.  

탐욕 알고리즘 - 동전 개수를 최소한으로 선택하는 방법.  

**선택 절차**  
거스름돈의 동전 개수를 줄이기 위해 현재 가장 가치가 높은 동전을 우선 선택한다.  

**적절성 검사**  
선택 과정을 통해 선택된 동전들의 합이 거슬러 줄 금액을 초과하는지 검사한다.  
초과하면 마지막에 선택한 동전을 삭제하고, 선택 절차로 다시 돌아가 한 단계 작은 동전을 선택한다.  

**해답 검사**  
선택된 동전들의 합이 거슬러 줄 금액과 일치하는지 검사한다.  
액수가 부족하면 선택 절차 과정부터 다시 반복한다.  

### 일상 속 예시 2  

🥖$3 40g | 🍞$1.5 25g | 🥯$2.5 5g | 🥐 $2 20g
👜 LIMIT 35g
>장발장이 빵 가게에서 빵을 훔치려고 한다.  
장발장의 가방은 35g까지의 빵만 담을 수 있다.  
빵은 가격과 무게가 전부 다르며, 4개의 종류가 각 1개씩 있다.  
빵은 쪼개어 담을 수 있고, 장발장은 최대한 비싼 빵으로만 채우고 싶다.  
>
빵의 가격과 무게   
🥖 $3 / 40g,  🍞 $1.5 / 25g, 🥯 $2.5 / 5g, 🥐 $2 / 20g  
👜 LIMIT 35g  

탐욕 알고리즘 - 달러당 부피가 가장 작은 빵들로 가방을 체우는 방법.  

$1당 2g인 🥯빵(5g) 먼저 가방에 담을 수 있다 - 남은 가방 무게: 30g  
$1당 10g인 🥐빵(20g)을 다음으로 담을 수 있다 - 남은 가방 무게: 10g  
$1당 13.3g인 🥖빵(40g)을 다음으로 담을 수 있다.  
그러나, 40g을 온전히 못 채우기 때문에 쪼개어, 10g만 담는다.  

만약 “빵을 쪼갤 수 없는 상황”이라면 마시멜로 실험 결과처럼 Greedy는 최적의 결과를 보장할 수 없다.  
-> greedy는 "현재"에 최선인 선택을 하기 때문에 마시멜로를 당장 1개를 받지만, 전체적으로 보면 1분 뒤 2개를 받는 선택이 최적의 선택이 된다.  
-> 따라서, 두 가지의 조건을 만족하는 "특정한 상황" 이 아니면 탐욕 알고리즘은 최적의 결과를 보장하지 못한다.   

### 탐욕 알고리즘(Greedy)의 조건  

**1. 탐욕적 선택 속성(Greedy Choice Property)**  
앞의 선택이 이후의 선택에 영향을 주지 않는다.  

**2. 최적 부분 구조(Optimal Substructure)**  
문제에 대한 최종 해결 방법은 부분 문제에 대한 최적 문제 해결 방법으로 구성된다. 탐욕 알고리즘은 항상 최적의 결과를 도출하는 것은 아니지만, 어느 정도 최적에 근사한 값을 빠르게 도출할 수 있는 장점이 있다. 이 장점으로 인해 탐욕 알고리즘은 근사 알고리즘으로 사용할 수 있다.  

>**근사 알고리즘(approximation algorithm)**
어떤 최적화 문제에 대한 해의 근사값을 구하는 알고리즘을 의미.  
이 알고리즘은 가장 최적화되는 답을 구할 수는 없지만, 비교적 빠른 시간에 계산이 가능하며 어느 정도 보장된 근사해를 계산할 수 있다.  

-----
## Implementation  
### 구현(Implementation)  

알고리즘 문제를 푼다는 것은, 내가 생각한 문제 해결 과정을 컴퓨터식 사고로 변환하여 코드로 구현한다는 것과 같다.  
문제 해결 과정은 대부분 여러 개의 카테고리로 묶여진다.  

문제 해결을 코드로 풀 때, 정확하고 빠를 수록 구현 능력이 좋다고 말한다.  
머리로 이해하고 있어도 코드로 작성하지 못한다면 구현 능력이 떨어진다고 말한다. 본인이 선택한 프로그래밍 언어의 문법을 정확히 알고 있고, 문제의 조건에 전부 부합하는 코드를 실수 없이 빠르게 작성하는 것을 목표로 두는 것을 **구현 문제, 구현 유형** 이라고 통칭할 수 있다.  

구현 능력을 보는 대표적인 사례에는 **완전 탐색과 시뮬레이션** 이 있다.   

- 완전 탐색  
가능한 모든 경우의 수를 전부 확인하여 문제를 푸는 방식   
- 시뮬레이션   
문제에서 요구하는 복잡한 구현 요구사항을 전부 코드로 옮겨 푸는 방식  

### 시뮬레이션(Simulation)  

모든 과정과 조건이 제시되어, 그 과정을 거친 결과가 무엇인지 확인하는 유형.   

>**예시**  
비밀스러운 비밀 조직 '시크릿 에이전시'는 소통의 흔적을 남기지 않기 위해 3일에 한 번씩 사라지는 메신저 앱을 사용했다. 그러나 내부 스파이의 대화 유출로 인해 대화를 할 때 조건을 여러 개 붙이기로 했다. 
시크릿 에이전시의 바뀌기 전 대화를 받아, 해당 조건들로 전부 수정한 대화를 객체에 키와 값으로 담아 반환하기.  

**조건**   
- 캐릭터는 아이디, 닉네임, 소속이 영문으로 담긴 배열로 구분한다.
- 소속은 'true', 'false', 'null' 중 하나이다.
- 소속이 셋 중 하나가 아니라면 아이디, 닉네임, 소속, 대화 내용의 문자열을 전부 X로 바꾼다.
- 아이디와 닉네임은 길이를 2진수로 바꾼 뒤, 바뀐 숫자를 더한다.
- 캐릭터와 대화 내용을 구분할 땐 `공백:공백`으로 구분한다.   
'Blue', 'Green', 'null' : hello.  
- 띄어쓰기 포함, 대화 내용이 10 글자가 넘지 않을 때, 내용에 `.,-+`이 있다면 삭제한다.  
- 띄어쓰기 포함, 대화 내용이 10 글자가 넘을 때, 내용에 `.,-+@#$%^&*?!`이 있다면 삭제한다.  
- 띄어쓰기를 기준으로 문자열을 반전한다.  
`'abc' -> 'cba'`   
- 띄어쓰기를 기준으로 소문자와 대문자를 반전한다.  
`'Abc' -> 'aBC'`  
- 같은 캐릭터가 두 번 말하면, 공백을 한 칸 둔 채 내용을 추가해야야 한다.  
- 대화는 문자열로 제공되며, 하이픈- 으로 구분된다.  
- 문자열은 전부 싱글 쿼터로 제공되며, 전체를 감싸는 문자열은 더블 쿼터로 제공된다.  
`"'Blue', 'Green', 'null' : 'hello. im K.' - 'Black', 'red', 'true': '? what? who are you?'"`  

이를 바탕으로 코드로 구현을 해야 한다.

### 완전 탐색 알고리즘(Brute-Force Algorithm)  

컴퓨터 과학에서 Brute Force는 시행착오 방법론을 말한다.  

암호학에서는 Brute Force Attack이라고 불리며 특정한 암호를 풀기 위해서 모든 값을 대입하는 방법을 말한다.   
수많은 시행착오를 통해 민감한 데이터를 해킹하는 방법이다.  
무차별 대입 공격이 다른 해킹 방법과 다른 점은 지능형 전략을 사용하지 않는 점이다.  
무차별 대입 공격은 올바른 조합을 찾을 때까지 다양한 조합을 시도한다.

>**Brute Force Attack 예시**   
0-9 사이의 4자리 숫자로 된 자물쇠가 있다.  
이 자물쇠의 번호 조합을 잊어버렸다.   
자물쇠를 사용하려면 비밀번호를 0000부터 9999까지의 경우의 수를 모두 하나하나 대입하여 자물쇠를 열어야 한다.   
이때 최악의 경우 10000번의 시도가 필요하다.

**Brute Force Algorithm**  
무차별 대입 방법을 나타내는 알고리즘.  
순수한 컴퓨팅 성능에 의존해 모든 가능성을 시도하는 문제 해결 방법이다.  
Brute Force는 최적의 솔루션이 아니라는 것을 의미하기도 한다.  
공간복잡도와 시간복잡도의 요소를 고려하지 않고 최악의 시나리오를 취하더라도 솔루션을 찾으려고 하는 방법.  

**Brute Force Algorithm 사용 경우**

- 프로세스 속도를 높이는데 사용할 수 있는 다른 알고리즘이 없을 때  
- 문제를 해결하는 여러 솔루션이 있고 각 솔루션을 확인해야 할 때  


Brute Force Algorithm은 문제에 더 적절한 해결 방법을 찾기 전에 시도하는 방법이다.  
그러나 데이터의 범위가 커질수록 상당히 비효율적이고, 프로젝트의 규모가 커진다면 더 효율적인 알고리즘을 사용해야 한다.

**Brute Force 활용 알고리즘**  

- 순차 검색 알고리즘 (Sequential Search)
배열 안에 특정 값이 존재하는지 검색할 때 인덱스 0부터 마지막 인덱스까지 차례대로 검색한다.   

```java
public boolean SequentialSearch2(int[] arr, int K) {
 boolean result = false;
  for(int i = 0; i < arr.length; i++) {
    if(arr[i] == K) {
      result = true;
    }
  }
  return result;
}   
// 배열을 순회하는 도중에, 해당 값이 발견되더라도 배열을 모두 순회한 이후에 결과값을 리턴
```

- 문열 매칭 알고리즘 (Brute-Force String Matching)
길이가 n인 전체 문자열이 길이가 m인 문자열 패턴을 포함하는지를 검색한다.

```java
public boolean BruteForceStringMatch(int[] arr, int[] patternArr) {
    int n = arr.length;
    int m = patternArr.length;
    for (int i = 0; i < n - m; i++) {
      // 전체 요소개수에서 패턴개수를 뺀 만큼만 반복. 
      // i 반복문은 패턴과 비교의 위치를 잡는 반복문이다.
      int j = 0;
      // j는 전체와 패턴의 요소 하나하나를 비교하는 반복문이다.
      while (j < m && patternArr[j] == arr[i + j]) {
        j = j + 1;
      }
      if (j == m) {
        return true;
      }
   }
   return false;
 }

```

- 선택 정렬 알고리즘 (Selection Sort)

전체 배열을 검색하여 현재 요소와 비교하고 컬렉션을 완전히 정렬한다.  
오름차순, 내림차순 정렬

```java
// 오름차순 정렬
public int[] SelectionSort(int[] arr) {
    for (int i = 0; i < arr.length - 1; i++) {
      int min = i;
      for (int j = i + 1; j < arr.length; j++) {
        if (arr[j] < arr[min]) {
          min = j;
        }
      }
      int temp = arr[i];
      arr[i] = arr[min];
      arr[min] = temp;
    }
  return arr;
}

```  

- 버블 정렬 알고리즘(Bubble Sort Algorithm)  
- Exhausive Search(BFS, DFS)
- [동적 프로그래밍(Dynamic Programing, DP)](https://www.geeksforgeeks.org/difference-between-brute-force-and-dynamic-programming/)  
동적 프로그래밍의 접근법은 문제를 가능한 작은 하위 문제로 분할하고 정복하는 것과 유사하다. -> 단순한 재귀에 대한 최적화.   

|비교|Brute Force|Dynamic Programing
|:---:|:----:|:-----:
|방법론|주어진 문제의 가능한 모든 결과를 찾아낸다.|가능한 모든 결과를 찾지만, 값을 저장하여 재계산을 방지한다.
|반복|반복횟수가 동적 프로그램보다 많다|반복횟수가 완전 탐색보다 적다
|효율|효율이 낮다.|효율이 높다.
|저장|하위 문제의 결과를 저장하기 위한 추가 공간이 필요없다.|하위 문제에 대한 결과를 저장하기 위한 추가 공간이 필요하다.  

**📚 추가 학습**  
- [Closet-Pair Problems by Brute Force
Convex-Hull Problems by Brute Force](http://www.csl.mtu.edu/cs4321/www/Lectures/Lecture%206%20-%20Brute%20Force%20Closest%20Pair%20and%20Convex%20and%20Exhausive%20Search.htm)

-----
## Binary Search Algorithm  

>원하는 정보를 구글링을 통해 찾을 때, 구글에서는 관련성이 높은 검색 결과를 정리해두고 원하는 정보를 찾도록 제시하는 방법을 사용한다.   
이때 정리하는 과정은 정렬 알고리즘을 사용하고 찾는 과정은 검색(탐색) 알고리즘을 사용한다. 이렇게 수많은 데이터 중에서 원하는 데이터를 찾아낼 때 **탐색 알고리즘** 을 활용한다.

**탐색 알고리즘 종류**  
- [Linear Search Algorithm(선형 탐색 알고리즘)](https://www.geeksforgeeks.org/linear-search/)  
- **Binary Search Algorithm(이진 탐색 알고리즘)**  
- [Hash Search Algorithm(해시 탐색 알고리즘)](https://www.tutorialspoint.com/data_structures_algorithms/hash_data_structure.htm)

>**이진 탐색 알고리즘(Binary Search Algorithm)**  
>
데이터가 정렬된 상태에서 절반씩 범위를 나눠 분할 정복기법으로 특정한 값을 찾아내는 알고리즘.

### 동작단계  

1. 정렬된 배열의 가장 중간 인덱스를 지정한다.
2. 찾으려고 하는 값이 지정한 중간 인덱스의 값이라면 탐색을 종료, 아니면 3단계로 간다.
3. 찾으려고 하는 값이 중간 인덱스의 값보다 큰 지, 작은 지 확인한다.  
4. 값이 있는 부분과 값이 없는 부분으로 분리한다.
5. 값이 있는 부분에서 다시 1단계부터 반복한다.

```java
// 이진 탐색 알고리즘을 이용해 특정 num 찾기
int[] arr = {0,1,2,3,4,5,6,7,8,9,10};
int num = 6;
1 Step - 찾으려는 6이 중간 인덱스 5보다 크기 때문에 5보다 큰 부분을 새로운 범위로 설정하여 다시 찾는다.
2 Step - 찾으려는 6이 1 Step의 큰 부분의 중간 인덱스 8보다 작기 때문에 8보다 작은 부분을 새로운 범위로 설정하여 다시 찾는다.
3 Step - 찾으려는 6이 2 Step의 큰 부분의 중간 인덱스 6와 같으므로 탐색을 종료한다.
```

같은 값을 Linear Search Algorithm으로 찾아본다면 7번의 과정이 필요하다.  

### Binary Search Algorithm 사용 경우

- 정렬된 배열에서 요솟값을 더 효율적으로 검색할 때  
- 정렬된 데이터의 양이 많을 때 (많을 수록 효율이 높다.)   

시간복잡도는 O(logn)로, 빠른 편이지만 항상 효율이 좋은 것은 아니다.  
-> 앞쪽에 위치한 데이터를 탐색할 때는 선형 탐색이 빠른 구간이 존재한다.

### Binary Search Algorithm 한계  

- 배열에만 구현할 수 있다.
- 정렬되어 있어야만 구현할 수 있다.  
규모가 작은 배열은 정렬이 안 되어 있으면 정렬을 해도 효율이 높지 않다.  

### Binary Search Algorithm 활용 예시  

대규모의 데이터 검색에 주로 사용한다.  

- 사전 검색   
사전에서 단어를 찾을 때 사용.  

- 도서관 도서 검색  
도서관에서 사용하는 도서 코드로 도서를 검색할 때 사용  

- 대규모 시스템에 대한 리소스 사항 파악  
시스템 부하 테스트에서 예측된 부하를 처리하는데 필요한 CPU 양에 대해서 파악할 때 사용   

- 반도체 테스트 프로그램은 디지털, 아날로그 레벨을 측정하는데 사용  

### Binary Search Algorithm - Binary Search Tree  

Tree - 자료구조   
Algorithm - 해결 방법  

**Binary Search Tree**  
하나의 노드가 두 개의 하위 트리를 가지는 이진 트리로 이루어진 자료구조.   

**Binary Search Tree(BST)의 규칙**  
부모노드는 왼쪽 자식노드보다 큰 값을 가진다.  
부모노드는 오른쪽 자식노드보다 큰 값을 가진다.    


**📚 추가 학습**  
- [Divide-and-conquer algorithm](https://www.khanacademy.org/computing/computer-science/algorithms/merge-sort/a/divide-and-conquer-algorithms)
- [Binary Tree vs Binary Search Tree](https://www.upgrad.com/blog/binary-tree-vs-binary-search-tree/)

-----
## Algorithm with Math  
### 순열(permutation)과 조합(Combination)  

>**순열**  
요소 n개 중에 m개를 선택하여 순서에 상관 있게 뽑는 경우의 수.  
>
**조합**   
순서에 상관없이 요소 n개 중에 m개를 뽑는 경우의 수.  
>
**! (factorial, 팩토리얼)**  
n! 은 n에서부터 1씩 감소하여 1까지의 모든 정수의 곱이다.   
(n 보다 작거나 같은 모든 양의 정수의 곱)    
팩토리얼에서, 0!과 1!은 모두 1이다.  

### 문제 - 카드 뽑기  

A, B, C, D, E로 이뤄진 5장의 카드가 있다.  
이 5장의 카드 중 3장을 선택하여 나열하려고 한다.   
이때, 다음의 조건을 각각 만족하는 경우를 찾아야 한다.  

1. 순서를 생각하며 3장을 선택한다.(순열)  
2. 순서를 생각하지 않고 3장을 선택한다.(조합)   

각 조건을 만족시키며 카드를 나열하는 방법은 각각 몇 가지일까?

**1. 순열**  
순서를 생각하며 3장을 선택할 때의 모든 경우의 수

1. 첫번째 나열하는 카드를 선택하는 방법에는 다섯 가지가 있다.
2. 첫번째 카드를 나열한 후, 두번째 카드를 선택하는 방법은 네 가지가 있다.
3. 두번째 카드를 나열한 후, 세번째 카드를 선택하는 방법은 세 가지가 있다.   

`일반식 : nPr = n! / (n - r)!` 

-> `(5X4X3X2X1) / (2X1) = 60` 가지의 방법이 있다. 

```java
public static ArrayList<String[]> permutation() {
    String[] cards = new String[]{"A", "B", "C", "D", "E"};
    ArrayList<String[]> result = new ArrayList<>();
    
    for (int i = 0; i < cards.length; i++) {
      for (int j = 0; j < cards.length; j++) {
        for (int k = 0; k < cards.length; k++) {
          if (i == j || j == k || k == i) continue;
          // 중복된 요소는 제거
            String[] input = new String[]{cards[i], cards[j], cards[k]}; 
            // 반복문의 개수 == 요소를 뽑는 개수
            result.add(input);
        }
      }
    }
  return result;
}
```

**2. 조합**   
순서를 생각하지 않고 3장을 선택할 때의 모든 경우의 수   

1. 순열로 구할 수 있는 경우를 찾는다.  
2. 순열로 구할 수 있는 경우에서 중복된 경우의 수를 나눈다.  

`일반식: nCr = n! / (r! * (n - r)!)`

-> `(5X4X3X2X1) / ((3X2X1) X (2X1)) = 10` 가지의 방법이 있다.  

```java
public static ArrayList<String[]> combination() {
  String[] cards = new String[]{"A", "B", "C", "D", "E"};
  ArrayList<String[]> result = new ArrayList<>();
// 순열과 다른 점 -> 반복의 조건 (i = 0, j = i + 1, k = j + 1)
  for(int i = 0; i < cards.length; i++) {
    for(int j = i + 1; j < cards.length; j++) {
      for(int k = j + 1; k < cards.length; k++) {
        String[] input = new String[]{cards[i], cards[j], cards[k]};
				result.add(input);
      }
    }
  }
  return result;
}
```

### 순열과 조합의 한계점  

뽑아야하는 개수가 늘어나면 반복문의 수도 늘어난다.  

-> 재귀를 사용하여 풀이하는 경우가 많다.   

-----
## 정규 표현식  

![](https://velog.velcdn.com/images/wlsk124/post/7f46d62e-e508-4277-8214-2800ae4d9143/image.jpeg)

>**정규 표현식(정규식:正規式)**  
문자열에서 특정한 규칙에 따른 문자열 집합을 표현하기 위해 사용되는 형식 언어.   
정규표현식에서의 특수 문자는 각각 고유한 규칙을 갖고 있다.   
정규표현식을 사용하면 수십 줄이 필요한 코딩 작업을 간단하게 한두 줄로 끝낼 수 있다.   

### 정규 표현식 예시  

**이메일 유효성 검사**  

```java
String email = "example@gmail.com";
String regExp = "\\w+@\\w+\\.\\w+(\\.\\w+)?";

// Patten.matches 메서드 - 결과를 boolean타입으로 확인.

if(Pattern.matches(regExp, email)) System.out.println("올바른 이메일 주소입니다.");
else System.out.println("정확한 이메일 주소를 입력해 주세요.");
```

**휴대전화 번호 유효성 검사**  

```java
String regExp = "^01(?:0|1|[6-9])-(?:\d{3}|\d{4})-\d{4}$";
```

**정규표현식을 활용한 알고리즘 예제**   

>문자열의 길이가 5 또는 7이면서 숫자(0~9)로만 구성되어 있는지를 확인하는 함수를 작성하고,  
>결과는 Boolean으로 리턴하시오.   

```java
// 정규표현식 사용
public boolean example1(String str) {
	String regExp = "\\d{5}$|\\d{7}$"
	return Pattern.matches(regExp, str)
}

// 정규표현식 미사용
public boolean example2(String str) {
	if(str.length() == 5 || str.length() == 7) {
		for(int i = 0; i < str.length(); i++) {
			if(!Character.isDigit(str.charAt(i))) return false;
		}
		return true;
	}
	return false;
}
```

[정규표현식을 익힐 수 있는 웹페이지](https://www.regexplanet.com/)
