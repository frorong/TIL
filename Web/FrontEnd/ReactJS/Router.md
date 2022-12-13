# 라우터

#### 페이지를 전환

### 설치

```cmd
npm install react-router-dom
```

```cmd
yarn add react-router-dom
```

### react-router-dom

-   Hash Router
-   Browser Router

홈으로 가기

```js
function App() {
    return (
        <Router>
            <Switch>
                <Route path="/">
                    <Home />
                </Route>
            </Switch>
        </Router>
    );
}
```

유저가 / 이 경로에 있으면 홈 화면을 렌더링 해준다

`import { Link } from "react-router-dom";`

Link를 import해서 페이지를 전환시킬 수 있다

```jsx
<Link to="경로"></Link>
```

### URL 파라미터

경로에 콜론을 사용하여 설정할 수 있다  
`import { useParams } from 'react-router-dom';`

```js
const App = () => {
    return (
        <BrowserRouter>
            <Routes>
                <Route path="/경로/:경로Id" element={<Component />}></Route>
            </Routes>
        </BrowserRouter>
    );
};
```

```js
import React from 'react';
import { useParams } from 'react-router-dom';

const Component = () => {
    const { 경로Id } = useParams();
    return (
        <>
            <h3>{경로Id}페이지 입니다</h3>
        </>
    );
};

export default Component;
```

### 쿼리스트링

-   ### useLocation
    -   hash : 주소의 #뒤의 값
    *   pathname : 현재 주소값
    *   search : ?를 포함한 쿼리스트링
    *   state : 이동시 넣을 수 있는 상태값
    *   key : location 객체의 고유 값

```js
import React from 'react';
import { useParams } from 'react-router-dom';
import { useLocation } from 'react-router-dom';

const Component = () => {
    const location = useLocation();
    return (
        <div>
            <ul>
                <li>hash : {location.hash}</li>
                <li>pathname : {location.pathname}</li>
                <li>search : {location.search}</li>
                <li>state : {location.state}</li>
                <li>key : {location.key}</li>
            </ul>
        </div>
    );
};

export default Component;
```

## history

-   history로 페이지가 이동된 path를 볼 수 있다  
    history는 prop으로 받고 이걸 이용해서 페이지를 이동할 수 있다
