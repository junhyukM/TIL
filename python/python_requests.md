# requests 패키지를 사용한 간단한 데이터 추출

## requests 및 다른 패키지들 사용했던 메서드 정리


-패키지를 사용하기 위해선 import 필요
```python
import requests
from bs4 import BeautifulSoup
```

- `requests.get()`
    - 인자에 보통 url 을 입력하여 데이터를 가져온다.
    ```python
    URL = 'https://ajgkasentlasdj.aksgkas/agjh/'
    requests.get(URL)
    ```
- 

- `BeautifulSoup()`
    - get() 으로 가지고온 데이터를 parsing 하는 패키지
    - 어떤 형식인지 입력하면 다양한 메소드를 이용해 데이터 추출이 가능하게 한다
    ```python
    # data 변수에 get()을 통해 얻은 res변수의 text 부분만 html.parser로 파싱한 데이터를 저장한다
    data = BeautifulSoup(res.text, 'html.parser')
    ```

### API를 이용해 데이터를 추출하든, 개발자도구에서 selector를 알아내 특정 데이터를 추출하든 방법은 비슷하고, 데이터의 형식과 원하는 값이 있는 곳의 요소가 무엇인지 파악하는 것이 데이터 추출에 중요한 내용으로 보인다.


