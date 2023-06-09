
## lambda<br>
lambda parameter: expression(표현식, 코드)
```python
# 그냥 선언된 함수
def my_sum(a, b):
    return a + b
result = my_sum(1, 5)
print(result)
# lambda 를 사용해 익명함수 생성, 바로 호출
print((lambda a, b: a + b)(1, 2))
```
- 다른예시
```python
# 함수의 return에 lambda 함수 사용
def make_incrementor(n):
    return lambda x: x + n

# 변수에 함수 저장
f = make_incrementor(42)
# 아래와 같은 의미나 마찬가지
f = lambda x: x + 42
# 아래와 같은 느낌
def f(x):
    return x + 42

print(f(100))
```


이름공간 및 스코프(scope)
> LEGB <br>
> 1번부터 우선순위
1. Local : 정의된 함수 내부
    - 함수가 실행된 시점 이후부터 리턴 할 때 까지 존재
2. Enclosed : 상위 함수 (람다 때 참고)
    - 함수가 실행된 시점 이후부터 리턴 할 때 까지 존재
3. Global : 함수 밖 or import 된 모듈
    - 모듈이 호출된 시점 이후 끝까지 존재
4. Built-in : 파이썬에 내장되어있는 함수 혹은 변수
    - 파이썬이 실행된 이후 끝까지 존재

```python
# 기존의 함수와 같은 이름으로 변수를 만들어 보면 문제가 생긴다.

# Local scope 에서 print를 변수로 저장했기 때문이다.
print = 'hello'
# 에러 발생
print(print)
```
- 전역변수
```python
# 전역변수 건드린다.
# 아래와 같이 하면 전역 변수가 수정이 일어난다.
global_a = 1
def localscope2():
    # 함수 외부에 있는 전역변수를 가져와 사용하게 만든다
    global global_a
    global_a = 2
    print(global_a)

localscope2()
print(global_a)
```


재귀 함수 (recursive function)

- 팩토리얼 반복문으로 만들기
```python
def fact(n):
    #1부터 n까지의 수를 곱하기
    result = 1
    for i in range(1, n+1):
        result *= i
    return result    
print(fact(5))
```

- 팩토리얼 재귀함수를 사용해 만들기
```
f(3)
3 * f(2)
3 * 2 * f(1)
3 * 2 * 1
3 * 2
6

팩토리얼 함수 안에서 다시 팩토리얼 함수를 return
함수안에 함수안에 함수안에 함수안에 함수안에 함수안에 함수안에 ...
```
```python
def factorial(n):
    if n <= 1:
        return n
    else:
        return n * factorial(n-1)

print(factorial(5))
```

- 피보나치 수열 반복문으로 만들기
```python
def fib(n):
    # 시작점으로 1, 1이 들어있는 리스트를 만들기
    result = [1, 1]
    for i in range(1, n):
        # 리스트의 마지막 요소
        end1 = result[-1]
        # 리스트의 뒤에서 두번째 요소
        end2 = result[len(result) - 2]
        # 두개를 더해 하나의 값을 얻어
        fib_num = end1 + end2
        # result 리스트에 append()
        result.append(fib_num)
    # result 리스트의 마지막 요소 return
    return result[-1]

print(fib(1000))
```

- 피보나치 수열 재귀
```python 
def fib(n):
    # n이 1이거나 0이면 1 return
    if n == 1 or n == 0:
        return 1
    # n-1 과 n-2 의 합 -> 전에 것과 전전에 것을 합치기
    """재귀적으로 입력한 n 이 1 또는 0이 될 때까지 n-1, n-2를
    계산해가며 줄어들다가 if 조건문이 참이 되는 시점에 1을 
    return 하고 마무리"""    
    else:
        return fib(n-1) + fib(n-2)
   
print(fib(10))
```

## 문자열 메소드


- .join(iterable : 반복가능한 개체, 시퀀스 데이터)
```python
a = ['hi', 'my', 'name']
print(', '.join(a))
```

- .replace(old, new[, count])
```python
# 대괄호는 옵셔널하다 -> 넣어도 되고 안넣어도 된다
print('wooooooow'.replace('o', '!', 3))
```

