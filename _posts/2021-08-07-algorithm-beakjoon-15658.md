---
title: "백준 15658 python"
categories:
  - "algorithm"

tag:
  - "백트래킹"
  - "재귀"
  - "구현"
---

[백준 링크](https://www.acmicpc.net/problem/15658)

백트래킹을 많이 푼 경험이 있다보니 문제내용을 보니까
백트래킹으로 풀어야 되는지 알수있어졌다.

## 접근 방법

집합을 이용해서 주어진 부호들을 N - 1 만큼 뽑은다음에
뽑은 것으로 주어진 A 배열에 계산하면 된다.

이렇게 글로써 보니 참 간단하다.

### 코드

```python
N = int(input())

arr = list(map(int, input().split()))

nums = list(map(int, input().split()))


def fun2(s):
    if s == 0:
        return "+"
    elif s == 1:
        return "-"
    elif s == 2:
        return "*"
    elif s == 3:
        return "/"


def fun3(v):
    _sum = arr[0]
    for i in range(1, len(arr)):
        if v[i - 1] == "+":
            _sum += arr[i]
        elif v[i - 1] == "-":
            _sum -= arr[i]
        elif v[i - 1] == "*":
            _sum *= arr[i]
        elif v[i - 1] == "/":
            if _sum < 0:
                _sum = (abs(_sum) // arr[i]) * -1
            else:
                _sum = _sum // arr[i]

    return _sum


_max = (10**9 + 1) * -1
_min = 10**9 + 1


def fun(v, c):
    global _max, _min
    if c == N - 1:
        _max = max(fun3(v), _max)
        _min = min(fun3(v), _min)
        return

    for i in range(4):
        if nums[i]:
            nums[i] -= 1
            t = v + fun2(i)
            fun(t, c + 1)
            nums[i] += 1


fun("", 0)

print(_max)
print(_min)

```

내가 짠 코드인데 아까 틀려서 좀 코드를 고쳤는데 왜 틀렸냐면

\_max, \_min 변수에 초기값을 각각 1억- 1억으로 줬다.

귀찮아서 확인도 안하고 그냥 주니까 틀려서
코드를 살펴보니 10억이 안된것을 확인하고
허무한 기분으로 코드를 고쳤더니 맞았다.

하지만 이코드는 다른 코드에 비해 너무 느리다.

시간이 **1520ms** 가 나온다.

그래서 다른 답도 봤는데

[다른 답](https://it-sunny-333.tistory.com/28)

```python
N = int(input())
a = list(map(int,input().split()))
cnt = list(map(int,input().split()))
max_ans = -1000000000
min_ans = 1000000000

def dfs(idx, ans):
    global max_ans,min_ans

    if idx == N:
        max_ans = max(max_ans, ans)
        min_ans = min(min_ans, ans)
        return

    if cnt[0] > 0:
        cnt[0] -= 1
        dfs(idx+1, ans+a[idx])
        cnt[0] += 1
    if cnt[1] > 0:
        cnt[1] -= 1
        dfs(idx+1, ans-a[idx])
        cnt[1] += 1
    if cnt[2] > 0:
        cnt[2] -= 1
        dfs(idx+1, ans*a[idx])
        cnt[2] += 1
    if cnt[3] > 0:
        cnt[3] -= 1
        dfs(idx+1, int(ans/a[idx]))
        cnt[3] += 1

dfs(1,a[0])
print(max_ans)
print(min_ans)
```

내 코드와 저 코드의 차이점은
나의 코드는 fun 함수에서 숫자를 다뽑고 계산을 하지만
저 코드는 숫자를 계산해 가면서 뽑는다.

저렇게 보니 나는 아직 아닌거같다.

이 코드로 제출하니 **시간이 296ms** 가 나온다.

아까보단 훨씬 좋아졌다.

하지만 1등의 시간이 **156ms** 였다.

나는 만족 못한다.

```python
from sys import stdin
def go(num, plus, sub, mul, div, i=1) :
    global min_, max_
    if i == N :
        if min_ > num :
            min_ = num
        if max_ < num :
            max_ = num
        return True
    next = numbers[i]
    if plus >0 :
        go(num+next, plus-1, sub, mul, div, i+1)
    if sub >0  :
        go(num-next, plus, sub-1, mul, div, i+1)
    if mul >0 :
        go(num*next, plus, sub, mul-1, div, i+1)
    if div >0 :
        go(int(num/next), plus, sub, mul, div-1, i+1)

N = int(stdin.readline())
numbers = list(map(int, stdin.readline().split()))
plus, sub, mul, div = list(map(int, stdin.readline().split()))

min_ = (10 ** 9) +1
max_ = min_*-1
go(numbers[0], plus, sub, mul, div)

print(max_)
print(min_)
```

코드를 보니 웃음만 나온다.

매게변수로 부호 배열에 숫자를 관리 할줄이야
매일 매일 알고리즘 답을 보면 느끼는 거지만
정답은 많고 빠른 정답은 놀랍다.
