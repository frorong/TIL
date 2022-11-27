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
