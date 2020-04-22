---
title: First Post
image: /assets/img/stackpractice.jpg
date: 2020-04-22 08:26:28 -0400
categories: Practice Makes Perfect
---

프로그래머스 쇠파이프 문제:
문제 설명:
여러 개의 쇠막대기를 레이저로 절단하려고 합니다. 효율적인 작업을 위해서 쇠막대기를 아래에서 위로 겹쳐 놓고, 레이저를 위에서 수직으로 발사하여 쇠막대기들을 자릅니다. 쇠막대기와 레이저의 배치는 다음 조건을 만족합니다.


```python
def solution(arrangement):
    test = arrangement.replace('()','f')
    A = []
    answer = 0
    laser = 0
    for i in range(len(test)):
        if test[i] == '(':
            A.append(('(',i))
            laser = 0
        elif test[i] == ')':
            B = test[int(A[-1][1]):i]
            answer += B.count('f')+1
            A.pop()

    return answer
```
