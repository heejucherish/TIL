![공부_이미지](./img/bc.png)

# GIT
- 분산 버전 관리 프로그램 버전을 관리하기 위한 프로그램 
버전: 컴퓨터 소프트웨어 특정 상태 
- 개발되어온 과정 파악가능/ 코드의 히스토리버전을 관리하는 도구

## GitHub
- git 기반의 
저장소 서비스를 제공하는 서버

### GUI 
: 그래픽을 통해 사용자와 컴퓨터가 상호 작용하는 방식, CLI에 비해 사용하기 쉽지만 단계가 많고 컴퓨터의 성능을 더 많이 소모

### CLI
: 명령어를 통해 사용자와 컴퓨터가 상호 작용하는 방식

> 개발 시스템이 CLI를 통한 조작 환경을 제공

>기본 명령어
- `touch` : 파일을 생성하는 명령어
- `mkdir` : 새 폴더를 생성하는 명력어
- **ls** : 현재 작업 중인 디렉토리의 폴더 
- **Ctrl+L** :  창정리
- **path** : 정보를 주의깊게 살펴봐야한다! 
- **start** : 파일을 열어주는 명령어 
- **rm** : 파일지우는 명령어
- **rm - rf** : 폴더를 지우는 명령어/ 주의 필요함! 강제 삭제

> 절대 경로 / 상대경로 차이점 
- 절대 경로: 루트 디렉토리 부터 목적 지점까지 거치는 모든 경로를 전부 작성한것 c:/users 부터 시작 
- 상대경로: 현재 작업하고 있는 경로에서 위치를 정하는것 상대적 위치를 작성한 것 
- ./ 현재 작업하고 있는 폴더 ../ 현재 작업하고 있는 폴더의 부모 폴더- 상위 폴더 

> README.md 
- 전체적으로 공식문서처럼 볼수있다. 어떤 프로젝트인지 어떤 기술이 사용되었는지 왜 기획햇는지 설명 
- 개인 프로젝트의 소개문서 작성
매일 학습한 내용 정리
- 마크다운을 이용한 블로그 운영/ 개발 문서의 시작과 끝 
- README  문서-> 반드시 정리
일반적으로 소프트웨어와 함께 배포
- 가장 먼저 보는 문서 markdown 으로 작성 
- **대문자** 만 가능!! 

>Repository 
- 특정 디렉토리를 버전 관리하는 저장소 

- remote: github, gitlab
- local: 개인 pc 

     **git init** : 해당 명령어로 로컬 저장소를 생성
    - .git 파일이 생기므로 그 폴더는 깃에서 버전관리할수있다는 뜻

     
     git: 디렉토리에서 버전관리에 필요한 모든것이 들어있음

- 명령어 **ls -a** : 폴더 내부에 있는 모든 파일 보여줌(숨긴 파일 포함)

- (master) > 지금 이경로는 git으로 관리되고있다는 뜻 , / branch 명 

# commit은 3가지 영역을 바탕으로 동작

1. working directory : 내가 작업하고 있는 실제 디렉토리 > staging area로 올리고

2. staging area  : 커밋으로 남기고 싶은, 특정 버전으로 관리하고 싶은 파일이 있는곳 / repository에 저장하기 전에/ 중간 확인하는 공간 
3. Repository

- 상태 확인 
  - untracked: 버전 관리 대상이 아닌것들. 새로운 new. 추적되지 않은 파일 > 명령어 git add 하면 staging area로 이동 
  - staged : staging area에 올라온 상태. > 명령어 git commit 
  - committed : commit 01 / 커밋 완료 
  - modified : 수정되었다는 상태 

- 명령어 **git status** : git의 상태를 알아보는 명령어 
- 명령어 **git add .** : 모든 파일을 add하겠다. 


# GIT과 Local 연결 추가 
- 깃헙 repository 와  local repository 를 연결해주기
- 깃헙 repository를 local repository에 등록 한다는 말임! 
  
- **git remote add origin 레포지토리 주소**
  
- **git push origin master** 

>  master 차이점 branch 
- origin > github repo 위치 

-  명령어 : **git remote -v** >지금 등록된 레파지토리, 유저 정보 알수있음

-  clone 과 pull의 차이점 > 복제 github repository를 local로 복제 .git 파일도 같이 복제가 된다. 하지만 이 .git 파일은 git 설정이 있는 폴더이다. 
  (즉, remote 주소도 같이 복제가 된다.) git init 할 필요가 없다는 말~! git remote add도 할 필요 없다는 말~  
  
-  remote repository에 있는 버전과 동일한 버전으로 다운 받는 것 
  
-  git pull을 하려면 무조건 remote 정보가 필요하다. 이미 git으로 관리가 되고있어야한다. 즉 .git 파일이 존재해야한다. 

-  최초 1회만 clone을 해주면 쉽고 편하게 이용할수가있다. 

-  그 이후로는 pull과 push만 사용하면 된다. 


## 계정 추가 

- 명령어 **git config --global user.email "메일"**
- 명령어 **git config --global user.name "이름"**

## commit
-  commit 메세지 넣어줘야한다.
-  vim < 리눅스 텍스트 에디터,
     - vim 2가지  < command 모드 , edit 모드 
     - insert 키: 텍스트 수정/ esc + :wq : 저장하고 나가기 / wq!

- **git status**: git 상태 확인
- **git log** : commit 기록 보기 
- 명령어 **git log --oneline** : log 한줄로 간단하게 보기 
- modified : 수정된 파일
- **git commit -m "메세지 입력"** > 커밋메세지는 자세하게!!! 
- 왜 굳이 staging area  를 거치는가?? 내가 확실히 버전을 관리하고싶은 파일만 저장해서 관리하는게 더 효율적이기 때문에. 
- 명령어 **git diff** : 두 commit 간 차이 보기 

  
# remote repository 연결 추가
- git remote add origin 레포주소  
- git remote -v : 등록 확인
- git push 레포별명 브랜치명(origin master)
- git clone 레포 주소
- 경로를 주의깊게 지켜봐야한다. master 가 없으면 git add가 안됨 위치의심 항상! 
- 대문자 README
- 기준이 되는 버전은 GITHUH(기준버전) , 싱크를 맞춰줘야한다. 
- 버전을 맞추지 않으면, 충돌이 발생간다. 업데이트되면 GITHUB 버전 다운받아야한다. 
- GIT에 있는 내용을 받아와서 싱크를 받아와야한다.
- 내려받는건 PULL MASTER , PUSH 
- git pull origin master << 업데이트 해주는 명령어>>

# 마무리 정리 <중요> 1. 가장 먼저 pull 당겨오기를 해야한다 왜냐하면 업데이트 해야하니까! 그다음 공부 후> 2. add 하기 3. commit 하기 4. push 하기 깃에 보내기


## 마크다운 참고 
- https://www.markdownguide.org/cheat-sheet/



