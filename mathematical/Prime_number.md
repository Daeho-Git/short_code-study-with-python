## 소수를 구하는 코드

여기 몇 가지 방법으로 소수를 찾는 파이썬 코드를 제시합니다.

> 기본 알고리즘:
```python
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

def find_primes(start, end):
    primes = []
    for n in range(start, end + 1):
        if is_prime(n):
            primes.append(n)
    return primes

start, end = 10, 50
print(find_primes(start, end))
```

> 에라토스테네스의 체를 사용한 알고리즘:
```python
def sieve_of_eratosthenes(start, end):
    sieve = [True] * (end + 1)
    sieve[0] = sieve[1] = False

    for p in range(2, int(end**0.5) + 1):
        if sieve[p]:
            for i in range(p*p, end + 1, p):
                sieve[i] = False

    primes = [p for p in range(start, end + 1) if sieve[p]]
    return primes

start, end = 10, 50
print(sieve_of_eratosthenes(start, end))
```

> 기본 알고리즘을 개선하여 짝수를 건너뛰는 방식:
```python
def is_prime(n):
    if n < 2:
        return False
    if n == 2:
        return True
    if n % 2 == 0:
        return False
    for i in range(3, int(n**0.5) + 1, 2):
        if n % i == 0:
            return False
    return True

def find_primes_optimized(start, end):
    if start < 2:
        start = 2
    if start % 2 == 0:
        start += 1
    primes = [n for n in range(start, end + 1, 2) if is_prime(n)]
    if start == 3:
        primes.insert(0, 2)
    return primes

start, end = 10, 50
print(find_primes_optimized(start, end))
```
알고리즘 중에서 에라토스테네스의 체를 사용한 알고리즘이 일반적으로 가장 빠르지만,
범위가 크지 않은 경우에는 기본 알고리즘과 개선된 기본 알고리즘이 충분히 효율적입니다.

```python
def primes(a, b): return [n for n in range(a, b+1) if all(n % i != 0 for i in range(2, int(n**0.5)+1)) if n > 1]
while (n := int(input())): print(primes(n, 2 * n))
```
짧게 썼지만 타임아웃에 주의!


```python
m=999999
i,e=1,[1]*(m+1)
while(i:=i+1)*i<m+1:
 if e[i]:e[2*i::i]=[0]*(m//i-1)
while(n:=int(input()))>0:
 print(sum(e[n+1:2*n+1]))
```
누군가의 코드. 시간 여유생길 때 자세히 볼 
