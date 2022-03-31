---
layout: article
title: 이진 탐색(Binary Search) by 파이썬  
aside:
  toc: true
tags: algorithm
published : true
---

# 알고리즘 설명
이진 탐색은 가장 보편적으로 사용되는 탐색 알고리즘 중 하나입니다. 이진 탐색은 정렬된 배열에 적용될 수 있으며 빠른 탐색 알고리즘 중 하나입니다. 이진 탐색은 매 iteration 마다 탐색 공간을 반으로 나눠가는 알고리즘 입니다(자세한 설명은 [이 글](https://www.code-recipe.com/post/binary-search)을 참고하세요).
<!--more-->

# 구현
```python
def binary_search(arr: list, x: int) -> int:
    left = 0
    right = len(arr) - 1
    while right >= left:
        mid = (left + right) // 2
        if x == arr[mid]:
            return mid
        elif x < arr[mid]:
            right = mid - 1
        else:
            left = mid + 1
    return -1
```

