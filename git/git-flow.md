# Git-Flow
+ 깃으로 소스코드를 관리하는 방법론!
+ Git-Flow의 장점
    + 완료된 작업에서 새로운 분기를 만들어 병렬로 쉽게 개발할 수 있다  
    + 다수의 개발자가 동일한 기능에 대해 공동 작업을 쉽게 할 수 있다  
    + 긴급하게 변경을 할 수 있다 동시에 실수로 병합할 위험이 없다  
+ Git-Flow의 단점
    + 복잡하다
    + 병합시 충돌의 가능성이 높아진다
+ Git-Flow의 branch 구성
    + master : 배포 가능한 브랜치이다
    + develop : 개발을 하는 브랜치이다
    + feature : 필요한 기능을 개발하는 브랜치이다
    + release : QA를 통해 버그를 찾아내는 브랜치이다
    + hotfixes : 버그를 긴급하게 수정하기 위한 브랜치이다\
    (master, develop은 상시 유지되는 브랜치이고 나머지는 필요시 쓰는 브랜치이다)
+ 순서
    1. 처음엔 master, develop branch만 생성된다
    2. develop branch에서 개발을 시작한다
    3. 개발에 필요한 기능이 생기면 feature branch를 만들어 작업한다
    4. 기능 개발, 검토 후 develop branch에 병합한다
    5. 모든 기능이 개발되었다면 release branch를 생성해서 QA를 진행하며 버그를 고친다 
    6. QA가 끝났다면 release branch를 master, develop branch에 병합한다
    7. master branch에 태그 생성 후 배포한다
    8. 배포 후에 버그 발생시 hofixes branch를 생성해 버그를 수정 후 병합한다
+ 버전 태그
    + x.x.x의 형태를 가진다
    + 첫 번째 숫자는 보통 1로 시작하고 소프트웨어에 큰 변화가 생겼을 때 버전 업을 한다
    + 두 번째 숫자는 0으로 시작해서 기능의 변화가 생겼을 때 버전 업을 한다
    + 세 번째 숫자는 0으로 시작해서 버그나 보안의 변화가 생겼을 때 버전 업을 한다