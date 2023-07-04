## collections라이브러리 deque활용
  
Python에서 deque는 "double-ended queue"의 줄임말로, 양쪽 끝에서 삽입과 삭제가 모두 가능한 자료구조를 말합니다. 이는 collections 모듈에 포함되어 있습니다.
deque는 효율적인 메모리 사용과 빠른 연산 속도를 제공하기 때문에, 큐(queue)나 스택(stack)을 필요로 하는 알고리즘 문제를 해결할 때 많이 사용됩니다.
deque는 다음과 같은 주요 메서드들을 가집니다:

활용)
append(x): 오른쪽 끝에 항목 x를 추가합니다.
appendleft(x): 왼쪽 끝에 항목 x를 추가합니다.
pop(): 오른쪽 끝에 있는 항목을 제거하고 반환합니다.
popleft(): 왼쪽 끝에 있는 항목을 제거하고 반환합니다.
rotate(n): n이 양수면 오른쪽으로, n이 음수면 왼쪽으로 n만큼 데크를 회전시킵니다.
이러한 특징들로 인해 deque는 효율적인 자료구조로서 다양한 상황에서 활용됩니다.


백준 1021번 답안
```python
from collections import deque

# 입력
N, M = map(int, input().split())
pick = list(map(int, input().split()))

# 1부터 N까지의 숫자를 큐에 저장
queue = deque(range(1, N+1))

# 이동 횟수
count = 0

for num in pick:
    # 큐에서 num의 인덱스를 찾는다.
    index = queue.index(num)

    # 왼쪽으로 이동하는 경우와 오른쪽으로 이동하는 경우 중 작은 횟수를 선택한다.
    # 큐의 길이의 절반을 넘어서는 경우 반대 방향으로 이동하는 것이 더 효율적이다.
    if index > len(queue) // 2:
        count += len(queue) - index
        queue.rotate(len(queue) - index)  # num을 맨 앞으로 이동
    else:
        count += index
        queue.rotate(-index)  # num을 맨 앞으로 이동

    # 첫 번째 원소를 뽑는다.
    queue.popleft()

# 결과 출력
print(count)
```

간략화
```python
from collections import deque

N, M = map(int, input().split())
queue = deque(range(1, N+1))

count = sum(min(queue.index(num), len(queue) - queue.index(num)) + (queue.rotate(-queue.index(num)) or queue.popleft()) for num in map(int, input().split()))

print(count)

```

deque를 이용해 손쉽게 문제를 해결함.
