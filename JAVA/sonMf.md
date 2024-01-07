# 자식 클래스와 부모 생성자

+ 생성자는 자식 클래스에 상속되지 않는다
+ 부모에게 물려받은 멤버가 있다면 이를 초기화하기 위해 부모 클래스의 생성자가 필요하다
+ 자식 생성자를 호출하면 부모 생성자도 자동으로 호출된다
+ 자식 생성자의 첫 행에 부모 생성자를 호출하는 코드가 없다면 자동으로 super() 메서드가 생성된다
+ 맨 첫줄, 인자 맞춰주기