# CSS

#### 방법 1

css파일을 만들고 js에서 import를 해준다

```js
import './style.css';
```

#### 방법 2

style prop을 사용한다

```js
function component() {
    return (
        <button
            style={{
                backgroundColor: 'orange',
            }}
        ></button>
    );
}
```

create-react-app 덕분에 자동완성이 된다

#### 방법 3

##### CSS modules

css 파일을 만들고 (파일 이름: Name.module.css) import한다

```css
.Class {
    color: red;
    background-color: royalblue;
}
```

```js
import styles from './Name.module.css';

function Button({ text }) {
    return <button className={styles.Class}>{text}</button>;
}
```

create-react-app이 css코드를 js 오브젝트로 변환시켜준다

## Styled Component

-   설치

```
 npm i styled-components
```

-   import

```
import styled from "styled-components";
```

-   인자로 컴포넌트를 넘길 수 있다
-   export와 inport를 사용한다
-   컴포넌트별로 폴더를 만들어 관리하며 style파일은 위에 styled-component를 import 해야한다
-   style파일에서는 백틱을 사용하여 css 문법을 적용할 수 있다
-   작성한 변수는 export하여 jsx파일에서 사용 가능하다
