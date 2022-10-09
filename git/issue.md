### 오류
+ ```failed to push some refs to 'https://github.com/jytrack64/TIL.git'```
    + 원인 : 로컬 저장소와 원격 저장소의 상태가 달라서\
    + 해결법 : pull 후 다시 push를 한다
+ ```warning: LF will be replaced by CRLF in sass/scss.css. The file will have its original line endings in your working directory```
    + 원인 : 줄 바꿈에 대한 문자열이 달라서 git에서 경고 메세지를 띄움
    + 해결법 : git config --global core.autocrlf true를 친다​
+ ```error: Your local changes to the following files would be overwritten by checkout:```
    + 해결법 : 
    1. 파일의 변동사항을 저장한다 ```git stash```
    2. 작업을 한다
    3. 변동사항을 적용시킨다 ```git stash pop```