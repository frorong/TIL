# 배열
+ 동일한 데이터 타입의 집합을 쉽게 처리하기 위한 구조

### 선언
+ 너무 더럽다
```java
int[] scores;
//or
int scores[]
```
``` java
scores = new int[n];
```
```java
int[] scores = new int[n];
```
```java
int[] scores = {n,n1,n2,n3};
```
```java
int[] scores = new int[] {n1,n2,n3}
```
```java
int[] scores;
scores = new int[] {n,n1,n2};
```
```java
//XXXXXXXXXXXXXXXXXXXXX
int[] scores;
scores = {n,n1,n2,n3};
```

### 배열 원소의 접근과 배열의 크기   
+ 배열의 원소는 인덱스로 접근할 수 있다  
배열의 크기는 name.length에서 볼 수 있다

## 동적 배열!!!
+ 자바는 크기가 유동적인 배열을 지원하기 위해 ArrayList를 제공한다
+ 선언
```java
ArrayList<type> name = new ArrayList<>();
```
+ 사용
    + .add(데이터) : 데이터 추가
    + .remove(인덱스번호) : 데이터 제거
    + .get(인덱스번호) : 원소 가져오기
    + .size() : 원소의 개수

### for each
+ 형식
```java
for(type i : array or colection){

}
```
+ for each문은 배열이나 컬렉션의 모든 원소를 처음부터 대입하여 처리한다
+ for each 변수는 final로 지정하지 않아도 final 타입이다
+ 반복시 새로운 변수가 생성된다

### 메서드의 인수로 배열 전달
+ 배열도 메서드의 인수로 사용 가능하다
+ 메서드에서 배열을 건드리면 배열에게 영항을 주게된다
