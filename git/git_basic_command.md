# git 저장소 사용 기본 커맨드


- `git init`
    - 새로운 git 레포 생성
    ```
    git init
    ```
- `git status`
    - 브랜치, 커밋여부 등등 확인 가능
    ```
    git status
    ```

- `git add 파일명`
    - add를 하기 전에는 각 파일들이 옆에 U로 표시된다 (Untracked)
    - add를 한 파일은 옆에 A로 표시된다 (index added)
    - `.` -> 현재 위치의 모든 파일
    ```python
    # README.md 파일을 add
    git add README.md
    ```
        

- `git commit -m "커밋메세지"`
    - `commit`
    - `-m` -> 메세지
    - "커밋메세지"의 이름으로 커밋
    ```python
    # first commit 이라는 이름으로 add 된 파일 commit
    git commit -m "first commit"
    ```

- `git log`
    - 커밋을 한 로그(기록) 표현
    - `--online`
        - 각각의 커밋 정보를 간단하게 표현
    - `--graph`
        - 브랜치까지 시각적으로 표현해주는 옵션
    ```
    git log
    git log --online
    git log --online --graph
    ```    

## github에 올리기

- `git remote add origin '주소'`
    - `remote` 원격저장소
    - `add` 더하기
    - `origin` 별명은 이거고
    - 실제는 이 주소야
    ```python
    # 입력한 주소를 origin 이라는 별명으로 원격 저장소로 만든다
    git remote add origin '주소'
    ```
- `git remote`
    - 저장된지 확인 가능
    - `-v` -> 주소와 별명까지 확인 가능
    ```python
    # origin 
    git remote
    # origin : https://agnmkasdljtklasdjt.asdkgmk 형태로 저장된 원격 저장소까지 조회
    git remote -v
    ```
- `git push origin master`
    - `master` 브랜치를 `origin` 별명으로 저장된 주소에 `push`
    ```python
    # master 브랜치 -> origin 주소에 push(업로드)한다.
    git push origin master
    ```

---
## fork 한 repo의 데이터를 PC로 가져오는 방법
    
- `git clone https://~~` 
    - github 에서 PC로 내려받기
    ```python 
    # 마지막 TIL-copy는 이미 경로에 같은 폴더명이 있어서 TIL-copy라고 이름을 변경하여 가져온다는 뜻
    git clone https://github.com/junhyukM/TIL.git TIL-copy
    ```

---

## 브랜치? 

- `git branch`
    - branch 조회
    - `-c` branch 생성
    - `-d` branch 제거
    ```python
    # mjh 라는 이름의 branch 생성
    git branch -c mjh

    # mjh 라는 이름의 branch 제거
    git branch -d mjh
    ```

- `git switch branch이름`
    - branch 변경 
    ```python
    # 기존에 있던 branch에서 mjh branch로 변경
    git switch mjh
    # switch와 같은 기능을 하는 명령어로 최신 버전에서는 잘 사용하지 않지만 알고는 있자
    git checkout mjh
    ```


 ## **새로 생성한 브랜치에서 어떤 작업을 하고나면 반드시 저장은 기본이고 `add`와 `commit`을 해야한다.**


- `git merge branch이름`
    - branch의 내용을 현재 위치한 branch를 기준으로 `merge`
    ```python
    # 현재 master branch인 상태에서
    # mjh branch의 내용을 master branch에 merge하기
    git merge mjh
    ```    

---
## 협업과정에서 git 사용 시 충돌이 나는 경우

1. github에 있는 내용이 다른 사용자에 의해 변경이 되어있는 상태에서 `push`를 시도하는 경우가 대부분
2. 내용이 변경된 `repo`를 `pull` 해와서 내 로컬파일 상에서 `merge` 한다
    - `git pull origin master`
        - 다른 사용자에 의해 github 파일들에 변화가 생긴경우 로컬의 파일들과 차이가 있기 때문에 그 내용을 끌어와 로컬 파일에 반영 
        - `pull` 끌어온다
        - `origin` 주소에서
        - `master` 해당 branch에 반영된 내용
3. `merge` 된 `commit`을 다시 `push` 한다

---

## github 상에서 `branch`를 `merge`하는 방법

1. github의 `repo`가 권한을 가진 다른 사용자와 함께 파일을 수정할 때 충돌하는 경우가 많다
2. github에 branch 생성이 된 상태인지?
    - `git push origin branch이름`
        - 새로운 branch를 생성하여 업로드
        ```python
        # login 이라는 이름의 branch를 생성해서 작업 후 github에 login이라는 branch를 생성하며 업로드한다.
        git push origin login
        ```
3. 생성한 `branch`를 `master branch`와 `merge` 하기 위한 `pull requestst`
    - ![a](../markdown/assets/add_id_branch.png)
    - ### `git push origin branch이름` 으로 github에 추가된 `branch` 확인
    - ![b](../markdown/assets/add_id_branch_2.png)
    - ### `id branch`인 상태에서 `pull request` 버튼 클릭
    - ![라이언](../markdown/assets/add_id_branch_3.png)
    - ### 간단한 메모와 함께 `pull request` 생성
    - ![c](../markdown/assets/add_id_branch_4.png)
    - ![d](../markdown/assets/add_id_branch_5.png)
    - ![e](../markdown/assets/add_id_branch_6.png)
    - ### `master branch`에도 `id branch`에 있던 파일이 `merge`가 된 것을 확인

---


## 권한이 없는 다른 사용자의 레포에서 자료 수정해서 `pull request` 하는 과정
1. `fork`
    - 협업하고자 하는 `repo`에서 `fork` 버튼을 눌러 내 프로필에 `repo` 생성
2. `clone`
    - `clone`명령어를 사용하여 로컬에 데이터 내려받기
3. `fork`된 레포에 `push`
    - 내용 수정 등 작업 후 `fork`했던 내 `repo`에 `push`
4. `pull request`
    - ![req](../markdown/assets/add_pull_req.png)
    - `fork`를 했던 원래 `repo`에 해당 사항을 `merge` 해주겠습니까? 하는 요청의 의미로 `pull request`