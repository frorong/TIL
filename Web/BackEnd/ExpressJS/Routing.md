# 라우팅

애플리케이션 엔드 포인트의 정의와 URI가 클라이언트 요청에 응답하는 방식

매우 기본적인 라우터의 예

```js
var express = require('express');
var app = express();

// respond with "hello world" when a GET request is made to the homepage
app.get('/', function (req, res) {
    res.send('hello world');
});
```

## 라우트 메소드

라우트 메소드는 http메소드 중 하나로부터 파생된다

앱의 루트에 대한 get밑 post 메소드에 대해 정의된 라우트의 예

```js
// GET method route
app.get('/', function (req, res) {
    res.send('GET request to the homepage');
});

// POST method route
app.post('/', function (req, res) {
    res.send('POST request to the homepage');
});
```

## 라우트 경로

라우트 경로는 요청 메소드와의 조합을 통해 요청이 이루어질 수 있는 엔드포인트를 정의한다

### 문자열을 기반으로 하는 라우트 경로의 예

-   요청을 루트 라우트에 일치

```js
app.get('/', function (req, res) {
    res.send('root');
});
```

-   요청을 about에 일치

```js
app.get('/about', function (req, res) {
    res.send('about');
});
```

## 라우트 핸들러

하나의 콜백 함수는 하나의 라우터를 처리할 수 있다

```js
app.get('/example/a', function (req, res) {
    res.send('Hello from A!');
});
```

### app.route

app.route를 이용하여 라우트 경로에 대하여 체인 가능한 라우트 핸들러 작성이 가능하다

```js
app.route('/book')
    .get(function (req, res) {
        res.send('Get a random book');
    })
    .post(function (req, res) {
        res.send('Add a book');
    })
    .put(function (req, res) {
        res.send('Update the book');
    });
```

### express.router

express.Router클래스를 사용하면 모듈식 마운팅 가능한 핸들러 작성이 가능하다

```js
var express = require('express');
var router = express.Router();

// middleware that is specific to this router
router.use(function timeLog(req, res, next) {
    console.log('Time: ', Date.now());
    next();
});
// define the home page route
router.get('/', function (req, res) {
    res.send('Birds home page');
});
// define the about route
router.get('/about', function (req, res) {
    res.send('About birds');
});

module.exports = router;
```

```js
var birds = require('./birds');
...
app.use('/birds', birds);
```
