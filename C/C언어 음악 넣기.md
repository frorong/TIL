## C언어 음악 넣기
    1. 헤더파일 받기
        
        #include<MMSystem.h>
        #pragma comment(lib,"Winmm.lib")
        
    2. wav확장자 파일을 다운받아 프로젝트 폴더에 넣기
    3. 함수 실행하기
        
         PlaySound(TEXT("파일 이름"), NULL, SND_ASYNC);