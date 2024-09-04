## 명령어 정리

1. git으로 관리할 경로까지이동

2. 초기화
> git init

3. 브랜치 이름 기본값 변경하기(기본값이 master일떄)
> git config --global init.defaultBranch main (초기값 변경)
> git branch -M main(현재 브랜치명 수정)

4. git 상태확인
> git status

5. git으로 관리하는 파일로 추가
> git add

6. commit(해당 시점을 저장)
> git commit -m "커밋 메세지"

7. commit 이전에 계정정보 등록(--global 옵션은 해당컴퓨터 전체에 적용)
>  git config --list
>  git config --global user.email "you@example.com"
>  git config --global user.name "Your Name"

8. commit 정보 확인
> git log

9. 과제
> project_5/test1를 생성
> git으로 관리
> 파일 생성, 최소 커밋의 수는 5번 이상


## 로컬 컴퓨터(코드있음)와 github 사이트(비어있음) 연결

1. remote 정보 확인
> git remote
> git remote -v

2. remote 추가
> git remote add 리모트이름 github리퍼지토리주소
> git remote add origin https://github.com/D0won/project5_work1.git

3. remote 삭제
> git remote rm 리모트이름
> git remote rm origin

4. github 데이터 넣기
> git push -u origin main(처음에)
> git push


## clone
- 코드가 없는 상태에서 전체 코드를 다운로드 받을 경우

- 현재 위치에 리퍼지토리 이름의 폴더를 만들고 파일을 가져온다.
> git clone <git-remote-url> <디렉토리> (파일명 작성)
> git clone <git-remote-url> . (파일명이 리퍼지토리 이름)

## pull
- 코드가 있는 상태에서 변경된 부분만 받을 경우

## 브랜치 만들기
- 브랜치 목록 확인
> git branch

- 브랜치 생성
> git branch test01

- 브랜치 이동
> git switch test01

- 브랜치에서 소스 코딩, add, commit 작업 진행

## 파일 제외 시키기
- gitignore

