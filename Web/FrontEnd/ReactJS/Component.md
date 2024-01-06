# component

## JSX

#### JS를 확장한 문법이다

- HTML과 흡사한 문법으로 React요소를 만들 수 있다

```js
const span = React.createElement("span", { id: "Span" }, "Span");
const span = <span id="Span">Span</span>;
```

JSX문법을 사용하면 굉장히 간단하다

#### 함수로 만들기

```js
const SPAN = () => <span id="Span">Span</span>;
//아래와 같다
function SPAN() {
  return <span id="Span">Span</span>;
}
//이렇게 만들어서
<SPAN />;
//이렇게 렌더링한다
//중요한 것은 컴포넌트의 첫 글자는 반드시 대문자여야 한다는 것이다
```

이런 것을 함수형 컴포넌트라고 한다

##### 변수를 아래와 같이 넣을 수 있다

```js
let value = 0;
const Container = () => (
  <div>
    <h3>value : {value}</h3>
  </div>
);
```

#### ReactJS는 이전에 렌더링된 컴포넌트와 렌더링될 컴포넌트를 비교해서 다른 부분만 업데이트한다

### component import하기

새로운 js파일을 만들어서 component를 만들고 아래에 이렇게 입력해준다

```js
export default Name;
```

App.js에 import 해준다

```js
import Name from "./Name";
```

이 상태에서 npm start를 입력하면 경고가 뜬다\
Name은 정의되었지만 사용되지 않았다고\
이건 create-react-app이 주는 도움이라고 한다

# 합성 (Composition) vs 상속 (Inheritance)

React는 강력한 합성 모델을 가지고 있다  
상속 대신 합성을 사용하여 컴포넌트간의 코드를 재사용 하는 것이 좋다

### 컴포넌트에서 다른 컴포넌트를 담기

```js
function FancyBorder(props) {
  return (
    <div className={"FancyBorder FancyBorder-" + props.color}>
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
      <p className="Dialog-message">Thank you for visiting our spacecraft!</p>
    </FancyBorder>
  );
}
```

위와 같은 방식으로 jsx를 중첩하여 임의의 자식을 전달할 수 있다
