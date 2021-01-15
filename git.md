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