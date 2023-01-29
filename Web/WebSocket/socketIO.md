# Socket IO

쉽게 실시간 기능을 만들어주는 프레임워크

실시간, 양방향, 이벤트 타입의 통신을 가능하게 한다

웹 소켓을 쓸 수 없다라도 Socket IO는 계속 작동한다  
웹 소켓을 사용할 수 없을 경우 http long polling을 사용한다

많은 도박 사이트들이 Socket IO를 사용하는데 이 것은 그만큼 신뢰할 수 있다는 것이다

### 서버 생성

```js
const server = http.createServer(app); // 서버 만들기(http 서버)
const io = SocketIO(server);
```

http 서버를 먼저 만들고 socketIO 서버를 만든다

프론트

```js
const socket = io();
```

### 연결

```js
wsServer.on('connection', (socket) => {});
```
