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

### emit

```js
socket.emit('event', {});
```

```js
socket.on('event', (msg) => {});
```

socketIO의 emit의 1번째 argument는 event 이름이 들어가고  
2번째 argument로 payload를 보내는데 object도 전송이 가능하다  
마지막 argument로 서버에서 호출하는 function이 들어간다  
서버는 백엔드에서 function을 호출하지만 function은 프론트에서 실행된다!!  
백엔드에서 실행시키면 보안 문제가 발생할 수 있기 때문이다

## Room

```js
socket.join(roomName);
```

방에 들어가게 해준다

```js
socket.room;
```

어떤 방에 있는지 알려준다

```js
socket.leave(roomName);
```

방을 나간다

```js
socket.to(room).emit('message');
```

방 전체에 메세지를 보낸다
