# JSX

-   jsx는 js를 확장한 문법이다. html과 js를 섞은 것처럼 생겼다

-   JSX를 쓰면 js 안에서 UI 작업을 할 때 시각적으로 도움이 된다고 한다

## 사용

-   JSX의 중괄호 안에는 모든 js 표현식 사용이 가능하다
-   ```jsx
    const element = <div></div>;
    ```
    -   처럼 사용 가능하다

## 특징?

-   JSX로 엘리먼트의 속성과 자식도 정의가 가능하다
-   주입 공격을 방지하여 사용자 입력을 안전하게 사용할 수 있다
-   React.createElement()로 호출되어져서 객체를 표현하게 된다
