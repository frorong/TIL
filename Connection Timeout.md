# Connection Timeout

```
일정 시간 내에 동작이 수행되지 않아 진행이 중단되는 것을 Timeout 이라고 한다
Connection Timeout은 클라이언트와 서버가 Connection을 하려고
하지만 장애 상황으로 인해 Connection도 되지 않은 것이다
Connection 과정에서 정확한 전송을 위해 사전에 세션을 수립하는 것을
3-way HandShake 라고 한다
(클라이언트에서 서버에 SYN 패킷을 보내고 SYN/ACK 응답을 기다린다
서버는 SYN 요청을 받은 후 ACK + SYN 패킷을 보내고 ACK로 응답을 기다린다
클라이언트는 서버에게 ACK를 보낸다)
Connection Timeout === 3-way HandShake가 정상적으로 수행되기까지의 시간
```
