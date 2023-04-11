##Euclid's Composition Act

math모듈을 사용하면 쉽게 구현이 가능
```python
import math
a, b = map(int, input().split())
print(math.gcd(a, b))
print(math.lcm(a, b))
```

유클리도 호제법
```python
a,b=map(int,input().split());L=a*b
while b:a,b=b,a%b
print(a,L//a)
```

백준 2609번 기준으로 유클리드가 더 짧은 메모리로
두 코드 모두 같은시간으로 해결되었다.
(44ms)

math모듈은 c언어로 구현돼 속도가 빠를 수 있는데
데이터의 차이로 생각함.