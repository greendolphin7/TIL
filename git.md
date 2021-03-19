### 깃 시작

git init - 대상이 되는 폴더를 git으로 관리하겠다.

git status - 어떤 변경사항이 있는지 확인하는 명령어

stage 단계 - 변경사항이 관리되기 시작하는 단계

git add 파일명

### 기록하는 사람 정보 설정
git config --global user.name 이름  
git config --global user.email 이메일

### 위 부분 설정 끝난 후 커밋하기
commit 단계 - git commit -m '커밋 메시지'

### 로그 기록 확인
git log - 기록 확인
git log --online(옵션)

### 깃헙 주소 설정하기
git remote add origin 깃헙주소 예 : https://github.com/greendolphin7/~~~

git push origin master -> 저장 완료


### 클론

git clone + url

업데이트 할 때 
git pull origin


### .gitignore

git을 쓸 때 파일에 변화가 존재해도 git에 영향을 끼치지 않게하는 파일이다.

안에 파일 이름을 적으면 작동된다.

또는 '*.py' 라고 작성하면 python 파일들은 모두 깃에 영향을 받지 않는다.

gitignore.io 에 들어가면 자신의 프로젝트에 꼭 맞는 .gitignore 파일을 만들 수 있다.

### git add 취소하기
$ git rm --cached 파일명   : git add 해놓은 파일 내리기


### VIM

$ git commit --amend 를 통해 VIM으로 들어갈 수 있다.

i를 누르면 데이터 넣기 모드 (esc를 누르면 모드 취소)
:wp   (저장하고 나감)

### git reset 
id 값은 $ git log --oneline 으로 확인 가능
$ git reset --hard id값  : 코드도 변하고 커밋하기 전으로 돌아감  
$ git reset --soft id값  : 코드는 변하지 않고 add 한 후로 돌아감 (staging)  
$ git reset id 값        : 코드는 변하지 않고 커밋하기 전으로 돌아감 (working directory)  