- .strip([chars])
```python
str_l = '            hello\n'
str_r = 'hellohihihihi'
print(str_l.strip())
left strip
print(str_l.lstrip())
right strip
print(str_r.rstrip('hi'))
```

- .find(x)
```python
a = 'apple'
print(a.find('p'))
print(a.find('z'))
```

- .index(x)
```python
a = 'apple'
print(a.index('a'))
find 는 에러 발생 X index는 없으면 에러발생
print(a.index('z'))
```

- .split(x)
```python
a = 'my_name_is_junhyuk'
print(a.split('_'))
```

- .isXXX => True, False를 리턴한다.


## 리스트 메소드 -> 리스트는 뮤터블한 데이터 이므로 메소드를 적용시 데이터가 바뀐다

- .remove(x)
```python
numbers.remove(3.5)
print(numbers)
# 이미 지워서 없는데 또 지우라고 하면 에러 발생
# 최초로 발견된 인덱스의 요소만 제거
numbers.remove(3.5)
```

- .pop(i) -> index
```python
numbers.pop(0)
print(numbers)
```

- .sort()
```python
numbers.sort()
print(numbers)
# 속성에 resverse = True 면 정렬 기준이 반대로 바뀐다
numbers.sort(reverse=True)
print(numbers)
```

- .reverse()
```
# 거울 같이 대칭으로 만들어 줌
numbers.reverse()
print(numbers)
```

### copy
같은 주소를 참조한다. <br>
리스트 자료구조에 해당하는 내용 변수나 다른 자료구조들에 해당되는 내용 아니다.
```python
# origin_list 와 copy_list가 같은 주소를 참조하고 있다는 것을 확인 할 수 있다.
origin_list = [1, 2, 3]
copy_list = origin_list

copy_list[0] = 100

print(origin_list)
print(copy_list)
print(id(origin_list))
print(id(copy_list))
```

- copy 복사 방법
- 슬라이싱
```python
# 복사라기 보다는 같은 내용으로 새로운 자료를 만든다고 보는게 맞을것 같다.
a = [1, 2, 3]
b = a[ : ]
# b = list(a) 라고 표현해도 된다.

b[0] = 100

print(a)
print(b)
```

- copy 얕은복사
```python
# 리스트가 중첩되었을 때에
a = [1, 2, [3, 4]]
# 슬라이싱의 방법을 사용해도
b = a[:]

b[2][0] = 100

# 같은 주소를 참조하게 된다.
print(a)
print(b)
```

-copy 깊은복사
```python
# copy 라이브러리의 .deepcopy 메소드를 사용해서 복사하면 깊은 복사가 일어난다.
import copy
a = [1, 2, [3, 4]]
b = copy.deepcopy(a)

b[2][0] = 100

# 서로 다른 주소를 참조하고 있는 것을 확인 가능
print(a)
print(b)
```

- .clear()
```python
a = [1, 2, 3, 4]
# 빈 리스트로 깨끗해진다
a.clear()
print(a)
```

## list comprehension

```python
numbers = list(range(1, 11))

# 세제곱 만들기 for
result = []
for i in numbers:
    result.append(i**3)

print(result)
```
```python
# 세제곱 만들기 comp
# [code... for i in numbers]
result2 = [i**3 for i in numbers]
print(result2)
```
```python
# 짝수만 고르기 for
even_list = []
for i in numbers:
    if i % 2 == 0:
        even_list.append(i)
print(even_list)
```
```python
# 짝수만 고르기 comp
# [여기에 넣어 for i in numbers 만약~ 하면]
even_list2 = [i for i in numbers if i % 2 == 0]
print(even_list2)
```


- 모음을 제거
```
words = 'my name is Min'
vowels = 'aeiou'
```
```python
# 반복문 버전
result = []
for c in words:
    if c not in vowels:
        result.append(c)
        
print(''.join(result))
```
```python
# comp 버전
# [] 안에 for c in words 작성 후 조건은 오른쪽에 왼쪽엔 뭘 반환할지 작성
result2 = [c for c in words if c not in vowels]
print(''.join(result2))
```

## 딕셔너리 메소드

