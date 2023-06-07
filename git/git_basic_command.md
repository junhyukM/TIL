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
        

- `git commit -m "파일명"`
    - `commit`
    - `-m` -> 메세지
    - "파일명"의 이름으로 커밋
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

