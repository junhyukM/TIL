# 프로젝트를 진행 시 git 관련 주의할 사항

## 보안이 중요한 데이터가 포함 되어 있을 수 있으므로, github에 접근이 안되게끔 하는 설정을 신경써야 한다.

- `.env` 파일
    - URL을 통해 데이터를 받고자 할 때, API 활용을 위해 발급 받은 키와 같이 타인에게 유포되면 문제가 되는 것들을 해당 파일에 저장

- `.gitignore` 파일
    - github에 push 할 때 해당 파일 내에서 지정한 데이터들은 포함되지 않게 설정 가능

### .gitignore 파일에는 https://www.toptal.com/developers/gitignore/ 페이지에서 원하는 조건을 선택 후 내용 전체 복사해서 붙여넣으면 간단하다.
    수업 시간에 활용시엔 python, window, visual studio code 세개 선택함
    $ 복봍할 때 ctrl + a 전체 선택 기본적인건데 몰랐다. 꿀팁



### `requests`, `decouple` 등 특정 모듈의 함수를 사용하기 위해선 모듈을 `install` 해주어야 한다.

```python
# 콘솔창에 입력한다
pip install requests
```

- 위에 설명한 ignore 관련 기능을 사용하려면 python-decoule 패키지 다운해야 가능.

### requests 패키지를 활용하면서 얻은 정보, get으로 가져온 데이터를 크롬 상에서 json 파일로 보기 좋게 하는 확장 프로그램 다운로드 하자
    - jason viewer 설치 -> 검색 후 크롬 확장 프로그램 다운로드 하면 됨

    