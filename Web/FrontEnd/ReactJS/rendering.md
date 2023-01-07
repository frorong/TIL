# 조건부 렌더링

원하는 동작을 캡슐화하는 컴포넌트를 만들면 컴포넌트중 몇 개만을 렌더링할 수 있다

-   ### 논리 && 연산자 if의 인라인 표현

```js
function Component1(props) {
    let isTrue = true;
    return (
        <div>
            <h1>hello world!</h1>
            {isTrue && <h2>이것은 사실이다</h2>}
        </div>
    );
}
```

is True가 true면 이것은 사실이다  
js에서

```js
true && expression;
```

은 항상 expression이고

```js
false && expression;
```

은 항상 false이다

-   ### 삼항연산자

```js
function Component2(props) {
    let isTrue = true;
    return (
        <div>
            <h1>hello world!</h1>
            {isTrue ? <h2>이것은 사실이다</h2> : <h2>이것은 거짓이다</h2>}
        </div>
    );
}
```