```python
info = {
    'name': 'Min',
    'location': 'incheon',
    'phone': '123-123-123'
}
```

- .pop(key[, default])
```python
info.pop('phone')
print(info)
print(info.pop('school', 'key가 없습니다.'))
print(info)
```

- .update(key=value)
```python
info.update(name='junhyuk')
print(info)
```

- .get(key[, default])
```python 
print(info['name'])
print(info.get('name'))
print(info['school'])
print(info.get('school'))
```

## dictionary comprehension
```python 
# 이와 같은 결과물 원해요 {1: 1, 2: 8, 3: 27}
cube_dict = {}
for i in range(1, 4):
    cube_dict[i] = i**3
print(cube_dict)
              #리스트와 비슷하게 왼쪽에 들어가는 값을 쓰는데, key: value 순으로 작성하면 된다
cube_dict2 = {i: i**3 for i in range(1, 4)}
print(cube_dict2)
```

- 연습
```python 
dust = {
    '서울': 100,
    '대전': 12,
    '인천': 70,
    '부산': 34,
    '전주': 67,
}
```

- 50 이상 지역만 뽑아서 새로운 dict 만들기
```python 
# for
l_dict = {}
for l, d in dust.items():
    if d >= 50:
        l_dict[l] = d
print(l_dict)        
```
```python 
# comp
# 똑같다 왼쪽은 결론 오른쪽은 조건 
l_dict2 = {l: d for l, d in dust.items() if d >= 50}
print(l_dict2)
# 그런데.. 2가지 조건을 동시에 만족하는 것을 기입할 때는 value 자리에 이렇게 조건문으로 작성하는 경우도 있다
result3 = {k: '나쁨' if v >= 50 else '좋음' for k, v in dust.items()}
print(result3)
```

## 세트 메소드
```python 
fruits = {'apple', 'banana', 'melon'}
```

- .add(x)
```python 
fruits.add('watermelon')
print(fruits)
```

- .update(*objects)
```python 
fruits.update('grape')
fruits.update({'orange', 'pear'})
print(fruits)
```

- .remove(x)
```python 
fruits.remove('banana')
print(fruits)
없을 때 제거하려면 에러 
fruits.remove('dog')
```

- .discard(x)]
```python 
없어도 에러 안뜸
fruits.discard('dof')
print(fruits)
```

- .pop()
```python 
임의의 원소 제거
fruits.pop()
print(fruits)
```


## map(), zip(), filter()

- map(function, iterable 데이터)
```python 
number = [1, 2, 3]

number_str = map(str, number)
print(number_str)
print(list(number_str))

def cube(x):
    return x**3

# cube_list는 map 함수를 사용해 cube 함수를 number 이터레이블 데이터에 각각 적용한 값이 들어간 리스트다.
cube_list = list(map(cube, number))
print(cube_list)
```

- 아래와 같은 결과를 얻고 싶다
```python 
# 1 2 3 4 5 6 7 8 9 10 => [1, 2, 3, 4, 5...]
# => 1 8 27 ... 1000
```
```python 
# input() 사용할 때, 여러 값을 띄어쓰기로 구분해서 입력을 할 일이 생기고, 입력하는 데이터가 숫자일 경우 split과 int, map 함수를 이용하여 숫자로 이루어진 리스트를 입력하는 코드. 알고리즘 테스트할때 자주 사용하는 코드임
numbers = input().split()
result = map(int, numbers)
print(list(result))

numbers = list(map(int, input().split()))
print(list(numbers))
```

- zip
```python 
a_number = [1, 2, 3]
b_number = [100, 200, 300]

# 같은 인덱스에 대응되는 데이터끼리 묶어서 반환해줌
print(list(zip(a_number, b_number)))
```


- filter(function, iterable)
```python 
# function은 참/거짓이 반환되는 함수여야 한다.
# filter를 거친 결과는 참의 경우인 요소들로 이루어진 리스트
def isodd(x):
    if x % 2 == 1:
        return True
    else:
        return False
    return bool(x % 2) 

numbers = [1, 2, 3, 4, 5]
result = filter(isodd, numbers)
print(list(result))
```