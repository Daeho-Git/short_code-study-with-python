## 주어진 식을 최솟값이 되게 괄호를 추가


나의 풀이
```python
def min_expression(expression):
    split_minus = expression.split('-')
    result = sum(map(int, split_minus[0].split('+')))

    for i in range(1, len(split_minus)):
        result -= split_minus[i].split('+')
    return result

if __name__ == '__main__':
    expression = input().strip()
    print(min_expression(expression))
```


숏코딩
```python
a,*b=[sum(map(int,s.split('+')))for s in input().split('-')];print(a-sum(b))
```

*b (extended unpacking)을 이용해서 a,b 를 분리해서 a 에서 sum(b)를 빼는 방식
