# Components와 Props

Component를 통해 UI를 재사용 가능한 개별적인 조각으로 나눌 수 있다

component를 정의하는 가장 간단한 방법은 js 함수를 작성하는 것이다

```js
const Component1 = (props) => {
    return <div>{props.data}</div>;
};
```

이러한 component는 js 함수이기 때문에 함수형 component라고 한다

es6를 통해서도 component를 정의할 수 있다

```js
class Component1 extends React.Component {
    render() {
        return <div>{this.props.data}</div>;
    }
}
```

react의 관점에서 볼 때 위 두 component는 동일하다

react element는 사용자 정의 component로도 나타낼 수 있다

```js
const element = <Component1 name="CPNT1" />;
```

## Component 합성

component는 자신의 출력에 다른 component를 참조할 수 있다

Com1을 여러번 렌더링하는 App을 만들 수 있다

```js
const Com1 = () => {
    return <h1>hi</h1>;
};

const App = () => {
    <div>
        <Com1 />
        <Com1 />
        <Com1 />
    </div>;
};
```

## Component 추출

component를 여러 개의 작은 component로 나누는 것을 두려워하지 마라고 한다

## props는 읽기 전용이다

component의 자체 props를 수정하면 안 된다  
모든 react component는 자신의 props를 다룰 때 반드시 순수 함수처럼 작동해야 한다고 한다
