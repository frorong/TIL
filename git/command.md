## git
### command
+ init 
    + git init : 새로운 git 저장소를 생성한다
+ file
    + git add . : 모든 파일을 추가한다\
      git add 파일 이름 : 선택한 파일을 추가한다\
      git status : 어떤 파일이 있는지 확인한다\
      git rm 파일 이름 : 파일을 삭제한다\
      git restore 파일 이름 : 파일을 복구해준다\
      git blame : 파일의 수정 내역을 알려준다\
+ commit
    + git commit "메세지" : 새로운 커밋을 만든다\
      git log : 커밋 내역을 확인해준다\
      git show : 커밋의 상세 정보를 보여준다
+ branch
    + git branch : 어떤 브랜치가 있는지 알려준다\
      git branch 이름 : 새로운 브랜치를 만든다\
      git checkout 이름 : 브랜치로 이동을 한다\_
      git push origin 이름 : 브랜치를 서버에 전송한다\
      git branch -m 이름 : 브랜치 이름을 변경한다\
      git branch -d 이름 : 브랜치를 삭제한다\
      git checkout -b 이름 : 브랜치를 만들고 이동을 해준다
+ remote
    + git remote add origin 주소 : 원격 저장소와 연걸을 해준다\
      git remote remove origin : 원격저장소를 삭제한다\
      git remote -v : 어디에 연결 되어있는지 알려준다
+ clone
    + git clone URL : 복제를 한다
+ push, pull
    + git push origin main : 메인에 변경사항을 업로드한다\
      git pull : 원격 저장소의 데이터를 가져와 병합합다
+ local
     + git diff : 수정 파일과 원래 버전의 차이를 알려준다\
       git fetch origin : 현재 상태를 다운로드 해준다
### 명령어 add
+ add
    + git add <파일 경로>
      git add . : 현재 디렉토리 내의 모든 변경 내용 선택
      git add -A : 모든 디렉토리 내의 모든 변경 내용 선택
      git add -p : 각 변경 사항을 선택