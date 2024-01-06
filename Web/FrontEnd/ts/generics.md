# Generics

-   한 함수에 다른 타입을 보내 쓰고 싶을 때 계속 유니온 타입으로 지정한다면 불편하다  
    이런 상황을 위해 Generics이 있다

-   Generics는 꺽쇄 안에 T를 넣어 사용한다(T를 넣는게 일반적이다)
-   ```ts
    function func<T>(arr: T[]): number {
        return arr.length;
    }
    ```
-   함수를 사용할 때에도 마찬가지로 꺽쇄 안에 T를 넣어준다
-   ```ts
    func<number>(arr1);
    ```
-   interface에서도 사용이 가능하다
-   ```ts
    interface Intf<T> {
        like: T;
    }
    ```
