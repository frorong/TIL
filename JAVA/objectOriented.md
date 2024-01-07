# 객체 지향

### 객체
+ 현실 세계에서 구체적이거나 추상적인 사물

### 절차 지향 vs 객체 지향
+ 절차 지향 : 인련의 동작을 순서에 맞추어 단계적으로 실행
+ 객체 지향 : 현실 세계의 특성을 고려하여 객체 단위로 프로그래밍

### 객체와 클래스
+ 클래스는 객체를 만들 수 있는 틀이다
+ 객체는 해당 클래스의 인스턴스이다
+ 필드는 상태를 나타내고 메서드는 동작을 시킨다

## 특징
### 캡슐화
+ 필드와 메서드를 외부에서 알 수 없도록 은닉하는 것

### 상속
+ 상위 객체를 상속받은 하위 객체가 상위 객체의 메서드와 필드를 사용할 수 있다
+ 메서드를 다시 정의해서 사용할 수도 있으며 새로운 필드나 메서드를 추가할 수 있다

### 다형성
+ 대입되는 객체에 따라서 메서드를 다르게 동작하도록 구현한다

### 객체 생성과 참조 변수
```java
ClassName cn = new ClassName();
```
+ 참조 변수는 자기 객체가 아니라 자기 객체를 가리키는 주소를 저장한다