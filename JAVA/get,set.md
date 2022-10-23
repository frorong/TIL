# 접근자와 설정자
+ 클래스 멤버를 외부에서 조작할 수 없도록 하려면 private로 지정한다
+ 클래스의 모든 멤버가 private면 안 된다

+ get
```java
public int getInt(){
    return num;
}
```
+ set
```java
public void setInt(int num){
    this.num = num;
}