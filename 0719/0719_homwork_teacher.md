## homework

1. mutteble : dic , set, list

    immutable : str, range, tuple 

    2. dic 에서 key는 immutable 한 값만 가능

    3. 

```python
scores = [80,89, 99 ,83]
total = 0
count =0
for sc  in scores:
    totla = totla + sc
    count += 1

average = total /count 
```

### workshop

1. ```python
   a = int(input())
   b = int(input())
   print( a+b)
   ```

### onsil

```python
# 내 풀이
orders = '아이스아메리카노,카라멜마키야또,에스프레소,아메리카노,아메리카노,아이스라떼,핫초코,아이스아메리카노,아메리카노,아이스카라멜마키야또,아이스라떼,라떼마키야또,카푸치노,라떼마키야또'

orders = orders.split(',')

# 총 주문 건수 
count = len(orders)

# 중복제거 주문 음료 리스트
set_orders= list(set(orders))
# 중복제거 주문 음료 리스트 내림차순 정렬 & 출력 
set_orders = sorted(set_orders, reverse = True)
print(f'총 주문 건수는 {count}잔 입니다')
print(set_orders)


# 교수님 풀이 내장함수 x
orders = '아이스아메리카노,카라멜마키야또,에스프레소,아메리카노,아메리카노,아이스라떼,핫초코,아이스아메리카노,아메리카노,아이스카라멜마키야또,아이스라떼,라떼마키야또,카푸치노,라떼마키야또'

orders = orders.split(',')

count = 0
for coffe in orders:
    count +=1
print(f'총 주문 건수는 {count}잔 입니다')

menu = []
for coffe in orders:
    if coffe in menu:
        continue
    else:
        munu.append(coffe)

print(sorted(menu, reverse = True))
```
