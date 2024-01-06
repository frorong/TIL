# React
### React 프로젝트 구조 생성
    npm init react-app ProjectName
    ProjectName이라는 이름을 가진 폴더가 만들어진다

    node_modules 폴더 안에는 자바스크립트 모듈들이 있다
    public 폴더 안에는 index.html파일과 정적 파일들이 있다
    src 폴더에는 우리가 리액트 코드들을 개발해 나간다
    package.json에는 전체 프로젝트의 대한 정보를 담고 있다

    cd ProjectName을 해서 ProjectName으로 이동 후 npm start를 한다
    로컬 호스트 3000번에서 정상적으로 실행됨을 확인할 수 있다
### 함수형 Component
+ ex
     ```js
    import React from "react";

    function Home(){
        return <h1>Home 화면 입니다.</h1>;
    }

    export default Home;
    ```
+ 화살표 함수 형식
    ```js
    const Home = () => {
    return <h1>Home 화면 입니다.</h1>;
    }
    ```
### Class형 Component
+ ex
    ```js
    import React, {Component} from "react";
    class Home extends Component{
        render() {
            return <h1>Home 화면 입니다.</h1>
        }
    }

    export default Home;
    ```
    ##### 최근에는 함수형 Component로 많이 개발하는 추세라고 한다


### 가져오기
+ ex
    ```js
    import Home from "./pages/Home"
    ```
    이렇게 하면 pages폴더 안에 있는 Home을 가져올 수 있다
    가져온 후에는 html태그에서 쓸 수 있다\
    ex
    ```js
    <Home />
    ```

## 태그
+ Link 태그
    ``` js
    import {Routes, Route, Link} from "react-router-dom";
    ```
    ```js
    <Link to="/">Home</Link>
    ```
    a태그와 동일 기능
    ```js
    <Routes>
        <Route path="/" element={<Home/>}/>
    </Routes>
    ```
+ button 태그
    ```js
    const [num, setNumber] = useState(0); //동적값을 처리하기 위해 사용 Seter함수(setNumber)를 통해서 관리를 해야만 한다
    const increase = () => {
        setNumber(num+1);
    }
    return(
        <button onClick={increase}>+1</button>
        <p>{num}</p> //중괄호 안에 변수를 넣는 방법은 혁신적이다
    )
    ```
    버튼이 onClick되면 increase를 실행시킨다

### 여러 input 입력받기
```js
const [inputs, setInputs] = useState({
        name:"",
        emlai:"",
        tel:""
    });
```
배열 형식으로 선언해서 각 input value에 값을 지정해준다