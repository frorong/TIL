# 상속과 접근 제어
+ 캡슐화는 클래스 멤버를 숨기는 것이다
+ public : 전범위 공개
+ protected : 다른 패키지 제외 공개
+ default : 자식, 다른 패키지 제외 공개
+ private : 동일 클래스 제외 비공개

### 주의사항
+ private 멤버는 상속되지 않는다
+ 클래스는 protected와 private로 지정 불가
+ 오버라이딩할 때 부모 클래스의 메서드보더 좁은 접근 지정 불가
    + ex) 부모가 protected인데 자식이 private 불가

### final
+ final class : 더이상 상속이 불가능한 종단 클래스이다
+ final method : 더이상 오버라이딩 불가한 종단 메서드이다