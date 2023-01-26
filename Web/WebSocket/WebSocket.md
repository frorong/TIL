# WebSocket

WebSocket은 프로토콜이다  
http와는 전혀 다르다

브라우저가 서버로 webSocket Request를 보내면 서버가 받거나 거절하거나 선택한다  
이런 악수가 한 번 성립되면 연결은 성립되는 것이다  
브라우저와 서버가 계속 커뮤니케이션 할 수 있다  
서버는 request를 기다리지 않아도 된다

브라우저에는 내장된 web socket API가 있다

# ws

클라이언트와 서버 사이의 웹 소켓의 기반이 되는 패키지

## event

브라우저에서 click과 같은 이벤트가 존재하듯이 WebSocket에도 이벤트가 존재한다

```js
wss.on('connection', handleConnection);
```

이런식으로 이벤트를 들을 수 있다

## socket

socket은 연결된 브라우저와의 연락 라인이다  
socket을 이용하면 메세지 주고받기를 할 수 있다

```js
const socket = new WebSocket(`ws://${window.location.host}`);
```

app에서 가지고있는 socket은 서버로의 연결을 뜻한다

```js
const handleConnection = (socket) => {
    console.log(socket);
};
```

server에서 가지고있는 socket은 연결된 브라우저를 뜻한다
