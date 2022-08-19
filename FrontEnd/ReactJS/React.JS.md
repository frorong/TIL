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

### prop types
prop을 보낼 때 타입을 잘못 보내는 실수를 할 수 있다\
PropType은 어떤 타입의 prop을 받고 있는지 체크해준다
```html
<script src="https://unpkg.com/prop-types@15.6/prop-types.js"></script>
```
ex
```js
Component1.propTypes = {
    text: PropTypes.string,
    fontSize: PropTypes.number,
}
```
위와 같이 작성할 수 있다\
그럼 경고 문구를 볼 수 있다\
Warning: Failed prop type: Invalid prop `fontSize` of type `string` supplied to   `BTN`, expected `number`.  
    at BTN (<anonymous>:18:21)  
    at App (<anonymous>:42:31)  
printWarning @ react.development.js:245  
  
(fontsize는 string이었지만 number를 원한다)

array, func, bool, number, object, string, symbol, node, element, 등 다양하게 적용 가능하다  
  
  확실하게 하고싶다면 뒤에 isRequired를 붙여주면 된다\
  ex
```js
Component1.propTypes = {
    text: PropTypes.string.isRequired,
    fontSize: PropTypes.number,
}
```
이 경우에는 text는 필수고 number는 선택이다

#### 만약 prop이 존재하지 않는다면 default값을 줄 수 있다
ex
```js
function Component({text, number = 15}){}
```
number의 기본값은 15가 된다.

### Create React App

아래와 같은 코드를 콘솔에 입력해준다
```cmd
npx create-react-app NameForReactApp(만들 폴더의 이름)
```

package.json을 확인한다\
package.json에는 우리가 쓸 수 있는 script들이 있다\
이것들은 create-react-app 팀에 의해서 만들어진 것이다   

```cmd
npm run
```
을 입력해보자\
자동적으로 브라우저가 열리게된다

create react app의 장점중에는 auto-reload가 된다는 것이 있는데\
이것은 익스텐션을 깔면 된다

#### component import하기
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

#### prop types checking

```cmd
npm i prop-types
```
prop-types를 install해준다\
install이 되었다면 proptypes를 inport한다
```js
import PropTypes form "prop-types";
```

### CSS

#### 방법 1
css파일을 만들고 js에서 import를 해준다
```js
import "./style.css";
```

#### 방법 2
style prop을 사용한다
```js
function component(){
    return(
        <button 
        style={{
                backgroundColor:"orange",
        }}>
        </button>
    )
}
```
create-react-app 덕분에 자동완성이 된다

#### 방법 3
##### CSS modules
css 파일을 만들고 (파일 이름: Name.module.css) import한다
```css
.Class{
    color: red;
    background-color: royalblue;
}
```
```js
import styles from "./Name.module.css";

function Button({text}){
    return(
        <button className={styles.Class}>{text}</button>
    )
}
```
create-react-app이 css코드를 js 오브젝트로 변환시켜준다


### useEffect

state를 change할 때 마다 똑같이 function이 다시 실행된다\
=> 가끔 특정 코드의 실행을 제한하고 싶다

useEffect는 2개의 인자를 가지는 함수이다  
우리 코드가 딱 한번만 실행될 수 있도록 보호해준다
+ 첫 번째 인자는 우리가 딱 한번만 실행하고 싶은 코드이다  
+ 두 번째 인자는 변화를 지켜볼 dependency인데 변화가 생기면 첫 번째 인자인 코드가 실행된다  
두 번째 인자를 [ ]로 비워둔다면 처음 한 번만 실행된다
```js
const [value, setValue] = useState(" ");
useEffect(() => {
    console.log("실행");
}, [value]);
```
위와 같은 경우에는 value가 update될 때 마다 "실행" 이라고 찍힌다

```js
const [value, setValue] = useState(" ");
const [VALUE, SETvALUE] = useState(" ");
useEffect(() => {
    console.log("value와 VALUE가 바뀔 때 실행");
}, [value, VALUE]);
```
위와 같은 경우처럼 두 가지를 동시에 지켜볼 수도 있다

#### Cleanup function
react.js는 component가 destory될 때도 코드를 실행시킬 수 있다
```js
function Component () {
    useEffect(() => {
        console.log("hi");
        return()=>console.log("bye");
    }, [])
}
```
Component가 rendering될 때 "hi"가 찍히고 destory될 때 "bye"가 찍힌다\
화살표 함수는 간편하다

## 라우터   
#### 페이지를 전환
### 설치
```cmd
npm install react-router-dom
```
### react-router-dom
+ Hash Router
+ Browser Router
    
홈으로 가기
```js
function App() {
    return <Router>
        <Switch>
            <Route path="/">
                <Home/>
            </Route>
        </Switch>
    </Router>
}
```
유저가 / 이 경로에 있으면 홈 화면을 렌더링 해준다

import { Link } from "react-router-dom";

Link를 import해서 페이지를 전환시킬 수 있다