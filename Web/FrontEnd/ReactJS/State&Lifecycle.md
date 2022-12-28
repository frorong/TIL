# State and Lifecycle

state는 비공개이며 component에 의해 완전히 제어된다

많은 component가 있는 어플리케이션에서는 component가 삭제될 때 해당 component가 사용 중이던 리소스를 확보하는 것이 중요하다

컴포넌트 클래스에서 특별한 메서드를 선언하여 component가 마운트 되거나 언마운트 될 때 일부 코드를 작동시킬 수 있다

```js
componentDidMount();
```

메서드는 컴포넌트 출력물이 DOM에 렌더링 된 후에 실행된다

## State를 올바르게 사용하기

-   직접 state를 수정할 수 없다
-   state 업데이트는 비동기적일 수도 있다
    -   state가 비동기적으로 업데이트 될 수 있기 때문에 다음 state를 계산할 때 해당 값에 의존적이면 안된다
-   state 업데이트는 병합된다
    -   setState를 호출하면 react는 제공한 객체를 현재 state로 병합한다
-   데이터는 아래로 흐른다
    -   컴포넌트는 자신의 state를 자식 component에 props로 전달할 수 있다
