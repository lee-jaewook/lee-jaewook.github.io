---
layout: article
title: 코딩 테스트, 파이썬 문법 정리
aside:
  toc: true
published : true
tags: coding-test
---
파이썬의 많은 문법 중 코딩 테스트에서 생산성을 높이기 위한 고급(?) 문법을 정리해 보도록 하겠습니다.  
(출처 : [파이썬 알고리즘 인터뷰](https://github.com/onlybooks/algorithm-interview#%ED%8C%8C%EC%9D%B4%EC%8D%AC-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-%EC%9D%B8%ED%84%B0%EB%B7%B0))
<!--more-->
# 네이밍 컨벤션
- 자바와 달리 파이썬에서의 네이밍 컨벤션은 스네이크 케이스를 따릅니다.
- 스네이크 케이스란, 각 단어를 밑줄(_)로 구분하여 표기하는 스네이크 케이스(Snake Case)를 따른다.
> 카멜 케이스, 스네이크 케이스  
> - 카멜 케이스  
> camelCase: int = 1
> - 스네이크 케이스  
> snake_case: int = 1

# 타입 힌트
- 파이썬은 동적 타이핑 언어임에도, 타입을 지정할 수 있는 타입 힌트가 추가됨
- 타입 힌트를 사용하면 가독성이 좋아지며 버그 발생 확률을 줄일 수 있음
- 사용 예시
```python
a: str = "1"
def fn(a: int) -> bool:
```
- 강제 규약이 아니기 때문에, 여전히 동적으로 할당될 수 있음  
> `mypy` 타입 힌트에 오류를 확일할 수 있는 라이브러리  
> `$ pip install mypy`

# 리스트 컴프리헨션
- 리스트 컴프리헨션 : 기존 리스트를 기반으로 새로운 리스트를 만들어내는 구문  
- 예시  
```python
[n * 2 for n in range(1, 10 + 1) if n % 2 == 1]
>>>[2, 6, 10, 14, 18]
```
- 리스트 컴프리헨션을 사용하지 않는 경우  
```python
a = []
for n in range(1, 10 + 1):
  if n % 2 == 1:
    a.append(n * 2)
print(a)
>>>[2, 6, 10, 14, 18]
```
- 번외로 딕셔너리도 가능하다.  
```python
a = {key: value for key, value in original.items()}
```
- 딕셔너리 컴프리헨션을 사용하지 않는 경우
```python
a = {}
for key, value in original.items():
  a[key] = value
```

# 제너레이터
- 제너레이터 : 루프의 반복 동작을 제어할 수 있는 루틴 형태
- `yield` 구문을 사용해 제너레이터를 리턴할 수 있다.
- 예시
```python
def get_natural_number():
  n = 0
  while True:
    n += 1
    yield n
```
```python
get_natural_number()
>>><generator object get_natural_number at ...>
```
```python
g=get_natural_number()
for _ in range(0, 100):
  print(next(g))
>>>1
>>>2
>>>3
>>>4
...
```

# range()
- 제너레이터의 방식을 활용하는 대표적인 함수가 range이다.
- 예시
```python
list(range(5))
>>>[0,1,2,3,4]
```
- for 문에서 사용할 경우 내부적으로 제너레이터의 next()를 호출하듯 매번 다음 숫자를 생성
  - 예시
  ```python
  for i in range(5):
    print(i)
  >>>0 1 2 3 4
  ```
- 값을 생성하는 것이 아리나, 생성해야 한다는 조건만 존재
- <mark>range가 실제 선언보다 메모리 점유율이 낮음</mark>
  - 예시
  ```python
  a = [n for n in range(1000000)] # 메모리 8697464
  b = range(1000000) # 메모리 48
  ```
  
# enumerate