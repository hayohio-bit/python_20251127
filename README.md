## 1. Python이란?

Python은 **간결하고 읽기 쉬운 문법**을 가진 고수준 프로그래밍 언어다.

### 핵심 특징

- **인터프리터 언어**: 컴파일 없이 즉시 실행
- **동적 타이핑**: 변수 타입을 선언하지 않음
- **들여쓰기로 코드 블록 구분**: 중괄호 대신 들여쓰기 사용
- **풍부한 표준 라이브러리**: 다양한 기능 내장
- **크로스 플랫폼**: Windows, Mac, Linux 모두 지원

### 주요 활용 분야

- 웹 개발 (Django, Flask)
- 데이터 분석 & 머신러닝 (Pandas, NumPy, TensorFlow)
- 자동화 스크립트
- API 개발
- DevOps 및 시스템 관리

---

## 2. 개발 환경 설정

### Python 설치

- [python.org](https://www.python.org/)에서 최신 버전 다운로드
- 설치 확인: `python --version` 또는 `python3 --version`

### 가상환경 (Virtual Environment)

```bash
# 가상환경 생성
python -m venv myenv

# 활성화 (Windows)
myenv\\Scripts\\activate

# 활성화 (Mac/Linux)
source myenv/bin/activate

# 비활성화
deactivate

```

### 패키지 관리 (pip)

```bash
# 패키지 설치
pip install 패키지명

# 설치된 패키지 목록
pip list

# requirements.txt로 일괄 설치
pip install -r requirements.txt

# requirements.txt 생성
pip freeze > requirements.txt

```

---

## 3. 기본 문법

### 변수와 출력

```python
# 변수 선언 (타입 선언 필요 없음)
name = "홍길동"
age = 25
height = 175.5
is_student = True

# 출력
print("Hello, World!")
print(f"이름: {name}, 나이: {age}")  # f-string (권장)
print("이름: {}, 나이: {}".format(name, age))  # format()
print("이름:", name, "나이:", age)  # 콤마로 구분

# 입력
user_input = input("이름을 입력하세요: ")  # 항상 문자열로 반환
age = int(input("나이를 입력하세요: "))  # 정수 변환

```

### 주석

```python
# 한 줄 주석

"""
여러 줄 주석
(Docstring으로도 사용)
"""

'''
작은 따옴표도 가능
'''

```

---

## 4. 데이터 타입

### 숫자 (Numbers)

```python
# 정수 (int)
a = 10
b = -5

# 실수 (float)
pi = 3.14159

# 산술 연산
print(10 + 3)   # 13 (덧셈)
print(10 - 3)   # 7 (뮨셈)
print(10 * 3)   # 30 (곱셈)
print(10 / 3)   # 3.333... (나눗셈)
print(10 // 3)  # 3 (몹)
print(10 % 3)   # 1 (나머지)
print(10 ** 3)  # 1000 (거듭제곱)

```

### 문자열 (String)

```python
# 문자열 생성
s1 = '작은 따옴표'
s2 = "큰 따옴표"
s3 = '''여러 줄
문자열'''

# 문자열 연산
print("Hello" + " " + "World")  # 연결
print("Hi" * 3)  # HiHiHi (반복)

# 인덱싱 & 슬라이싱
text = "Python"
print(text[0])      # 'P' (첫 글자)
print(text[-1])     # 'n' (마지막 글자)
print(text[0:3])    # 'Pyt' (슬라이싱)
print(text[::2])    # 'Pto' (두 글자씩)
print(text[::-1])   # 'nohtyP' (역순)

# 주요 문자열 메서드
print(len(text))           # 6 (길이)
print(text.upper())        # 'PYTHON'
print(text.lower())        # 'python'
print("  hi  ".strip())    # 'hi' (공백 제거)
print("a,b,c".split(","))  # ['a', 'b', 'c']
print("-".join(['a','b'])) # 'a-b'
print(text.replace('P', 'J'))  # 'Jython'
print('Py' in text)        # True (포함 여부)

```

### 리스트 (List)

```python
# 리스트 생성
fruits = ['사과', '바나나', '딸기']
numbers = [1, 2, 3, 4, 5]
mixed = [1, 'hello', True, 3.14]
empty = []

# 접근 & 수정
print(fruits[0])      # '사과'
fruits[0] = '포도'    # 수정 가능

# 주요 메서드
fruits.append('망고')      # 끝에 추가
fruits.insert(1, '오렌지')  # 특정 위치에 삽입
fruits.remove('바나나')    # 값으로 삭제
popped = fruits.pop()       # 마지막 요소 제거 및 반환
fruits.sort()               # 정렬
fruits.reverse()            # 역순
print(len(fruits))          # 길이

# 리스트 컴프리헨션
squares = [x**2 for x in range(5)]  # [0, 1, 4, 9, 16]
evens = [x for x in range(10) if x % 2 == 0]  # [0, 2, 4, 6, 8]

```

### 튜플 (Tuple)

```python
# 불변(immutable) 리스트
coords = (10, 20)
colors = ('red', 'green', 'blue')

# 언패킹
x, y = coords
print(x, y)  # 10 20

# 튜플은 수정 불가
# coords[0] = 5  # 에러!

```

### 딕셔너리 (Dictionary)

```python
# 키-값 쌍
person = {
    'name': '홍길동',
    'age': 25,
    'city': '서울'
}

# 접근 & 수정
print(person['name'])       # '홍길동'
print(person.get('email', 'N/A'))  # 없으면 기본값
person['age'] = 26          # 수정
person['email'] = 'a@b.com' # 추가

# 주요 메서드
print(person.keys())    # 모든 키
print(person.values())  # 모든 값
print(person.items())   # (key, value) 쌍
del person['city']      # 삭제

# 순회
for key, value in person.items():
    print(f"{key}: {value}")

```

### 세트 (Set)

```python
# 중복 없는 집합
numbers = {1, 2, 3, 3, 4}  # {1, 2, 3, 4}
a = {1, 2, 3}
b = {3, 4, 5}

# 집합 연산
print(a | b)  # {1, 2, 3, 4, 5} (합집합)
print(a & b)  # {3} (교집합)
print(a - b)  # {1, 2} (차집합)

# 메서드
numbers.add(5)       # 추가
numbers.remove(1)    # 삭제
numbers.discard(10)  # 없어도 에러 안남

```

---

## 5. 제어문

### 조건문 (if)

```python
age = 20

# 기본 조건문
if age >= 19:
    print("성인입니다")
elif age >= 13:
    print("청소년입니다")
else:
    print("어린이입니다")

# 비교 연산자
# ==, !=, <, >, <=, >=

# 논리 연산자
# and, or, not

if age >= 19 and age < 65:
    print("성인입니다")

# 삼항 연산자
result = "성인" if age >= 19 else "미성년"

```

### 반복문 (for)

```python
# 리스트 순회
fruits = ['사과', '바나나', '딸기']
for fruit in fruits:
    print(fruit)

# range() 사용
for i in range(5):        # 0, 1, 2, 3, 4
    print(i)

for i in range(1, 6):     # 1, 2, 3, 4, 5
    print(i)

for i in range(0, 10, 2): # 0, 2, 4, 6, 8 (스텝)
    print(i)

# enumerate() - 인덱스와 함께
for index, fruit in enumerate(fruits):
    print(f"{index}: {fruit}")

# 딕셔너리 순회
person = {'name': '홍길동', 'age': 25}
for key, value in person.items():
    print(f"{key}: {value}")

```

### 반복문 (while)

```python
count = 0
while count < 5:
    print(count)
    count += 1

# 무한 루프
while True:
    user_input = input("입력 (q=종료): ")
    if user_input == 'q':
        break
    print(f"입력값: {user_input}")

```

### break, continue, pass

```python
# break - 반복 중단
for i in range(10):
    if i == 5:
        break
    print(i)  # 0, 1, 2, 3, 4

# continue - 다음 반복으로
for i in range(5):
    if i == 2:
        continue
    print(i)  # 0, 1, 3, 4

# pass - 아무것도 하지 않음 (자리표시)
if True:
    pass  # 나중에 구현

```

---

## 6. 함수 (Function)

### 기본 함수

```python
# 함수 정의
def greet(name):
    return f"안녕하세요, {name}님!"

# 함수 호출
message = greet("홍길동")
print(message)

# 여러 값 반환
def get_info():
    return "홍길동", 25

name, age = get_info()

```

### 매개변수 종류

```python
# 기본값 매개변수
def greet(name, greeting="안녕하세요"):
    return f"{greeting}, {name}님!"

print(greet("홍길동"))  # 안녕하세요, 홍길동님!
print(greet("홍길동", "반갑습니다"))  # 반갑습니다, 홍길동님!

# 키워드 인수
def info(name, age):
    print(f"{name}, {age}세")

info(age=25, name="홍길동")  # 순서 상관없이

# 가변 인수 (*args)
def add_all(*args):
    return sum(args)

print(add_all(1, 2, 3, 4, 5))  # 15

# 키워드 가변 인수 (**kwargs)
def print_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_info(name="홍길동", age=25, city="서울")

```

### 람다 함수 (Lambda)

```python
# 간단한 한 줄 함수
add = lambda x, y: x + y
print(add(3, 5))  # 8

# 정렬에서 활용
students = [
    {'name': '홍길동', 'score': 85},
    {'name': '김철수', 'score': 92},
    {'name': '이영희', 'score': 78}
]

# 점수 기준 정렬
students.sort(key=lambda x: x['score'], reverse=True)

```

### 내장 함수

```python
# 자주 사용하는 내장 함수
print(len([1, 2, 3]))       # 3
print(type("hello"))        # <class 'str'>
print(range(5))             # range(0, 5)
print(list(range(5)))       # [0, 1, 2, 3, 4]
print(sum([1, 2, 3]))       # 6
print(max([1, 2, 3]))       # 3
print(min([1, 2, 3]))       # 1
print(abs(-5))              # 5
print(round(3.7))           # 4
print(sorted([3, 1, 2]))    # [1, 2, 3]
print(reversed([1, 2, 3]))  # 이터레이터
print(list(zip([1,2], ['a','b'])))  # [(1,'a'), (2,'b')]

# map, filter
numbers = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x**2, numbers))  # [1, 4, 9, 16, 25]
evens = list(filter(lambda x: x % 2 == 0, numbers))  # [2, 4]

```

---

## 7. 클래스와 객체지향 (OOP)

### 클래스 기본

```python
class Person:
    # 클래스 변수
    species = "Homo sapiens"

    # 생성자
    def __init__(self, name, age):
        # 인스턴스 변수
        self.name = name
        self.age = age

    # 인스턴스 메서드
    def greet(self):
        return f"안녕하세요, {self.name}입니다."

    def birthday(self):
        self.age += 1
        return f"{self.name}님, 생일 축하드립니다! ({self.age}세)"

# 객체 생성
person1 = Person("홍길동", 25)
person2 = Person("김철수", 30)

print(person1.greet())    # 안녕하세요, 홍길동입니다.
print(person1.birthday()) # 홍길동님, 생일 축하드립니다! (26세)

```

### 상속 (Inheritance)

```python
# 부모 클래스
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        pass

# 자식 클래스
class Dog(Animal):
    def speak(self):
        return f"{self.name}: 멍멍!"

class Cat(Animal):
    def speak(self):
        return f"{self.name}: 야옹~"

dog = Dog("바둑이")
cat = Cat("나비")

print(dog.speak())  # 바둱이: 멍멍!
print(cat.speak())  # 나비: 야옹~

```

### super()

```python
class Employee:
    def __init__(self, name, salary):
        self.name = name
        self.salary = salary

class Developer(Employee):
    def __init__(self, name, salary, language):
        super().__init__(name, salary)  # 부모 생성자 호출
        self.language = language

    def code(self):
        return f"{self.name}이(가) {self.language}로 코딩 중"

dev = Developer("홍길동", 5000, "Python")
print(dev.code())  # 홍길동이(가) Python으로 코딩 중

```

### 접근 제어자

```python
class MyClass:
    def __init__(self):
        self.public = "Public"        # 공개
        self._protected = "Protected" # 보호 (관례적)
        self.__private = "Private"    # 비공개

    def get_private(self):
        return self.__private

obj = MyClass()
print(obj.public)        # OK
print(obj._protected)    # OK (권장하지 않음)
# print(obj.__private)   # 에러!
print(obj.get_private()) # OK (getter로 접근)

```

### 특수 메서드 (Magic Methods)

```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __str__(self):
        return f"Point({self.x}, {self.y})"

    def __repr__(self):
        return f"Point({self.x}, {self.y})"

    def __add__(self, other):
        return Point(self.x + other.x, self.y + other.y)

    def __eq__(self, other):
        return self.x == other.x and self.y == other.y

p1 = Point(1, 2)
p2 = Point(3, 4)
p3 = p1 + p2  # __add__ 호출

print(p3)        # Point(4, 6)
print(p1 == p2)  # False

```

---

## 8. 예외 처리

```python
# 기본 예외 처리
try:
    result = 10 / 0
except ZeroDivisionError:
    print("0으로 나눌 수 없습니다")
except Exception as e:
    print(f"예외 발생: {e}")
else:
    print("성공!")
finally:
    print("항상 실행")

# 여러 예외 처리
try:
    num = int(input("숫자 입력: "))
    result = 100 / num
except (ValueError, ZeroDivisionError) as e:
    print(f"에러: {e}")

# 예외 발생시키기
def validate_age(age):
    if age < 0:
        raise ValueError("나이는 음수일 수 없습니다")
    return age

# 사용자 정의 예외
class CustomError(Exception):
    pass

```

---

## 9. 파일 처리

```python
# 파일 쓰기
with open('test.txt', 'w', encoding='utf-8') as f:
    f.write("안녕하세요\\n")
    f.write("파이썬 파일 처리\\n")

# 파일 읽기
with open('test.txt', 'r', encoding='utf-8') as f:
    content = f.read()       # 전체 읽기
    # lines = f.readlines()  # 리스트로 읽기
    # line = f.readline()    # 한 줄 읽기

print(content)

# 파일 모드
# 'r' - 읽기 (기본)
# 'w' - 쓰기 (덮어쓰기)
# 'a' - 추가
# 'x' - 생성 (이미 있으면 에러)
# 'b' - 바이너리 모드

# JSON 처리
import json

data = {'name': '홍길동', 'age': 25}

# JSON 쓰기
with open('data.json', 'w', encoding='utf-8') as f:
    json.dump(data, f, ensure_ascii=False, indent=2)

# JSON 읽기
with open('data.json', 'r', encoding='utf-8') as f:
    loaded = json.load(f)
    print(loaded)

```

---

## 10. 모듈과 import

```python
# 모듈 import
import math
print(math.sqrt(16))  # 4.0
print(math.pi)        # 3.14159...

# 특정 함수만 import
from math import sqrt, pi
print(sqrt(16))  # 4.0

# 별칭 사용
import numpy as np
import pandas as pd

# 모든 함수 import (비권장)
from math import *

```

### 자주 사용하는 표준 모듈

```python
# os - 운영체제 인터페이스
import os
print(os.getcwd())           # 현재 디렉토리
os.makedirs('new_dir', exist_ok=True)  # 폴더 생성
print(os.listdir('.'))       # 파일 목록

# datetime - 날짜/시간
from datetime import datetime, timedelta
now = datetime.now()
print(now.strftime('%Y-%m-%d %H:%M:%S'))
yesterday = now - timedelta(days=1)

# random - 랜덤
import random
print(random.randint(1, 10))     # 1~10 정수
print(random.choice(['a','b']))  # 랜덤 선택
print(random.random())           # 0~1 실수

# re - 정규표현식
import re
text = "Email: test@example.com"
match = re.search(r'[\\w.-]+@[\\w.-]+', text)
if match:
    print(match.group())  # test@example.com

# collections
from collections import Counter, defaultdict
counter = Counter(['a', 'b', 'a', 'c', 'a'])
print(counter)  # Counter({'a': 3, 'b': 1, 'c': 1})

```

---

## 11. 주요 외부 라이브러리

### requests - HTTP 요청

```python
import requests

# GET 요청
response = requests.get('<https://api.example.com/data>')
print(response.status_code)  # 200
data = response.json()       # JSON 파싱

# POST 요청
response = requests.post(
    '<https://api.example.com/users>',
    json={'name': '홍길동', 'age': 25},
    headers={'Authorization': 'Bearer token'}
)

```

### pandas - 데이터 분석

```python
import pandas as pd

# DataFrame 생성
df = pd.DataFrame({
    'name': ['홍길동', '김철수', '이영희'],
    'age': [25, 30, 28],
    'city': ['서울', '부산', '대구']
})

# 기본 연산
print(df.head())        # 상위 5행
print(df.describe())    # 통계
print(df['age'].mean()) # 평균

# 필터링
seoul = df[df['city'] == '서울']

# CSV 읽기/쓰기
df.to_csv('data.csv', index=False, encoding='utf-8-sig')
df = pd.read_csv('data.csv')

```

### numpy - 수치 연산

```python
import numpy as np

# 배열 생성
arr = np.array([1, 2, 3, 4, 5])
zeros = np.zeros((3, 3))
ones = np.ones((2, 4))

# 연산
print(arr * 2)      # [2, 4, 6, 8, 10]
print(arr.mean())   # 3.0
print(arr.sum())    # 15

```

---

## 12. 데코레이터 (Decorator)

```python
# 기본 데코레이터
def timer(func):
    import time
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()
        print(f"{func.__name__} 실행 시간: {end-start:.4f}초")
        return result
    return wrapper

@timer
def slow_function():
    import time
    time.sleep(1)
    return "완료"

result = slow_function()  # slow_function 실행 시간: 1.0001초

```

---

## 13. 제너레이터 (Generator)

```python
# yield를 사용한 제너레이터
def number_generator(n):
    for i in range(n):
        yield i * 2

# 사용
gen = number_generator(5)
for num in gen:
    print(num)  # 0, 2, 4, 6, 8

# 제너레이터 표현식
squares = (x**2 for x in range(10))

```

---

## 14. 유용한 팁

### Type Hints (타입 힌트)

```python
def greet(name: str, age: int) -> str:
    return f"{name}님, {age}세"

from typing import List, Dict, Optional

def process(items: List[int]) -> Dict[str, int]:
    return {'sum': sum(items), 'count': len(items)}

def find(name: Optional[str] = None) -> str:
    return name or "Anonymous"

```

### 주의사항 & Best Practices

- **PEP 8** 스타일 가이드 준수
- 변수/함수명: `snake_case`
- 클래스명: `PascalCase`
- 상수: `UPPER_CASE`
- 들여쓰기: 스페이스 4칸
- 가능하면 `with`문 사용 (파일, 연결 등)
- 리스트 컴프리헨션 적극 활용
- `f-string` 사용 (포맷팅)

---

## 15. 유용한 라이브러리 목록

| 라이브러리 | 용도 |
| --- | --- |
| `requests` | HTTP 요청 |
| `pandas` | 데이터 분석 |
| `numpy` | 수치 연산 |
| `matplotlib` | 데이터 시각화 |
| `flask` | 경량 웹 프레임워크 |
| `django` | 풀스택 웹 프레임워크 |
| `selenium` | 웹 자동화 |
| `beautifulsoup4` | HTML 파싱 |
| `pytest` | 테스트 |
| `fastapi` | 빠른 API 개발 |

---

## 16. 참고 자료

- [Python 공식 문서](https://docs.python.org/ko/3/)
- [Real Python](https://realpython.com/)
- [Python 튜토리얼](https://docs.python.org/ko/3/tutorial/)
