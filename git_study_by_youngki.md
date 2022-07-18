# git 설치
- git setup
1. VScode 에디터 설정 -> 충돌 문제 발생 시 VScode로 볼 수 있음
2. 배쉬 온리X 윈도우 프롬프트 -> 편의를 위해 선택

- GitLens
VScode 확장으로 설치, 왼쪽 사이드바 원 안에 줄기 아이콘으로 사용
VScode 환경에서 변경사항, 브랜치, 리모트, 히스토리 등 Git을 편하게 확인

# git 기본작업원리
1. 개발자A가 Local Repository에서 작업
2. 작업한 내용을 Commit & Push하여 Server Repository에 업로드
3. 개발자B는 A가 작업한 소스를 Pull하여 Local Repository에 받아옴

# git 작업명령
git config --list       //깃 설정 목록으로 보기
git config --global user.name [깃허브유저명]	//깃 유저명 설정
git config --global user.email [깃허브이메일]	//깃 이메일 설정
git init                //깃 초기화
git add --all           //업로드할 파일 준비
git commit -am "메시지 작성"        //업로드할 파일 커밋으로 묶어주기
git remote add origin [깃허브주소]  //서버와 로컬 통로 연결
git push -u origin master          //서버에 업로드
git pull                //서버에서 받아오기
git clone               //깃허브에 만든 저장소 클론하기

# origin이란?
원격 저장소의 기본 이름
git remote add [이름] [주소] 형식으로 명령어에서 일반적으로 이름에 origin을 사용
이 때, 주소는 이름에 등록되어 주소를 일일히 칠 필요없이 origin만 사용 가능

# add & commit 3단계
1. working directory -> 소스를 작업하는 디렉터리, add시 staging area로 넘어감
2. staging area -> 준비 태세 단계, commit시 git repository로 넘어감
3. git repository -> 로컬 저장소, push시 server repository로 올라감

# git reset [hard | soft | mixed]
hard -> 돌아간 이력 이후의 변경사항을 제거, 완전히 리셋
soft -> 돌아간 이력 이후의 변경사항은 유지, staged 상태로 만듬
mixed -> 돌아간 이력 이후의 변경사항은 유지, unstaged 상태로 만듬

# git reset 사용법
1, 2, 3번 커밋이 쌓여있고 3번에서 2번으로 돌아가고 싶을 경우
-> git reset으로 2번으로 돌아감
-> rollback 메시지를 넣고 commit 생성
-> 소스를 rollback commit과 똑같이 수정
-> push 하면 돌아가기 성공 (reject 당하면 -uf 옵션 또는 +브랜치로 push)

# git revert
git reset과 비슷하지만 소스를 유지하고 history가 쌓임
되돌아간 흔적을 남기기위해 reset보다 revert를 사용 권장

# conflicts 해결방법
여럿이 같은 부분을 수정하면 충돌이 날 경우
1. 현재 변경 사항 수락 -> 내 코드만 수용
2. 수신 변경 사항 수락 -> 다른 사람 코드만 수용
3. 두 변경 사항 모두 수락 -> 양쪽 코드를 모두 수용
4. 직접 해결 -> 자동으로 해결이 안될 경우 직접 코드를 수정

# git flow & git issue 실습 과정
# 실습 과정 기록 https://blog.naver.com/ceron3804/222812092254
1. git flow	
git flow 설치 유무 확인
일반적으로 git을 설치하면 같이 설치 

2. git flow init
git flow 초기화
-d 옵션을 사용하면 엔터를 칠 필요 없이 default로 진행
develop 브랜치 생성

3. git flow feature start [브랜치명]
feature 브랜치 생성
스터디에서 브랜치명은 issue-이슈번호 형식으로 약속

4. git branch -a
모든 브랜치 확인하기

5. git push origin --all
생성한 브랜치 깃허브에 올리기

6. github에 브랜치가 생겼는지 확인하기

7. github Issues에서 이슈 생성
오른쪽 사이드바 활용하여 이슈에 옵션 추가

8. github Projects (classic)에서 이슈 드래그
- to do 컬럼 -> 해야할 일
- in progress 컬럼 -> 진행중인 일
- done 컬럼 -> 끝난 일
스터디에서 3가지 컬럼을 쓰기로 약속
맞는 컬럼에 드래그하여 넣기 

9. code .
VScode를 현재 프로젝트로 빠르게 오픈
이곳에서 이슈에 올릴 md 파일 작성

10. add & commit
작성한 md 파일 올릴 준비

11. git flow feature publish
작성한 md 파일 feature 브랜치에서 main 브랜치로 풀리퀘스트 요청

12. github 상단에 나온 Compare & pull requests 클릭

13. Pull requests에 녹색 Merge pull request 나오면 성공이므로 merge하기