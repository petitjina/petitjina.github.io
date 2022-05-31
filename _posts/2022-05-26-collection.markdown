---
title: "Collection"
layout: post
date: 2022.05.26
headerImage: false
tag:
- Java
- Concept
- Back-end
category: study
author: Jina Kim
---

## Generic
클래스 내부에서 사용할 데이터 타입을 외부에서 파라미터 형태로 지정하면서 타입을 일반화 한다.  
-> 제네릭 없이 객체에 여러 자료형을 받으려면 int, float, string 등 모든 자료형에 대해 클래스를 만들어야 한다.  


**제네릭 생성**  
```java
public class 클래스명<타입 매개변수>{ ... }
public interface 인터페이스명<타입 매개변수>{ ... }

```
**타입의 매개변수**  

|타입인자	|설명
|:------:|:----:
|&#60;T&#62;|	Type
|&#60;E&#62;|	Element
|&#60;K&#62;|	Key
|&#60;N&#62;|	Number
|&#60;V&#62;|	Value
|&#60;R&#62;|	Result
  
### 제네릭의 필요성  

```java
public class Box {}

public class Box extends Object {}
//두개는 같은 클래스다. 
//Java의 모든 클래스는 Object클래스를 상속받아 확장된다.
```

코드의 중복을 줄이고 효율적으로 코드를 짜기 위해 제네릭이 생겼다.  

**예시 코드**  

```java
// 제네릭 타입의 Box 클래스
public class Box <T> {
	private T t;
	public T get() { return t; }
	public void set(T t) { this.t = t; }
}
```
```java
// 일반 Box 클래스 생성(타입의 종류만큼 생성해야 한다) 
// new Box<String>();
public class Box {
	private String t;
	public String get() { return t; }
	public void set(String t) { this.t = t; }
}

// new Box<Integer>();
public class Box {
	private Integer t;
	public Integer get() { return t; }
	public void set(Integer t) { this.t = t; }
}
```
```java
// 입력 후 값은 같다(제네릭 타입의 클래스 == 일반 클래스)
public class Main {
	public static void main(String[] args) {
		Box<String> box1 = new Box<String>();
		box1.set("String");
		String str = box1.get();

		Box<Integer> box2 = new Box<Integer>();
		box2.set(1);
		int value = box2.get();
	}
}

```
  


**제네릭의 장점**  
1. 타입체크와 형변환을 생략해서 간결한 코드 작성이 가능  
2. 클래스나 메서드 내부에서 사용되는 객체의 타입 안정성을 제공  

### 제네릭 클래스 정의   

여러 참조 자료형을 사용해야 하는 경우에 Object가 아닌 하나의 문자로 표현.  
**제네릭 타입의 클래스 선언**  

```java
접근 제어자 class 클래스명<T> { // 제네릭 타입 매개변수가 1개일 때
 //타입 T를 사용
}

접근 제어자 class 클래스명<K, V> { //제네릭 타입 매개변수가 2개일때
 //타입 K, V를 사용한 코드
}

// 제네릭 타입의 클래스 선언(예시)
public class Box <T> {}

// 제네릭 타입의 인터페이스 선언(예사)
public interface Box <T> {}
```

**제네릭 클래스의 사용 단계**  

```java
// 1. 템플릿 형태의 제네릭 클래스 정의
class Example<T> {
}

// 2. 제네릭 클래스에 속성과 메서드 정의  
class Example<T> {
	private T t;
	public T get() { return t; }
	public void set(T t) { this.t = t; }
}
// 3. 제네릭 객체 생성 
Example <String> ex = new Example<String>();

// 4. 제네릭 객체 사용
ex.set("Kim Jina");
System.out.println(ex.get()); // Kim Jina
```
 
다이아몬드 연산자 &#60; &#62;
```java
// 제네릭 클래스를 생성할 때 생성자에 자료형을 명시하지 않을 수 있다.
ArrayList<String> list = new ArrayList<>();
```

