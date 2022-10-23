# 문자열
+ 문자열은 String 타입을 사용한다
+ String은 자바가 기본으로 제공하는 클래스이다
```java
//초기화
String str = "문자열";
```
+ 내용이 같은 문자열이면 더 이상 새로운 객체를 생성하지 않고 기존의 것을 공유한다

## 문자열 비교!!!
+ 문자열의 내용 비교시 ==나 !=를 사용하면 안 된다  
==나 !=는 동인한 객체인지 검사한다
```java
String s1 = "str";
String s2 = new String("str");
// s1 != s2
String s3 = "str";
//s1 == s3
s1 = s3;
//s1 == s3
```

## 문자열 비교 메서드!!!
+ ```int compareTo(String s)``` : 문자열을 사전 순으로 비교해 정숫값을 반환
+ ```int compareToIgnoreCase(String s)``` : 대소문자 무시 문자열 사전 순으로 비교
+ ```boolean equals(String s)``` : s와 현재 문자열 비교 true/false
+ ```boolean equalsIgnoreCase(String s)``` s와 현재 문자열 대소문자 구분 없이 true/false

+ 쉽게 말하면 compareTo는 문자열을 빼는거고 equals가 같은지 다른지 보는 것이다

## 문자열의 다양한 연산!!!!!
+ char charAt(int index) : index가 지정한 문자를 반환
+ String concat(String s) : 주어진 문자열 s를 현재 문자열 뒤에연결
+ boolean contains(String s) : 문자열 s를 포함하는지 조사
+ boolean endsWith(String s) : 끝나는 문자열이 s인지 조사
+ int indexOf(String s) : 문자열 s가 나타난 위치를 반환
+ boolean isBlank() : 길이가 0 혹은 공박 앴으면 true반환
+ boolean isEmpty() : 길이가 0이면 true를 반환
+ int length() : 길이를 반환
+ String repeat(int c) : c번 반복한 문자열을 반환
+ boolean startsWith(String s) : 시작하는 문자열이 s인지 조사
+ String substring(int index) : index부터 시작하는 문자열의 일부를 반환
+ String toLowerCase() : 모두 소문자로 변환
+ String toUpperCase() : 모두 대문자로 변환
+ String trim() : 앞뒤에 있는 공백을 제거한 후 반환