git - 형상관리 툴
    - 로컬 레포지토리 

# 다운로드
    구글 검색 - git-scm
    https://git-scm.com/

    -> 우측 모니터 모양에 있는 다운로드 클릭
    -> Click here to download 클릭
    -> 다운로드 창 뜨면 전부 next 클릭

git init
# 로컬 레포지토리 생성
    - 파일 생성
    - git 입력시 상단에 git 어쩌구 뜨면 괜찮음
    - cd 파일 경로 입력
    - git init 입력시 Initialized empty Git repository in C:/git_exam/.git/
        나오면 됨
    - 그러면 만든 폴더에 .git 파일 생긴걸 확인 할 수 있음
    
git config
# 계정 설정
    -g (전체 설정)

    - git config --global user.name "git 허브 가입시 기입한 사용자 명"
        예) git config --global user.name "chuminkyoung"
    
    - git config --global user.email "git 허브 가입시 기입한 이메일"
        예) git config --global user.email "chuu_u94@naver.com"

스냅샷(SNAPSHOT)
# 스테이징 단계 - 소스의 변경사항을 스테이지에 올리는 단계
    1) git add 파일명, 파일 경로
        예) git add . (모단 변경이 있는 파일)

    2) 커밋 단계 - 소스의 변경 사항의 복구 시점
        git commit -m "메모" 파일명, 파일 경로
            예) git commit -m "메모" .

    3) 히스토리 확인
        - git log
            -> 노란글씨로 커밋명 길게 나옴
        - git log --oneline (짧게 볼때)

        - git add . 수정된 파일 저장
        - git commit -m "메모" .
        - git log --oneline 으로 수정 후 저장
            HEAD -> 현재 시점의 위치
            MASTER -> 브랜치 명

    4) 현재 시점 변경 (복구)
        - git checkout commit (아이디 노란글씨) --> 아이디 시점으로 이동
        - git checkout --> 가장 최근 시점으로 복귀

        - git log --online 
            -> 히스토리확인
        - git checkout -
            -> 원래 작업 내용으로 복구
        - git log --online
            -> 기록 확인
    

--------------------------------------------
## 브랜치
기본 브랜치 master

- 브랜치 조회
    git branch
        ex) master

- 브랜치 생성
    git branch 브랜치명
        -> 현재 위치하고 있는 브랜치의 소스가 새로 생성되는 브랜치에 복사
        
        ex) git branch member (생성)
            -> git branch 로 branch 생성된거 확인 가능

- 브랜치 이동
    git checkout 브랜치명
        ex) git checkout member
        -> git branch 로 브랜치명 확인 가능 (* 초록색 글씨)

- 브랜치 삭제
    git branch -d 브랜치명
    -> git branch -D 강제 삭제

    git branch -d 브랜치명 / 안될때는 강제 삭제 -D

- 브랜치 병합   (조장만)
    git merge 브랜치 명
        ex) git checkout test 인 상태에서 -> git merge member 입력하면 test 와 member 통합 됨
    
        - 현재 브랜치에 merge에 입력한 브랜치 소스가 병합

    - 통합 후 기능 테스트 해야함
        -> 메인 브랜치로 이동

        *** 충돌났을 경우
            CONFLICT (content): Merge conflict in README.md
                -> 충돌
                -> 파일 열어서 맞는 부분을 확인해서 수정 후 git add . 로 저장 후 git merge

- 원격 레포지토리 
    로컬 레포지토리 -> 원격 레포지토리 (github, gitlab, ...)

    -> 원격 레포지토리 연결
        - git remote add origin 원격 레포지토리 주소 (만든 git 저장 자리)
            예) git remote add origin https://github.com/chuminkyoung/git_exam.git

            - git remote add 할때 기존 원격 레포지토리 삭제 후 다시 등록
                -> git remote add 

    -> 로컬 레포지토리 상태 -> 원격 레포지토리 반영
        - git push origin 원격 브랜치명

        예) git push origin master
            - 인증 어쩌구 나오면 인증 하면 됨
        
            git push origin 브랜치명 -> git에 branch 추가

- 원격 레포지토리 상태 -> 로컬 레포지토리 상태로 동기화
    -> 작업 시작전에 소스 동기화 먼저(!!!)
    git pull origin 원격 브랜치명


-----------------------------------------------------------------------------


# GIT UI 툴
sourceTree 설치
https://www.sourcetreeapp.com/