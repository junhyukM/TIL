# Python 의 기본적인 지식과 문법 학습

## python 언어를 작성 시 주의 사항

    이 예시들은 서로 다른 변수를 나타냄
1. apple / Apple   
    - 대소문자가 다르면 다른 변수로 생각
2. git add. / git add .  
    - 띄어쓰기가 다르면 동작하지 않음
3. message / massage  
    - 오타일 경우 당연하게도 동일한 변수로 인식하지 않음

---
## python 언어의 변수의 기초적인 내용


### **변수, variable**
```python
# dust를 변수로 10 이라는 숫자 저장
dust = 10
# dust를 변수로 '10' 이라는 문자 저장
dust = '10'
#greeting 을 변수로 'hello' 라는 문자 저장
greeting = 'hello'

# 1
status = True
# 0
status = False

# 리스트
dust_list = [10, 20, 20, 15, 100, 150]
# 리스트 [10, 20, 20, 15, 100, 150] 출력
print(dust_list)
# 리스트의 데이터 중 0번째 자리에 있는 데이터 출력 -> 10
print(dust_list[0])

# 딕셔너리
dust_dict = {
    '서울': 100,
    '대전': 50,
    '부산': 10
}
# 딕셔너리 key 와 value가 쌍으로 묶여 출력
print(dust_dict)
# key 값이 '서울'인 데이터의 value가 출력 -> 100
print(dust_dict['서울'])

# 셋 set()
# 로또 번호 당첨 체크할 때 사용했던 자료형

num = [1, 2, 3, 4, 5]

set_num = set(num)
print(set_num)
```

## 위와 같이 변수에는 숫자형, 문자형, True / False, 리스트, 딕셔너리의 형태로 저장될 수 있다.

---
### **조건문**
```python
# age 변수에 10을 저장하고 if 우측에 작성된 조건을 참으로 만족한다면 밑에 있는 코드를 수행하는 조건문
age = 10

if age > 20:
    print('성인입니다')
elif age > 8:
    print('청소년입니다')
else:
    print('어린이입니다')
```
> 조건문을 사용하는 이유는 조건을 기준으로 다른 결과를 얻고 싶을 때 사용.

### **반복**
```python
# 리스트 데이터가 저장된 menus 변수를 반복적, 순서대로 print 하게 하는 반복문
menus = ['짜장면', '국밥', '김밥', '라면', '피자']
# while 문 이용
n = 0
while n < 2:
    print(menus[n])
    n += 1

# for 문 이용
for menu in menus:
    print(menu)
```    
> 반복문을 사용하는 이유는 특정 동작을 반복을 통해 원하는 볼륨 만큼의 결과를 얻고 싶을 때 사용.


---
강의 수강하며 작성한 python 파일은 [github python](https://github.com/junhyukM/python/blob/master/basic.py)에 업로드 되어 있음