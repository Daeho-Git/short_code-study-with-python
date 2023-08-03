## Basic Stack Implementation
  
 > 스택(Stack)은 데이터 구조 중 하나로, 먼저 들어간 요소가 나중에 나오는 LIFO(Last-In-First-Out) 특성을 가지고 있습니다.
그러나 python에서는 기본적인 데이터구조를 list를 이용해서 너무 쉽게 구현 가능함.

구성요소를 까먹는게 아니라면 그다지 어렵지 않게 즉석으로 구현이 가능함.
 #### python에서는 collections의 deque를 이용해 구현하지 않고 이용이 가능(참고)
 ####  'queue' 모듈에는 'LifoQueue'라는 클래스가 존재함(스레드 간 안전한 스택 구현을 제공합니다.)

기본적인 class구현.
```python
class Stack:
    def __init__(self):
        self.stack = []

    def isEmpty(self):
        return len(self.stack) == 0

    def push(self, data):
        self.stack.append(data)

    def pop(self):
        if self.isEmpty():
            return None
        else:
            return self.stack.pop()

    def peek(self):
        if self.isEmpty():
            return None
        else:
            return self.stack[-1]

    def size(self):
        return len(self.stack)
```
isEmpty() 메소드는 스택이 비어 있는지 확인합니다.
push(data) 메소드는 스택에 새로운 요소를 추가합니다.
pop() 메소드는 스택의 맨 위에 있는 요소를 제거하고 반환합니다.
peek() 메소드는 스택의 맨 위에 있는 요소를 반환하지만 제거하지는 않습니다.
size() 메소드는 스택에 있는 요소의 수를 반환합니다.


사용예시
```python
s = Stack()

print(s.isEmpty())

s.push(1)
s.push("foo")
s.push(2)


print(s.size())
print(s.peek())
print(s.pop())
print(s.pop())
```
간단히 구현됨.