와일드카드 ?
-> 제한을 두지 않는 기호
```java
<?> //타입 매개변수에 모든 타입 사용
<? extends T> //T 타입과 T타입을 상속받는 하위 클래스 타입만 사용
<? super T> // T 타입과 T타입을 상속받은 상위 클래스 타입만 사용
```

### 제네릭 메서드

클래스 내부의 특정 메서드만 제네릭으로 선언.  
제네릭 메서드는 호출되는 시점에서 실제 제네릭 타입을 지정.   
해당 메서드 안에서만 사용할 수 있는 지역 변수처럼 사용.  

```java
class Example { //일반 클래스 내부의 제네릭 메서드를 선언
    public <T> T accept(T t){
        return t;
    }
    public <K, V> void getPrint(K k, V v) { //리턴 타입 앞에 타입 매개변수 선언
        System.out.println(k+ ":" + v);
    }
}
```
제네릭 메서드를 정의하는 시점에서는 실제 어떤 타입이 입력 되는지 알 수 없다.  
-> length()와 같은 String 메서드는 정의하는 시점에서 사용 불가능. 
-> 최상위 클래스인 Object 클래스의 메서드는 사용 가능.   
```java
//불가능한 제네릭 메서드 예시
class Example {
    public <T> void print(T t) {
        System.out.println(t.length()); 
        //String 클래스 메서드 length()는 사용 불가능
    }
}
```

```java
//가능한 제네릭 메서드 예시
class Example {
    public <T> void getPrint(T t) {
        System.out.println(t.equals("Kim jina")); 
        //Object 클래스 메서드 equals는 사용 가능
    }
}
```

**Object 클래스의 메서드**   

|제어자 및 타입|메서드|설명
|:-------:|:-----:|:--:
|protected Object|clone()|해당 객체의 복제본을 생성하여 반환.
|boolean|equals(Object obj)|해당 객체와 전달받은 객체가 같은지 여부 반환.
|protected void|finalize()|	해당 객체를 아무도 참조하지 않아 가비지 컬렉터가 객체의 리소스를 정리.
|Class&#60;T&#62;|getClass()|해당 객체의 클래스 타입을 반환.
|int|hashCode()|해당 객체의 해시 코드값을 반환.
|void|notify()|해당 객체의 대기(wait)하고 있는 하나의 스레드를 다시 실행.
|void|notifyAll()|해당 객체의 대기(wait)하고 있는 모든 스레드를 다시 실행.
|String|toString()|	해당 객체의 정보를 문자열로 반환.
|void|wait()|해당 객체의 다른 스레드가 notify()나 notifyAll() 메소드를 실행할 때까지 현재 스레드를 일시적으로 대기(wait).
|void|wait(long timeout)|해당 객체의 다른 스레드가 notify()나 notifyAll() 메소드를 실행하거나 전달받은 시간이 지날 때까지 현재 스레드를 일시적으로 대기(wait).
|void|wait(long timeout, int nanos)|해당 객체의 다른 스레드가 notify()나 notifyAll() 메소드를 실행하거나 전달받은 시간이 지나거나 다른 스레드가 현재 스레드를 인터럽트(interrupt) 할 때까지 현재 스레드를 일시적으로 대기(wait).



-----
## Collection Framework

