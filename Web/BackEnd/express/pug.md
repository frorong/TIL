# Pug

Pug은 view엔진이다  
express에 설치하기도 쉽고 직접 템플릿을 작성하는 것보다 빠른 효율을 얻을 수 있다

### 설치

`npm install pug`

### app.js

app.js에 아래 코드를 추가 => express view-engine의 설정을 바꿔준다

```js
app.set('view engine', 'pug');
```

### express views 설정

프로젝트 폴더 안에 /views 폴더를 만들어준다

### home.pug

views 폴더 안에 home.pug파일을 생성한다

## Pug 문법

html

```html
<p>hi</p>
```

pug

```pug
p hi
```

pug 파일 내에서 HTML을 사용해도 정상적으로 받아들인다

id는 아래와 같이 작성한다

```
tag#idName
```

클래스는 아래와 같이 작성한다

```
tag.className
```

attribute는 아래와 같이 작성한다

```
form(action="#", method="post")
```

아래와 같이 작성하면 {}안에 js 코드 작성이 가능하다

```
#{}
```

### controller

-   viewController
    -   res.render를 이용해서 pug파일을 보여준다
    -   ```js
        export const home = (req, res) => res.render('home');
        ```
