##피보나치 수열

>내풀이
```python
def fibonacci(num, dct):
    if num in dct:
        return dct[num]
    elif num == 0:
        return 0
    elif num <= 2:
        return 1
    else:
        dct[num] = fibonacci(num - 1, dct) + fibonacci(num - 2, dct)
        return fibonacci(num, dct)


dct = {}
n = int(input())
print(fibonacci(n, dct))
```
피보나치 수열에 대한 나의 풀이
딕셔너리를 활용해 소요시간을 줄이도록 함.


>숏코딩
```python
a,b=0,1;exec("a,b=b,a+b;"*int(input()));print(a)
```
exec()는 숏코딩에서 가장 많이 쓰임.
exec()는 문자열 코드를 실행시킴. 보안상 위험성 큼.
숏코딩으로는 반복으로만 올라갈 수 있어 반복되는 출력에서 매우 느릴것으로 예상됨
