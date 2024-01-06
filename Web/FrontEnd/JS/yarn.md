# yarn

-   yarn은 프로젝트의 의존성을 관리하는 package manager이라고 한다

-   npm은 저장소의 보안이 취약하고 패키지가 많아 빌드 성능이 좋지 않다  
    반면에 yarn은 설치 시간이 단축되고 설치된 패키지의 무결성을 확인하여 좋다

*   yarn lock
    -   같은 package.json에 의존하는 서로 다른 버전의 패키지 의존성을 가지는것을 방지
*   아래 명령어를 사용하여 패키지를 다운받을 수 있다
    -   `yarn add <package...>`
*   아래 명령어를 사용하여 패키지를 시스템 전역에 다운받을 수 있다
    -   `yarn  global <add/bin/list/remove/upgrade>`
*   아래 명령어를 사용하여 프로젝트를 설치할 수 있다
    -   `yarn create <starter-kit-package>`
*   아래 명령어를 사용하여 package.json을 생성할 수 있다
    -   `yarn init`
*   아래 명령어를 사용하여 의존성 모듈을 다운받을 수 있다
    -   `yarn install`
