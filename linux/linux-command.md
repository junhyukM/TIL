# 리눅스 명령어 정리

```shell
명령어 옵션 인자(매개변수) 들 사이는 항상 띄어쓰기를 해야함
```

`git -h` (git 의 다양한 옵션이나 내용에 대해 help desk 같이 안내문 나옴)

- 명령어 옵션 인자 입력순을 보며 파악 내용
    - `-v` 와 `--version` 의 차이

    1. `git -v`
    2. `git --version`
        - 의미는 동일하다.
        - 약어는 - 하나
        - 단어는 -- 두개
    
- `pwd` (print working directory)
    - 현재 작업중인 경로 출력
- `ls` (list)
    - 현재 위치해 있는 폴더에 어떠한 파일 혹은 폴더가 있는지 출력
    - 폴더 -> 파란색 글씨로 표시
    - 파일 -> 하얀색 글씨로 표시
    - `-a` (option) : 숨김처리된 파일, 폴더까지 전부 출력
        - `ls -a`
            - `./` 내 현재 위치
            - `../` 상위 폴더   

**상대경로**로 이동 -> 현재위치를 기준으로 cd 커맨드를 사용해 이동하는 것

- `cd` (change directory)
    - `cd ../` -> 현재 위치의 상위 폴더로 이동
    - `~` -> home 으로 이동 (계정의 최상위 위치)
        - `cd /` -> root로 이동

**절대경로**로 이동 -> cd 커맨드를 이용하는 것은 동일, 근데 `~` 부터 모든 경로를 직접 기입
```
cd ~/Desktop/swcamp25/markdown
```

- mkdir (make directory)
    - 폴더 생성

- touch ()
    - 파일 생성

- rm (remove)
    - 파일 삭제 (폴더는 지울 수 없다)
    - `-rf` option 사용하면 폴더 지울 수 있음
        - `-r` (recursion) 재귀
        - `-f` (force) 강제

          **강제로 재귀?**
        - 폴더를 삭제
        - 위의 두 옵션을 동시에 `-rf` 
    ```
    rm -rf git 
    ```


## git 사용하기

- `git config --global user.name`
    - `git` 명령어에서
    - `config` 설정
    - `global` 전역으로 설정 (컴퓨터 전체)
    - `user.name` 이름 설정

```
git config --global user.name -> 알려줘 (설정안했으니까)
git config --global user.name 'junhyukM' -> 설정할게 ('junhyukM' 으로)(매개변수)
```

```
git config --global user.email -> 알려줘 (설정안했으니까)
git config --global user.email 'minjh1031@gmail.com' -> 설정할게 ('minjh1031@gmail.com' 으로)(매개변수)
```


- `git config --list`
    - 위에 설정한 부분들 확인하는 명령어
    - 내용이 많아서 한번에 출력이 안되는데 마지막까지 가면 END 되면서 거기서 빠져나오는게 안되는데
    - 빠져나오려면 `q` 누르면 빠져나온다
    - 터미널출력창이 작아서 생기는 문제 

- `mv` (move)
    - 파일 위치 옮기는 명령어
    ```
    mv markdown.md markdown/   -> markdown.md 를 markdown 폴더 안에 옮기기
    ```












