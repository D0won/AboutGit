# 명령어 정리

1. git으로 관리할 경로까지이동

2. 초기화
> git init

3. 브랜치 이름 기본값 변경하기(기본값이 master일떄)
> git config --global init.defaultBranch main (초기값 변경) <br>
> git branch -M main(현재 브랜치명 수정)

4. git 상태확인
> git status

5. git으로 관리하는 파일로 추가
> git add

6. commit(해당 시점을 저장)
> git commit -m "커밋 메세지"

7. commit 이전에 계정정보 등록(--global 옵션은 해당컴퓨터 전체에 적용)
>  git config --list <br>
>  git config --global user.email "you@example.com" <br>
>  git config --global user.name "Your Name"

8. commit 정보 확인
> git log

9. 과제
> project_5/test1를 생성 <br>
> git으로 관리 <br>
> 파일 생성, 최소 커밋의 수는 5번 이상


## 로컬 컴퓨터(코드있음)와 github 사이트(비어있음) 연결

1. remote 정보 확인
> git remote <br>
> git remote -v

2. remote 추가
> git remote add 리모트이름 github리퍼지토리주소 <br>
> git remote add origin https://github.com/D0won/ABOUTGIT.git

3. remote 삭제
> git remote rm 리모트이름 <br>
> git remote rm origin

4. github 데이터 넣기
> git push -u origin main(처음에) <br>
> git push


## clone
- 코드가 없는 상태에서 전체 코드를 다운로드 받을 경우

- 현재 위치에 리퍼지토리 이름의 폴더를 만들고 파일을 가져온다.
> git clone <git-remote-url> <디렉토리> (파일명 작성) <br>
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

## 브랜치 병합

- main에서(main으로 코드 합류)
> git merge 브랜치명 <br>
> git add . <br>
> git commit -m "메세지"

## 브랜치 삭제
> git branch -d 브랜치명

## 브랜치 복구
> git branch 브랜치명 커밋번호

> git log --graph --oneline --all

## 파일 제외 시키기(gitignore)

- 작업 디렉토리 최상위에 위치하게 한다.
- .gitignore 파일을 작성하고, 제외하고자 하는 파일에 대한 내용을 기재한다.

- 경로는 상관없이 특정파일 제외하기
> filename.txt

- 현재 경로에 있는 파일만 제거
> /filename.txt

- 특정 폴더에 있는 파일 제외
> 폴더명/

- 특정 경로의 특정 파일 제외
> 폴더명/filename.txt

- 특정 경로 아래 특정 파일 제외
> 폴더명/**/filename.txt

- 특정 확장자를 가진 파일 제거
> *.png

- 예외
> !filename.txt

- git의 캐시값 때문에 적용이 안될 수 있다
- 캐시 삭제하고 진행
> git rm -r --cached . <br>
> git add . <br>
> git commit -m "캐시 삭제"

## reset

> git log <br>
> git log --oneline <br>
> git reset --soft 커밋아이디

- 스테이지에 올리지 않은 파일 정리
> git clean -f     

- github와 로컬 컴퓨터 내용이 일치하지 않을 경우 로컬 컴퓨터 내용으로 push 함.
> git push -f       

## 옵션
> – soft: 커밋을 취소하지만 스테이징 영역에는 그대로 남겨둡니다. <br>
> 워킹 디렉토리의 변경 사항은 그대로 유지됩니다. <br>
> 스테이징 영역의 변경 사항은 그대로 유지됩니다. <br>
> 커밋 기록은 변경되지 않습니다.

> –mixed: 커밋을 취소하고 스테이징 영역을 비웁니다. <br>
> 워킹 디렉토리의 변경 사항은 그대로 유지됩니다.<br>
> 스테이징 영역은 비워집니다. <br>
> 커밋 기록은 변경되지 않습니다.

> –hard: 커밋을 취소하고 스테이징 영역과 워킹 디렉토리를 모두 이전 상태로 되돌립니다. <br>
> 워킹 디렉토리의 변경 사항은 모두 삭제됩니다. <br>
> 스테이징 영역은 비워집니다. <br>
> 커밋 기록은 변경됩니다.

## reflog
- 로컬 저장소에서 HEAD의 업데이트 기록을 확인

> git reflog <br>
> git reflog "branch name"

## revert
- git revert [되돌리고 싶은 commit의 해시값 6자기까지]

- commit A -> commit B -> commit C 라면 <br>
역순 commit C -> commit B -> commit A순으로 revert

- revert한 이력이 다 개별적으로 남은 위의 경우 3개의 커밋이 더 생성됨
- 이때 --no-commit 옵션을 주면 커밋은 하나만 생성되지만 명령어는 3번에 걸쳐 작성

- 한번에 명령으로 3단계를 취소하고 싶다면 HEAD~3 <br>
git revert --no-commit HEAD~3 #3단계를 취소함

- revert 후 commit하고 push하면 된다.

## 깃 구성
- 작업트리(파일) - 스테이지 - 저장소 로 구성
- git add . -> 스테이지로 파일 이동
- git commit -m -> 저장소로 파일 이동