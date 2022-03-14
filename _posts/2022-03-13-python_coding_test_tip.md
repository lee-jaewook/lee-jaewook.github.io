---
layout: article
title: 파이썬 코딩 테스트 팁 정리
aside:
  toc: true
published : false
---

# 네이밍 컨벤션
- 자바와 달리 각 단어를 밑줄(_)로 구분하여 표기하는 스네이크 케이스(Snake Case)를 따른다.
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
