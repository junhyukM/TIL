# Git이 뭘까?

## Git을 이용한 버전 관리란?
### DVCS(분산 버전 관리 시스템) 
- 수정사항을 별개로 저장하거나 하는 기존의 방식과 다르게
- 사진을 찍는 것에 비유할 수 있는 개념으로, 데이터를 사진과 같이 취급하여 데이터를 다룬다
- 관리되고 있는 데이터를 개인 로컬에 받아 서버가 정상동작 하지 않을때도 데이터를 사용하는 것에 문제가 생기지 않는다는 장점이 있다

- 이러한 방식으로 동시다발적 작업과 단순한 버전관리에 용이하기에 지금까지 가장 많은 사용자를 가지고 있다

![git](https://git-scm.com/book/en/v2/images/areas.png)

위의 세가지 상태로 버전이 관리되며 세가지 경우를 설정하고 관리하는 기본적인 command는 [git_basic_command.md](https://github.com/junhyukM/TIL/blob/master/git/git_basic_command.md) 파일에 작성

---
## 기초 단계에서 Git을 사용하는 간단한 작업순서

> 기존에 레포가 없을 때
1. `git init` 커맨드로 `.git` 을 생성 (없을때만 이미 있는 경우는 제외)
2. 파일 작성 및 수정이 완료되면 `git add` 로 파일을 스테이지에 올린다
3. `add` 된 데이터를 `commit` 하여 레포에 저장 (사진을 찍는다)
4. github에서 관리하고자 한다면 `git remote add origin '주소'`를 사용해 원격 저장소를 만든다
5. `git push` 로 `origin`이라는 별명으로 등록된 주소에 업로드 한다.

> 이미 github에 올린 이력이 있고 데이터 추가 및 수정사항을 `push` 할 때
1. `git add`
2. `git commint`
3. `git push`
- 세가지 순서로만 작업을 진행하면 된다. 원격저장소, 계정 등의 정보는 이미 있다

