> 입력받은 연 월 일로 요일을 알아내는 방법

```python
from datetime import date
x, y = map(int, input().split())
my_date = date(2007, x, y)
day_of_week = my_date.weekday()
day_name = ["MON", "TUE", "WED", "THU", "FRI", "SAT", "SUN"]
print(day_name[day_of_week])
```

datetime의 weekday()를 이용해 반환받은 정수를 요일로 환산

```python
m,d=map(int,input().split())
print('FSSMTWTRAUOUEHITNNEDU'[(d+m*23//9-(m>2)*2)%7::7])
```

(d + m * 23 // 9 - (m > 2) * 2) % 7: 요일을 계산하기 위한 식입니다.
이 식은 Zeller's Congruence라고 불리는 알고리즘을 기반으로 합니다.
Zeller's Congruence는 주어진 날짜에 대해 요일을 계산하는데 사용되는 공식입니다.
여기서 (m > 2) * 2는 입력받은 월이 2월보다 큰 경우 2를 빼줍니다. 이 값에 7로 나눈 나머지를 구하여 요일을 계산합니다.

'FSSMTWTRAUOUEHITNNEDU'[(d + m * 23 // 9 - (m > 2) * 2) % 7::7]: 요일을 계산한 값을 문자열 'FSSMTWTRAUOUEHITNNEDU'에서 인덱스로 사용합니다.
문자열은 각 요일의 첫 글자로 구성되어 있으며 3개의 글자가 연속되어 있습니다.
문자열 슬라이싱을 사용하여 [시작:끝:간격] 형태로 각 요일의 첫 글자를 가져옵니다.
이를 통해 요일을 출력합니다.
