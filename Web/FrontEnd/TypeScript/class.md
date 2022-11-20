# class

-   basic

```ts
class Car {
    color: string;
    constructor(color: string) {
        this.color = color;
    }
}
const newCar = new Car('black');
```

-   접근제한자

    -   public
        -   자식클래스, 클래스 인스턴스 모두 접근 가능하다
    -   private
        -   동일 클래스 내부에서만 사용 가능하다
        -   #으로 선언할 수 있다
    -   protected
        -   자식 클래스 내부에서 참조가 가능하다
    -   readonly
        -   readonly가 붙으면 읽기 전용이 된다
    -   static

-   추상클래스
    -   추상클래스는 클래스명 앞에 abstract키워드를 붙인다
    -   추상클래스의 추상 메소드는 반드시 상속받을시 언급이 필요하다
