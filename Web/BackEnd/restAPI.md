# REST

자원을 이름으로 구분하여 해당 자원의 상태를 주고받는 모든 것

- HTTP URI를 통해 자원을 명시
- HTTP Method를 통해 해당 자원에 대한 CRUD Operation을 적용

#### CRUD

- Create
- Read
- Update
- Delete

### 구성 요소

- 자원 Resource : HTTP URI
- 자원에 대한 행위 Verb : HTTP Method
- 자원에 대한 행위의 내용 Representations : HTTP Messege Pay Load

### 특징

- Server-Client
- StateLess
- Cacheable
- Layered System
- Uniform Interface

# RESTful

REST의 원리를 따르는 시스템을 의미

REST API의 설계 규칙을 올바르게 지킨 시스템을 RESTful하다 말할 수 있다

### 개발 원칙

- url만으로 내가 제어하고자 하는 것의 종류를 알 수 있어야 한다
- 행위가 명시되어야 한다
- 데이터만 보고 어떤 것인지 알 수 있어야 한다
- 추가적인 정보에 대한 링크를 제공할 수 있어야 한다

### 단점

- 4가지 메소드만 제공한다
- http에 의존적이다
- 아키텍쳐링 방법만 담고 있다
- 상호작용을 하는 개발에는 적당하지 않다

# REST API

REST의 원리를 따르는 API

### REST API 설계 예시

- URI는 동사보다는 명사를 사용하고 대문자보다는 소문자를 사용한다
- 마지막에 `/`를 포함하지 않는다
- 언더바 대신 `-`을 사용한다
- 파일 확장자는 URI에 포함하지 않는다
- 행위를 포함하지 않는다
