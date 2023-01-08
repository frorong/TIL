# 합성 (Composition) vs 상속 (Inheritance)

React는 강력한 합성 모델을 가지고 있다  
상속 대신 합성을 사용하여 컴포넌트간의 코드를 재사용 하는 것이 좋다

### 컴포넌트에서 다른 컴포넌트를 담기

```js
function FancyBorder(props) {
    return (
        <div className={'FancyBorder FancyBorder-' + props.color}>
            {props.children}
        </div>
    );
}
```

```js
function WelcomeDialog() {
    return (
        <FancyBorder color="blue">
            <h1 className="Dialog-title">Welcome</h1>
            <p className="Dialog-message">
                Thank you for visiting our spacecraft!
            </p>
        </FancyBorder>
    );
}
```

위와 같은 방식으로 jsx를 중첩하여 임의의 자식을 전달할 수 있다
