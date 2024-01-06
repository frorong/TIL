# Http&Https

### Http

- http란?
  - html문서와 같은 리소스들을 가져오게 도와주는 프로토콜
  - Plain text, JSON, XML등 다양한 문서도 전송 가능하다
- HyperTexT Protocol의 약자
- 문서를 전송하기 위한 약속이다

### Https

- HyperText Transfer Protocol over Secure Socket Layer의 약자
- Http의 보안이 강화된 버전이다

이들의 url은 http:// https://로 차이가 난다  
https는 소켓 통신에서 일반 텍스트를 이용하지만 프로토콜을 통해 데이터를 암호화한다

- 클라이언트
  - 서버에게 요청을 보내는 사용자이다
- 서버
  - 클러이언트의 요청에 대한 응답을 제공한다

클라이언트가 서비스를 서버에 요청하면 해당 요청에 대한 결과를 응답한다

- http 요청 메소드
  - GET
    - 특정 리소스를 받기 위한 요청
  - POST
    - 리소스 생성, 컨트롤러 실행
  - PUT
    - 리소스 업데이트
  - PATCH
    - 리소스 부분 업데이트
  - DELETE
    - 특정 리소스 제거
  - HEAD
    - 리소스에 대한 헤더만 검색
  - OPCTIONS
    - 수행 가능 동작 검색
