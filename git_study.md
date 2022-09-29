#git 활용
-

#git flow
- 기본 개요 - 협업을 위한 툴 (windows에는 기본으로 git 설치시 자동으로 설치된다.)
- 과정
  1. 처음에만 해야하는거(git 설치 및 git flow 초기화(명령어 - git flow init(나오는거 다 enter)))
  2. git 에서 issue등록 (해야하는 것 등록(study,개발,계획,토의 등), 대상, 프로젝트, 라벨 등록가능)
    다른 사람이 작업할 수도 있기에 설명 자세히 작성 바람!
  3. projects에서 확인. ( to do에 있음)
  4. projects에서 할 작업 선택해서 todo-> In progress로 옮김(드래그)
  5. git에서 선택한 issue branch로 이동(명령어 - git flow feature start issue-N(N에 issue #번호 넣음))
  6. 작업 진행! (명령어 - code . (code 쉽게 open))
  7. add 및 commit 시켜주기.
  8. 올리기 (명령어 - git flow feature publish)
  9. pull request에서 확인
* 1 에서 오류 날시( git branch 새로 만들어 주어 checkout 해 입력해 주거나, 목록에 잇는거 적어야 댐)
