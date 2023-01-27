# Message 보내기

아래와 같이 하여 socket으로 data를 보낼 수 있다

```js
socket.send('hello!!');
```

# Message 받기

브라우저에서 socket에 이벤트 리스너를 달아놓으면 이벤트를 받을 수 있다

```js
const socket = new WebSocket(`ws://${window.location.host}`); // 프론트에서 해줘야하는 연결
socket.addEventListener('open');
```

서버에선ㄴ 아래와 같다

쓸 수 있는 이벤트

-   open : 서버와 연결시 발생
-   message : 서버가 메세지 전송시 발생
-   error : 에러 발생시 발생
-   close : 서버와 연결이 끊길시 발생
