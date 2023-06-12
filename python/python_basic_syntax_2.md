**변수**
- 변수이름 = 값
- 변수이름은 어떤 이름이든 상관 없음
- 단, 영어, 숫자, _(언더바)로 구성되어있고 키워드는 사용 불가

**String (문자열)**
- String 입력 시 ' 입력 등을 위해 사용 `\`
- intro = '안녕하세요 저는 `\`'홍길동`\`'입니다.'
> 안녕하세요 저는 '홍길동'입니다.
- `docstring`
    - 함수에 대한 설명을 작성한다던가 할 때 사용
    - """  """ 로 텍스트를 감싸면 줄바꿈 등이 다 인식된 텍스트 형태로 작성 가능
```python
#docstring
intro = """
안녕하세요
저는 홍길동입니다.
"""
```

- string interpolation
    - string의 중간에 변수의 값을 유동적으로 작성하고 싶을 때 사용하면 유용
    - 보통 .fomat() 과 f''{}을 많이 사용
```python
dust = 100
message = '오늘 미세먼지 농도는 10입니다.'
message1 = '오늘 미세먼지 농도는 %s입니다.' % dust
message2 = '오늘 미세먼지 농도는 {}입니다.'.format(dust)
message3 = f'오늘 미세먼지 농도는 {dust}입니다.'
```


**형변환**
- 명시적 형변환
```python
# 형변환이 필요한 변수를 원하는 자료형으로 변환한다.
print('미세먼지 농도 : ' + str(10))
print(10 + int('20'))
print(float('3.4'))
print(float(2))
print(int('2.5'))
```

**시퀀스 데이터**

1. 리스트(list) 
2. 튜플(tuple) 
3. 레인지(range) 
4. 문자열(string)

리스트
- 리스트 안에 다양한 형태
- 한 줄에 하나의 데이터를 작성
```
a = [
    [1, 2, 3],
    {4, 5, 6},
    (7, 8, 9),
] 
```
> 마지막까지 `,` 사용하는 것 주의

튜플
- 수정불가능(immutable)
- a = (value1, value2...)
- a[index]
```python
# 아래와 같이 수정을 하려고 하면 에러가 난다.
a = (1, 2, 3, 4, 5)
a[1] = 10  
```
- 튜플을 이용한 예시에서 정리한 내용
    - (b, c) = (1, 2)
    - 1이 b에 들어가고 2가 c에 들어감


함수
```python
# 같은 어떤 기능을 하는 함수라고 생각했는데, 하나는 그냥 내장함수고 하나는 메소드
# 특정 자료형 안에 내장된 함수를 메소드라고 하는데, 객체 관련 학습시 더 자세히 학습 가능
a = [1, 2, 1, 4, 5]
print(len(a))
print(a.count(1))
```

**시퀀스가 아닌 자료**

set
- a = {value1, value2, ...}
- 순서가 없고 중복이 없음
```python
# 5를 중복으로 작성해도 출력하면 하나만 나옴
a = {1, 2, 3, 4, 5, 5} 
b = {2, 4, 6, 8}
```

- 합집합
```
print(a | b)
```
- 차집합
```
print(a - b)
```
- 교집합
```
print(a & b)
```

## 중복 데이터 날리고 list로 다시 바꾸기
```python
a = [1, 2, 3, 4, 5, 1, 2, 3, 4, 5]
print(list(set(a)))
```
dictionary
- a = {key1: value1, key2: value2, ...}
- key는 immutable한 것만 가능

- 뒤에 있는 key의 value가 덮어쓴다
```python
# 1 key 에 value를 두번 입력했으므로 뒤에 입력한 4가 1 key의 value가 된다.
b = {1: 1, 2: 2, 3: 3, 1: 4}
print(b[1])
print(b)
print(b.keys())
print(b.values())
```

**제어문**

조건문
```
if <조건식>:
    if의 조건식이 참인경우 실행하는 코드
elif <조건식>:
    elif의 조건식이 참인경우 실행하는 코드
else:
    거짓인 경우 실행하는 코드
```

> 연습2<br>
> 사용자에게 숫자하나를 입력 받아서 홀수인지 짝수인지 확인하는 코드
```python
a = int(input('숫자를 하나 입력해주세요 : '))
# a % 2 가 1의 값을 가져 True로 인식이 되었다는 것 인지
if a % 2:
    print('홀수입니다.')
else:
    print('짝수입니다.')
```

조건표현식
- true_value if <조건식> else false_value

> 홀수, 짝수 판별
```python 
num = int(input('숫자를 입력하세요 : '))
# true_value 혹은 false_value 값을 result 변수에 저장
result = '홀수' if num % 2 else '짝수'
print(result)
```

반복문

- while
    - while 조건식이 True인 경우 반복적으로 코드를 실행
```
while <조건식>:
    반복할 코드
```

- for
```
for variable in sequence:
    실행할 코드
```

> 연습1<br>
> 사용자에게 영단어 하나를 받아서 알파벳 하나씩 출력 시키는 코드
```python 
word = input('단어를 입려해주세요 : ')
for i in word:
    print(i)
```
```python
# 표현시 numbers 와같이 복수형으로 작성해서 for 문에 사용하는것이 보통이다.
# 외부에서 사용하는 변수와 for 문의 variable 변수를 같은 이름으로 쓰면 안된다. 외부에 있는 변수가 바뀌어버린다.
# 아래와 같이 기입하면 numbers 가 마지막으로 for문을 돌며 저장된 5 라고 출력이 된다.
number = 123
numbers = [1, 2, 3, 4, 5]
for number in numbers:
    print(number)
print(number)
```


> 연습3<br>
> 점심메뉴 리스트를 작성해서 하나씩 출력
```python
menus = ['라면', '김밥', '돈까스', '삼겹살']

for i in range(len(menus)):
    print(menus[i])
# enumerate 는 menus의 요소들의 인덱스와 value를 튜플형으로 반환해주는 함수
for idx, menu in enumerate(menus):
    # enumerate를 거치면 아래와 같이 데이터들이 뽑히고 print()에 출력된다.
    # idx, menu = (0, '라면')
    # idx, menu = (1, '김밥')
    # idx, menu = (2, '돈까스')
    # idx, menu = (3, '삼겹살')
    print(idx, menu)
```
