**Java 컬렉션 프레임워크 구조**
![](https://velog.velcdn.com/images/wlsk124/post/50aadbfa-9079-460b-93ac-8f7522296a8e/image.png)


컬렉션 프레임워크의 주요 인터페이스로 - List, Set, Map  

List, Set - 객체 추가, 삭제, 검색  
Map - 키(Key)와 값(Value)을 하나의 쌍으로 묶어서 관리  

|인터페이스|특징|구현 클래스
|:-----:|:--:|:-----:
|List|순서를 유지하고 저장, 중복저장 가능|	ArrayList, Vector, Stack, LinkedList 등
|Set|순서를 유지하지 않고 저장, 중복저장 불가능|HashSet, TreeSet 등
|Map|키(key)와 값(value)의 쌍으로 저장, 순서 유지하지 않음, 키는 중복저장 불가능|HashMap, Hashtable, TreeMap, Properties 등

### List&#60;E&#62;

객체를 일렬로 늘어놓은 구조  
객체를 인덱스로 관리하기 때문에 객체를 저장하면 자동으로 인덱스가 부여되고,  
인덱스로 객체를 검색, 삭제할 수 있는 기능을 제공한다.  
List 인터페이스를 구현한 클래스로는 ArrayList, Vector, LinkedList, Stack 등이 있다.  

|기능|리턴 타입|메서드|설명
|:----:|:------:|:----:|:----:
|객체 추가|void|add(int index, Object element)|주어진 인덱스에 객체 추가
||boolean|addAll(int index, Collection c)|주어진 인덱스에 컬렉션 추가
||Object|set(int index, Object element)|주어진 위치에 객체 저장
|객체 검색|Object|get(int index)|주어진 인덱스에 저장된 객체 반환
||int|indexOf(Object o) / lastIndexOf(Object o)|순방향/역방향으로 탐색해 주어진 객체의 위치 반환
||ListIterator|listIterator() / listIterator(int index)|List의 객체를 탐색하는 ListIterator 반환 / 해당 index부터 탐색하는 ListIterator 반환
||List|subList(int fromIndex, int toIndex)|fromIndex부터 toIndex에 있는 객체 반환
|객체 삭제|Object|remove(int index)|해당 인덱스에 저장된 객체를 삭제, 삭제된 객체 반환
||boolean|remove(Object o)|주어진 객체 삭제
|객체 정렬|void|sort(Comparator c)|주어진 비교자(comparator)로 List 정렬

**ArrayList**   

ArrayList는 List 인터페이스를 구현한 클래스   

객체를 추가하면 객체가 인덱스로 관리되고, 저장 용량을 초과한 객체들이 들어와도 자동으로 저장용량이 늘어난다.   
데이터가 연속적으로 존재.

ArrayList를 생성은 저장할 객체를 제네릭으로 표기하고 기본 생성자를 호출.  
```java
List<타입 파라미터> 객체명 = new ArrayList<타입 파라미터>(초기 저장용량);
```
객체를 추가하면 인덱스가 차례대로 저장되고 객체를 제거하면, 앞으로 1씩 당겨진다.   
-> 빈번한 객체 삭제와 삽입은 ArrayList보다 LinkedList가 적절하다.  


```java
List<String> list = new ArrayList<String>(); //ArrayList 생성

list.add("Java"); // String 객체 추가

int size = list.size(); // 저장된 총 객체 수 (배열로 치면 길이에 해당)
String skill = list.get(0); // 0번 인덱스의 객체 얻기

list.remove(0); // 0번 인덱스 객체 삭제
```

**LinkedList**   

LinkedList 컬렉션은 데이터를 효율적으로 추가, 삭제, 변경하기 위해 사용.  
데이터가 불연속적으로 존재하며, 서로 연결(link)되어 있다.
![](https://velog.velcdn.com/images/wlsk124/post/25f3785d-f521-4bf3-8719-b48a6ded78a0/image.png)


데이터(B)를 삭제하려면, A 요소가 C 요소를 참조하도록 변경 하면 된다.   
-> 링크를 끊어주는 방식. 배열처럼 데이터를 이동하기 위해 복사할 필요가 없다.  

데이터를 추가하려면, 추가할 위치의 이전 요소와 다음 요소 사이에 연결하면 된다.   
 
**ArrayList와 LinkedList 차이**  

ArrayList    

: 인덱스가 n인 요소의 주소값을 얻기 위해서 ```배열의 주소 + n * 데이터 타입의 크기```를 계산하여 데이터에 빠르게 접근하기 때문에 검색(읽기) 측면에서 유리.  

LinkedList   

: 데이터의 추가, 삭제 시 참조만 변경하기 때문에, 다른 데이터를 복사할 필요가 없다.  

-> 데이터의 잦은 변경이 예상된다면 LinkedList,   
데이터의 개수가 변하지 않는다면 ArrayList  

**Iterator**   

컬렉션에 저장된 요소를 읽어오는 방법.  

**Iterator 인터페이스에 선언된 메서드 **  
 
| 메서드 | 설명 
|:---:|:---:
| hasNext() | 가져올 객체가 있으면 true를 리턴하고, 없으면 false를 리턴한다 
| next() | 컬렉션에서 하나의 객체를 가져온다 
| remove() | 컬렉션에서 객체를 제거한다   


```java
List<String> list = ...;
Iterator<String> iterator = list.iterator();

while(iterator.hasNext()) { //괄호 안의 내용이 true이면
	String str = iterator.next(); //객체 하나를 가져온다.
    if(str.equals("단어")){ //가져온 객체와 비교해서, if문이 true면,
		iterator.remove(); //해당 객체 제거
}
```  

```java
//Iterator를 사용하지 않고, 향상된 for문을 이용해서 전체 객체를 대상으로 반복 가능.
List<String> list = ...;
for(String str : list) {
	// 저장된 객체 수만큼 반복한다.
}
```

### Set&#60;E&#62;

Set을 구현한 대표적인 클래스에는 HashSet, TreeSet이 있다.  

**List와 Set이 포함된 컬렉션 인터페이스에서 제공하는 주요 메서드**  

|기능|리턴 타입|메소드|설명
|:---:|:----:|:----:|:-----:
|객체 추가|boolean|add(Object o), addAll(Collection c)|주어진 객체 / 컬렉션의 객체들을 컬렉션에 추가
|객체 검색|boolean|contains(Object o), containsAll(Collection c)|주어진 객체 / 컬렉션이 저장되어 있는지 여부
||Iterator|iterator()|컬렉션의 iterator를 반환
||boolean|equals(Object o)|컬렉션이 동일한지 여부
||boolean|isEmpty()|컬렉션이 비어있는지 여부
||int|size()|저장되어 있는 전체 객체 수를 반환
|객체 삭제|void|clear()|컬렉션에 저장된 모든 객체를 삭제
||boolean|remove(Object o), removeAll(Collection c)|주어진 객체 / 컬렉션을 삭제하고 성공 여부를 반환
||boolean|retainAll(Collection c)|주어진 컬렉션을 제외한 모든 객체를 삭제하고 컬렉션에 변화 여부를 반환
|객체 변환|Object&#91; &#93;|toArray()|컬렉션에 저장된 객체를 객체배열(Object &#91; &#93;)로 반환
||Object&#91; &#93;|toArray(Object&#91; &#93; a)|주어진 배열에 컬렉션의 객체를 저장해서 반환

**HashSet**   

```java
public class Main {
    public static void main(String[] args) {
        HashSet<String > fruit = new HashSet<String>();

        languages.add("딸기");
        languages.add("바나나");
        languages.add("포도");
        languages.add("딸기");

        Iterator it = fruiy.iterator();

        while(it.hasNext()) {
            System.out.println(it.next());
        }
    }
}
//Output
포도
바나나
딸기
```
입력한 순서대로 출력되지 않고, “딸기”를 두 번 추가했지만 한 번만 저장되었다.  

**TreeSet**   

이진 탐색 트리 형태로 데이터를 저장.  

**이진 탐색 트리(Binary Search Tree)란**  

하나의 부모 노드가 최대 두 개의 자식 노드와 연결되는 이진 트리의 일종.  
정렬과 검색에 특화된 자료 구조다.   

최상위 노드를 ‘루트'라고 하고, 모든 왼쪽 자식의 값이 루트나 부모보다 작고,  
모든 오른쪽 자식의 값이 루트나 부모보다 큰 값을 가진다.  
![](https://velog.velcdn.com/images/wlsk124/post/227b27a8-6dad-4b54-aba1-c048edea7788/image.png)


```java
public class TreeSetExample {
    public static void main(String[] args) {
        TreeSet<String> fruit = new TreeSet<>();

        workers.add("포도");
        workers.add("딸기");
        workers.add("바나나");

        System.out.println(fruit);
        System.out.println(fruit.first());
        System.out.println(fruit.last());
    }
}
// Output
[딸기, 바나나, 포도]
딸기
포도
```
출력값이 오름차순으로 정렬. (기본 정렬이 오름차순)

**Comparator와 Comparable**   

컬렉션을 정렬하기 위해 자바에서 제공하는 인터페이스.   
두 인터페이스의 차이점은, Comparable은 비교 대상(매개 변수)과 자기 자신을 비교하고, Comparator는 매개 변수인 두 객체를 비교한다.  

Comparable 인터페이스는 compareTo() 메서드를 사용한다.  
compareTo()는 비교하는 두 객체가 같으면 0, 비교할 객체가 주어진 객체보다 작으면 음수, 크면 양수를 반환한다.


Comparator 인터페이스는 compare() 메소드를 재정의(오버라이딩)한다.  
주로, 기본 정렬 기준이 아닌 다른 기준으로 정렬하고 싶을 때 사용한다.   

### Map&#60;K, V&#62;

키(key)와 값(value)으로 구성된 Entry 객체를 저장하는 구조를 가지고 있다.   
map이란 어떤 두 데이터(키와 값)를 연결한다는(매핑) 의미.  

키는 중복 저장될 수 없지만, 값은 중복 저장이 가능하다.  
기존에 키와 동일한 키로 값을 저장하면, 기존의 값은 없어지고 새로운 값으로 대치된다.

**Map 인터페이스 메서드**  

|기능|리턴 타입|메서드|설명
|:---:|:----:|:----:|:---:
|객체 추가|Object|put(Object key, Object value)|주어진 키로 값을 저장, 새로운 키일 경우 null을 리턴하고 동일한 키가 있을 경우 값을 대체하고 이전값을 리턴
|객체 검색|boolean|containsKey(Object key)|주어진 키가 있으면 true, 없으면 false를 리턴
||boolean|containsValue(Object value)|주어진 값이 있으면 true, 없으면 false를 리턴
||Set|entrySet()|키와 값의 쌍으로 구성된 모든 Map.Entry 객체를 Set에 담아서 리턴
||Object|get(Object key)|주어진 키에 해당하는 값을 리턴
||boolean|isEmpty()|컬렉션이 비어 있는지 확인
||Set|keySet()|모든 키를 Set 객체에 담아서 리턴
||int|size()|저장된 키-값 쌍의 총 갯수를 리턴
||Collection|values()|저장된 모든 값을 Collection에 담아서 리턴
|객체 삭제|void|clear()|모든 Map.Entry(키와 값)을 삭제
||Object|remove(Object key)|주어진 키와 일치하는 Map.Entry를 삭제하고 값을 리턴

**HashMap**  

HashMap은 Map 인터페이스를 구현한 대표적인 클래스  
해싱(Hashing)을 사용해서 많은 양의 데이터를 검색하는 데 뛰어난 성능을 보인다.  

```java
//키 타입과 값 타입을 파라미터로 주고 기본 생성자 호출
Map<Key, Value> map = new HashMap<Key, Value>();
```
키와 값의 타입은 기본 타입을 사용할 수 없고, 클래스 및 인터페이스 타입만 가능.   
HashMap은 키(key)와 값(value)에 null 값 허용, Hashtable은 null 값을 허용 안함.   


-----
## Inner Class

클래스 내에 선언된 클래스. 외부 클래스와 내부 클래스가 서로 연관되어 있을 때 사용.  
내부 클래스는 외부 클래스의 멤버에 접근 할 수 있고, 코드의 복잡성을 줄일 수 있다.  

```java
// 예시
class Outer { // 외부 클래스
	class Inner {
		// 인스턴스 내부 클래스	
	}
	static class StaticInner {
		// 정적 내부 클래스
	}
	void run() {
		class LocalInner {
		// 지역 내부 클래스
		}
	}
}
``` 

|종 류|선언 위치|사용 가능한 변수
|:-----:|:-----:|:-----:
|인스턴스 내부 클래스(instance inner class)|	외부 클래스의 멤버변수 선언위치에 선언(멤버 내부 클래스)|외부 인스턴스 변수, 외부 전역 변수
|정적 내부 클래스(static inner class)|	외부 클래스의 멤버변수 선언위치에 선언(멤버 내부 클래스)|외부 전역 변수
|지역 내부 클래스(local inner class)|외부 클래스의 메서드나 초기화블럭 안에 선언|외부 인스턴스 변수, 외부 전역 변수
|익명 내부 클래스(anonymous inner class)|클래스의 선언과 객체의 생성을 동시에 하는 일회용 익명 클래스|외부 인스턴스 변수, 외부 전역 변수

### 멤버 내부 클래스

멤버 내부 클래스에는 인스턴스 내부 클래스와 정적 내부 클래스가 있다.

**인스턴스 내부 클래스**   

객체 내부에 멤버의 형태로 존재한다.  
외부 클래스의 모든 접근 지정자의 멤버에 접근할 수 있다.  

```java
class Outer {
    private int num = 1; //private 변수
    private static int sNum = 2; //클래스의 정적 변수

    private InClass inClass;

    public Outer() {
        inClass = new InClass(); // 외부 클래스 생성자
    }

    class InClass { //인스턴스 내부 클래스
        int inNum = 2; //내부 클래스의 인스턴스 변수

        void Test() {
            System.out.println("Outer num = " + num + "(외부 클래스의 인스턴스 변수)");
            System.out.println("Outer sNum = " + sNum + "(외부 클래스의 정적 변수)");
        }
    }
    public void testClass() {
        inClass.Test();
    }
}
public class Main {
    public static void main(String[] args) {
        Outer outer = new Outer();
        System.out.println("외부 클래스 사용하여 내부 클래스 기능 호출");
        outer.testClass(); // 내부 클래스 기능 호출
    }
}
```
외부 클래스의 num과 sNum은 private 예약어로 선언되었지만 내부 클래스에서 사용 가능하다.   
클래스의 생성과 상관없이 사용할 수 있는 정적 변수와 정적 메서드는 인스턴스 내부 클래스에서 선언할 수 없다.  


**정적 내부 클래스**  

내부 클래스가 정적 변수를 사용하려면 정적 내부 클래스를 선언하면 된다.   
정적 내부 클래스는 인스턴스 내부와 같이 클래스의 멤버 변수 위치에 정의하며 static 예약어를 사용한다.

```java
class Outer { //외부 클래스
    private int num = 3; //내부 클래스의 인스턴스 변수
    private static int sNum = 4;

    void getPrint() {
        System.out.println("인스턴스 메서드");
    }

    static void getPrintStatic() {
        System.out.println("스태틱 메서드");
    }

    static class StaticInClass { // 정적 내부 클래스
        void test() {
            System.out.println("Outer num = " +sNum + "(외부 클래스의 정적 변수)");
            getPrintStatic();
            // num 과 getPrint() 는 정적 멤버가 아니라 사용 불가능.
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Outer.StaticInClass a = new Outer.StaticInClass(); //정적 이너 클래스의 객체 생성
        a.test();
    }
}

```
### 지역 내부 클래스

클래스의 멤버가 아닌 메서드 내에서 정의되는 클래스.  

```java
class Outer {
    int num1 = 1;
    void test() {
        int num2 = 2;
        class LocalIn { //지역 내부 클래스
            void getPrint() {
                System.out.println(num1);
                System.out.println(num2);
            }
        }
        LocalIn localIn = new LocalIn();
        localIn.getPrint();
    }
}
public class Main {
    public static void main(String[] args) {
        Outer outer = new Outer();
        outer.test();
    }
}

```
### 익명 내부 클래스

이름을 알 수 없는 내부 클래스를 의미.   
클래스의 선언과 객체 생성을 동시에 하기 때문에 하나의 객체만을 생성하고, 일회용이다.   
지역 내부 클래스와 유사하다.
