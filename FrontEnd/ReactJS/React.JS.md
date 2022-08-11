# React JS

#### 어플리케이션이 인터랙티브하게 만들어주는 라이브러리

## React-dom

#### 라이브러리 또는 패키지
+ React Element를 HTML body에 두게 해준다   

### React JS로 html에 element를 추가하는 어려운 방법
```html
<script src="https://unpkg.com/react@17/umd/react.development.js" crossorigin></script>
<script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js" crossorigin></script>
<script>
    const root = document.getElementById("root");
    const span = React.createElement("span", {id:"Span"}, "Span");
    ReactDOM.render(span, root);
</script>
```
1. 먼저 React와 ReactDOM을 import한다
2. body에는 root라는 id를 가진 div 하나만 있다
3. React.createElement의 첫 번째 인자로는 html태그가 들어가고\
    두 번째 인자로는 property를 줄 수 있다\
    세 번째 인자로는 안에 들어갈 내용을 준다
4. ReactDOM.render로 root 안에 span을 추가해준다
5. 이 방법은 쓰지 않는다

중요한 것은 React JS로 유저에게 보여질 내용을 컨트롤 할 수 있다는 것

## JSX
#### JS를 확장한 문법이다   
+ HTML과 흡사한 문법으로 React요소를 만들 수 있다
```js
const span = React.createElement("span", {id:"Span"}, "Span");
const span = <span id="Span">Span</span>;
```
JSX문법을 사용하면 굉장히 간단하다

#### 함수로 만들기
```js
const SPAN = () => (
    <span id="Span">
       Span
    </span>
)
//아래와 같다
function SPAN() {
    return(
    <span id="Span">
       Span
    </span>
    );
}
//이렇게 만들어서
<SPAN />
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
)
```
#### ReactJS는 이전에 렌더링된 컴포넌트와 렌더링될 컴포넌트를 비교해서 다른 부분만 업데이트한다

### 배열
```js
const x = [1,2,3];
const [a, b, c] = x;
a == 1, b == 2; c == 3;
```

### class, for
```js
return(
    <label for="ID"></label>
    <input id="ID" class="CLASS"/>
)
```
JSX에서는 위와 같이 사용할 수 없다\
이미 js에서 선점된 단어이기 때문이다\
때문에 아래와 같이 사용해야 한다
```js
return(
    <label htmlFor="ID"></label>
    <input id="ID" className="CLASS"/>
)
```

#### disabled
```js
return(
    <input
        disabled={true};
    />
)
```
위와 같은 방법으로 사용이 가능하다\
true, flase값을 가진 변수를 활용할 수 있다

### JS사용
```js
return(
    <p></p>
    {
        const a = 0;
    }
)
```
{중괄호} 안에서는 JS 사용이 가능하다

### 동일한 스타일이지만 텍스트는 다르게
1. 원하는 스타일의 함수형 컴포넌트를 만든다
2. 함수형 컴포넌트를 호출할 때 아래와 같이 호출한다
    ```js
    return(
        <div>
            <Component1 text1:"텍스트"/>
        </div>
    )
    ```
    Component1 함수를 불러서 text1이라는 인자를 보내는 것과 같다\
    Component1 함수에서 전달받는 인자의 이름은 보통 props라고 한다
3. Component1 함수 내에서 아래와 같이 적용하면 된다
    ```js
    function Component1(props){
        return(
            <div>
                <p>{props.text1}</p>
            </div>
        )
    }
    ```
4. 더 편하게
    ```js
    function Component1({text1}){
        return(
            <div>
                <p>{text1}</p>
            </div>
        )
    }
    ```
    props는 object이기 때문에 중괄호를 이용하여 text1을 받을 수 있다

### 커스텀 component
```js
const App = () => {
    return(
        <div>
            <Component1 onClick={onClick} />
        </div>
    )
}
```
onClick과 같은 이벤트 리스너를 커스텀 component에 넣는다면 그 것은 prop일 뿐이다\
이벤트 리스너를 넣으려면 상위 div에 넣던가 해야한다

이런 경우는 style도 마찬가지다

### React Memo
부모가 어떤 state라도 변경이 있으면 자식들은 모두 re render될 것이다\
component들이 다시 그려질 때 우리가 컨트롤 할 수 있다
```js
const MemorizedComponent = React.memo(Conponent1);
const App = () => {
    return(
        <div>
            <MemorizedComponent onClick={onClick} />
        </div>
    )
}
```
