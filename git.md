# **GIT**   
***
#### git 최초설정
***
터미널프로그램(git bash)에서 아래 명령어 실행
```git
    git config --global user.name "(본인이름)"

    git congig --golbal user.email"(보인 이메일)"
```
아래의 명령어들로 확인
```git
    git config --global user.name

    git config --global user.email
```
#### 프로잭트 생성 & git관리시작
***
 적당한 위치에 원하는 이름으로 폴더를 생성하고 vs code로 열람
    해당 폴더에서(vs code 터미널 기본)아래 명령어 입력
   ```git
    git init
   ```

폴더에 숨김모드로 *.git*폴더생성 확인(이 폴더를 지우면 git관리내역이 삭제됩니다)
터미널에 아래 명령어 입력
   ```git
    git status
   ```   

 *.gitignore*파일을 사용하여 배제할 요소들을 지정
#### 타임캡슐에 담기
***
파일 하나 담기
```
    git add (파일이름) 
```
모든 파일 담기
```
    git add .
```
#### 타임캐슐 묻기
***
아래 명령어로 commit
```
    git commit
```
커밋 메세지까지 함께 작성하기
```
    git commit -m "first commit"
```
아래 명령어와 소스트리로 확인하기
```
    git log
```
*add*와 *commit*한꺼번에
```
git commit -am "(메세지)"
```
#### 과거로 돌아가는 두방식
***
**reset:** 원하는 시점으로 돌아간 뒤 이후 내역들을 지운다
**revert:** 되돌리기 원하는 시점의 커밋을 거꾸로 실행

>reset 사용하여 과거로 돌아가기   

```
git log //명령어로 커밋 내역 확인하고 커밋해시복사
git reset --hard (돌아갈 커밋 해시)
```
>revert 사용해서 revert 전으로 되돌아가기
```
git log //명령어로 커밋 내역 확인하고 커밋해시복사
git revert (되돌아갈 커밋 해시)
```
**Source Tree로 진행해보기**
* revert -해당커밋에 마우스 우클릭->"커밋되돌리기"
* reset  -해당커밋에 마우스 우클릭->"...이 커밋으로 초기화"->선택지에서 hard선택
#### 여러 Branch 만들어보기
***
브랜치 생성/이동/삭제하기
```
    git branch yee //yee라는 이름의 브랜치 생성
    git branch     //브랜치 목록 확인
    git switch yee //yee 라는 브랜치로 이동
```
브랜치 삭제하기/이름바꾸기
```
    git branch -d(삭제할 브랜치명)
    git branch -m (기존 브랜치명) (새 브랜치명)
```    
#### branch를 합치는 두가지 방법
***
**merge:** 두 브랜치를 한 커밋에 이어붙이기(브랜치 사용내역을 남길 필요가 있을때 적합)
**rebase:** 브랜치를 다른 브랜치에 이어붙임(한줄로 깔끔히 정리된 내역을 유지하기 원할 때 적합)
>merge로 합치기
* main 브랜치로 이동
* 아래의 명령어로 병합
    ```
    git merge yee // yee브랜치를 main브랜치로 병합
    ```
 * 병합된 브랜치는 삭제
     ```
     git branch -d yee //yee브랜치 삭제
    ```
>rebase로 합치기
* yee브랜치를 main브랜치로 rebase
* yee브랜치로 이동(* merge때와는 반대)
    ```
        git rebase main
    ```
* main브랜치는 뒤쳐져있는 상황 
(main브랜치로 이동후 아래명령어로 yee시점으로 fast-foraward)
    ```
        git merge yee
    ```
* yee 브랜치 삭제

#### 충돌 해결하기
***
>**merge충돌 해결하기**
* 오류 메세지와 git status확인, VS code에서 해당 부분 확인
* 당장 충돌 해결이 어려운 경우 아래 명령어로 merge중단
    ```
    git merge --abort //merge 중단하기
    ```
* 해결 가능 시 충돌 부분을 수정한 뒤 _git add ._ -> _git commit_ 으로 병합완료

>**rebase충돌 해결하기**
* 오류 메세지와 git status확인, VS code에서 해당 부분 확인
*  당장 충돌 해결이 어려운 경우 아래 명령어로 rebase중단
    ```
    git rebase --abort //rebase 중단하기
    ```
* 해결 가능 시 충돌 부분을 수정한 뒤   _git add ._ 
    ```
        git rebase --continue // 충돌이 해결될때까지 반복
    ```
#### GitHub 시작하기
***
* personal access token 만들기
  + 우측 상단의 프로필-setting
  + Developer setting
  + personal access token -generate new token
  + repo 및 원하는 기능에 체크, 기간 설정 뒤 generate token

