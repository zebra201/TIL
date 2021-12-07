## 코드업 파이썬 기초 100제 문제풀이 2



```
#6077 : [기초-종합] 짝수 합 구하기(설명)(py)
#6077 : [기초-종합] 짝수 합 구하기(설명)(py)
n=int(input())
total=0
# 1부터 n까지의 수열
for i in range (1,n+1,2):
#if i % 2: continue
    total=total+i
print(total)

```

```
#6081 : [기초-종합] 16진수 구구단 출력하기(py)

n=int(input(),base=16)

# 16진수도 숫자이므로, 그냥 곱해주면 됨
for i in range(1,16):
  print(f'{n:X}*{i:X}={n*i:X}')

B
B*1=B
B*2=16
B*3=21
B*4=2C
B*5=37
B*6=42
B*7=4D
B*8=58
B*9=63
B*A=6E
B*B=79
B*C=84
B*D=8F
B*E=9A
B*F=A5
```



### 포맷 문자열 확인(f 스트링 관련)

https://docs.python.org/ko/3/library/string.html#formatstrings.



구구단 예제

```
#예시 : n단구구단 출력

n=int(input())
for i in range (1,10):
  print(f'{n}*{i}={n*i}')

2
2*1=2
2*2=4
2*3=6
2*4=8
2*5=10
2*6=12
2*7=14
2*8=16
2*9=18
```

```
#예시2 : 2~9단 구구단 한번에 출력

n=2 # 2,3,4,5,6,.....,9 (이를 '중첩 루프'라고 함)

for n in range(2,10):
  for i in range (1,10):
    print(f'{n}*{i}={n*i}')
    
2*1=2
2*2=4
2*3=6
2*4=8
2*5=10
2*6=12
2*7=14
2*8=16
2*9=18
3*1=3
3*2=6
3*3=9
3*4=12
3*5=15
3*6=18
3*7=21
3*8=24
3*9=27
4*1=4
4*2=8
4*3=12
4*4=16
4*5=20
4*6=24
4*7=28
4*8=32
4*9=36
5*1=5
5*2=10
5*3=15
5*4=20
5*5=25
5*6=30
5*7=35
5*8=40
5*9=45
6*1=6
6*2=12
6*3=18
6*4=24
6*5=30
6*6=36
6*7=42
6*8=48
6*9=54
7*1=7
7*2=14
7*3=21
7*4=28
7*5=35
7*6=42
7*7=49
7*8=56
7*9=63
8*1=8
8*2=16
8*3=24
8*4=32
8*5=40
8*6=48
8*7=56
8*8=64
8*9=72
9*1=9
9*2=18
9*3=27
9*4=36
9*5=45
9*6=54
9*7=63
9*8=72
9*9=81
```

```
# 중첩루프 (파이썬 튜터에서 명확하게 확인가능)

for n in range(2,10):
  print(n, end=' ')
  print()

  for i in range(1,10):
    print(i, end=' ')
  print()
```



```
#백준 별찍기-1
# 제출 할 때 n을 표준입력으로 받아서 처리, 문제와 같이 n=5라고 가정하고 진행.
n=int(input())
for i in range(n):
  for j in range(i+1):
    print('*', end='')
  print('')
```

```
#백준 별찍기 - 만약 사각형 이라면
n=int(input())
for i in range(n):
  for j in range(n):
    print('*', end='')
  print('')
```

```
#백준 별찍기-2

n=int(input())
for i in range(1,n+1):
# 공백도 같이 출력해야함
  for a in range(n-i):
    print(' ', end='')
# 별 같이 출력    
  for b in range(i):
    print('*', end='')
  print()
 5
    *
   **
  ***
 ****
*****
```



```
##별찍기-3
# 별찍기 -1번과 동일한 문제
# 반대로 찍어야함
# -2번의 공백 출력을 응용

#오답 n=int(input())
#for i in range(n+1,1,-1):
#  for a in range(n):
#    print('*', end='')
#  print('')


n=int(input())
for i in range(n,0,-1):
  for a in range(i):
    print('*', end='')
  print()
  
5
*****
****
***
**
*
```

````
#별찍기-4
n=int(input())
for i in range(n,0,-1):
  for b in range(n-i):
    print(' ', end='')

  for a in range(i):
    print('*', end='')
  print()
5
*****
 ****
  ***
   **
    *
```



```
#별찍기-4 -2
n=int(input())
for i in range(n):
  for k in range(i):
    print(' ', end='')
  for j in range(n-i):
    print('*',end='')
  print()
5
*****
 ****
  ***
   **
    *
```



```
#백준 별찍기-5
# 첫째 줄에는 별 1개, 둘째 줄에는 별 3개, ..., N번째 줄에는 별 2×N-1개를 찍는 문제

n=int(input())

for i in range(n+1):
  #공백
  for k in range(n-i):
    print(' ', end='')
  #별
  for j in range( 2 * i -1):
    print('*', end='')
  print()
5
     
    *
   ***
  *****
 *******
*********
```



루프 + 리스트 => 다차원(2차원) 리스트



```
#코드업,6092 : [기초-리스트] 이상한 출석 번호 부르기1(설명)(py)

```

```
#코드업,6092-2 : [기초-리스트] 이상한 출석 번호 부르기1(설명)(py)

n = int(input())
a = list(map(int, input().split()))

check = [0] * 24
for i in a:
  check[i] += 1
print(*check, sep=' ')

10
1 2 4 3 4
0 1 1 1 2 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0
```

```
# 6093 : [기초-리스트] 이상한 출석 번호 부르기2(py)

n=int(input())
a=input().split()
for i in range(n):
  a[i]=int(a[i])
for i in range(n-1, -1, -1):
  print(a[i], end=' ')
10
10 4 2 3 6 6 7 9 8 5
5 8 9 7 6 6 3 2 4 10 
```

```
n=int(input())
a=list(map(int, input().split()))

for i in range(n-1, -1, -1):
  print(a[i], end=' ')
10
10 4 2 3 6 6 7 9 8 5
5 8 9 7 6 6 3 2 4 10 
```

```
n=int(input())
a=list(map(int, input().split()))

a.reverse()
print(*a, sep=' ')
10
10 4 2 3 6 6 7 9 8 5
5 8 9 7 6 6 3 2 4 10
```



```
# 6094 : [기초-리스트] 이상한 출석 번호 부르기3(py)

n=int(input())
a=list(map(int,input().split()))

#print(min(a))
#print(max(a))
# 최대 최소 함수 사용하지 말고

min=9999999999
for i in a :
  if min > i : min = i   # 값을 넣었을때 min 값보다 i 가 작으면 min 값을 i 로 저장
print(min)

# min_a = True
# for i in a :
#  if min_a or min_a > i: min_a = i
# print(min_a)

max= True
for i in a :
  if max or max < i: max = i
print(max)

10
10 4 2 3 6 6 7 9 8 5
2
5
```

