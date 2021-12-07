# 코드업 기초 100제 문제풀이



### 6027.10진 정수 입력받아 16진수 출력

\#hex(10)

\#'{:x}'.format(10)



a=int(input())

print(hex(a)[2:])



\# 6028. 10진 정수 입력받아 16진수 대문자 출력



a=int(input())

print(hex(a)[2:].upper())

255

FF



\# 6029 입력받은 16진수 정수 -> 8진수 형태 출력(oct()함수 사용 가능), f-string, format 을 사용할 떄는 'o'을 사용가능

a=int(input(),base=16)

print(f'{a:o}')



\# 6030 영문자 1개를 입력받아 **아스키 코드값** 출력.(파이썬에서는 .ord() 사용가능ㄴ)

a=ord(input())

print(a)



\# 6031. 10진 정수 입력받아 문저로 변환하여 출력

\# chr( )는 정수값->문자, ord( )는 문자->정수값 형태로 바꿔주는 서로 반대 방향으로 바꾸어 주는 기능을 한다.

#유니코드 코드 포인트가 정수 *i* 인 문자를 나타내는 문자열을 돌려줍니다. 예를 들어, `chr(97)` 은 문자열 `'a'` 를 돌려주고, `chr(8364)` 는 문자열 `'€'` 를 돌려줍니다. 이 것은 [`ord()`](https://docs.python.org/ko/3/library/functions.html?highlight=classmethod#ord) 의 반대입니다.

c=int(input())

print(chr(c))

65

A



\# 6032. 정수 1개 입력받아 부호 바꾸기

a=int(input())

print(-a)

65

-65



\# 6033. 문자 1개 입력받아 다음문자 출력하기

a=ord(input())

print(chr(a+1))

a

b



\# 6034. 정수 2개 입력받아 차 계산하기

a,b=input().split()

print(int(a)-int(b))

123 -123

246



\# 6035. 실수 2개 입력받아 곱 계산하기

a,b=input().split()

print(float(a)*float(b))



\# 6036. 단어 여러 번 출력하기

w, n = input().split()

print(w*int(n))

0.5 2.0

1.0



\# 6036. 단어 여러 번 출력하기

n=input()

s=input()

print(int(n)*s)

3

I love CS

I love CSI love CSI love CS



\# 6038. 정수 2개 입력받아 거듭제곱 계산하기

a,b = input().split()

print(int(a)**int(b))

2 10

1024



\# 6039. 실수 2개 입력받아 거듭제곱 계산하기

a,b=input().split()

print(float(a)**float(b))

4.0 2.0

16.0



\# 6040. 정수 2개 입력받아 나눈 몫 계산하기

a,b=input().split()

print(int(a)//int(b))

10 3

3



\# 6041. 정수 2개 입력받아 나눈 나머지 계산하기

a,b=input().split()

print(int(a)%int(b))

10 3

1



\# 6042. 실수 1개 입력받아 소숫점이하 자리 변환하기

a=float(input())

print( format(a, ".2f") )

3.141592

3.14



\#6043 : [기초-산술연산] 실수 2개 입력받아 나눈 결과 계산하기(소숫점 이하 넷째 자리에서 반올림하여 소숫점 세 번째 자리까지)

a,b=input().split()

c=float(a)/float(b)

print(format(c,".3f"))

10 3

3.333



혹은

a,b=map(float, input().split())

print(f'{a/b:.3f}')



\#6044 : [기초-산술연산] 정수 2개 입력받아 자동 계산하기

\#첫 번째 줄에 합

\#두 번째 줄에 차,

\#세 번째 줄에 곱,

\#네 번째 줄에 몫,

\#다섯 번째 줄에 나머지,

\#여섯 번째 줄에 나눈 값을 순서대로 출력한다.

\#(실수, 소수점 이하 둘째 자리까지의 정확도로 출력)

a,b=input().split()

print(int(a)+int(b))

print(int(a)-int(b))

print(int(a)*int(b))

print(int(a)//int(b))

print(int(a)%int(b))

c=float(a)/float(b)

print(format(c,".2f"))

13

7

30

3

1

3.33



\#6045 : [기초-산술연산] 정수 3개 입력받아 합과 평균 출력하기(설명)(py)

a,b,c=input().split()

d=int(a)+int(b)+int(c)

e=d/3

print(d, format(e,".2f"))

1 2 3

6 2.00



\#6048 : [기초-비교연산] 정수 2개 입력받아 비교하기1(설명)(py)

(비교/관계연산자는 <, >, <=, >=, ==(같다), !=(다르다) 6개가 있다.)

a,b=input().split()

if int(a) < int(b):

 print(True)

else:

 print(False)

1 9

True





\#6049 : [기초-비교연산] 정수 2개 입력받아 비교하기2(설명)(py)



a,b=input().split()

if int(a)==int(b):

 print(True)

else :

 print(False)

0 0

True



\#6050 : [기초-비교연산] 정수 2개 입력받아 비교하기3(설명)(py)

a,b=input().split()

if int(a)<=int(b):

 print(True)

else:

 print(False)

0 -1

False



\#6051 : [기초-비교연산] 정수 2개 입력받아 비교하기4(설명)(py)



a,b=input().split()

if int(a)!=int(b):

 print(True)

else:

 print(False)

0 1

True



\#6052 : [기초-논리연산] 정수 입력받아 참 거짓 평가하기(설명)(py)

a=int(input())

print(bool(a))

0

False![img](https://codeup.kr/upload/pimg6217_1.png)



\#6053 : [기초-논리연산] 참 거짓 바꾸기(설명)(py)

a=int(input())

print(bool(not a))

0

True

정수값이 입력될 때,
그 불 값을 반대로 출력하는 프로그램을 작성해보자.

예시
a = bool(int(input()))
print(not a)

참고
a = bool(int(input()))
와 같은 형태로 겹쳐 작성하면, 한 번에 한 단계씩 계산/처리/평가된다.
위와 같은 명령문의 경우 input( ), int( ), bool( ) 순서로 한 번에 한 단계씩 계산/처리/평가된다.

어떤 불 값이나 변수에 not True, not False, not a 와 같은 계산이 가능하다.

참 또는 거짓의 논리값을 역(반대)으로 바꾸기 위해서 not 예약어(reserved word, keyword)를 사용할 수 있다.

이러한 논리연산을 NOT 연산(boolean NOT)이라고도 부르고,
프라임 '(문자 오른쪽 위에 작은 따옴표), 바(기호 위에 가로 막대), 문자 오른쪽 위에 c(여집합, complement) 등으로 표시한다.
모두 같은 의미이다.

참, 거짓의 논리값 인 불(boolean) 값을 다루어주는 예약어는 not, and, or 이 있고,
불 값들 사이의 논리(not, and, or) 연산 결과도 마찬가지로 True 또는 False 의 불 값으로 계산 된다.

정수값 0은 False 이고, 나머지 정수 값들은 True 로 평가된다.
빈 문자열 "" 나 ''는 False 이고, 나머지 문자열들은 True 로 평가된다.

** 불 대수(boolean algebra)는 수학자 불이 만들어낸 것으로 True(참)/False(거짓) 값만 가지는 논리값과 그 값들 사이의 연산을 다룬다.



\#6054 : [기초-논리연산] 둘 다 참일 경우만 참 출력하기(설명)(py)

a,b=input().split()

print(bool(int(a)) and bool(int(b)))

1 1

True

2개의 정수값이 입력될 때,
그 불 값이 모두 True 일 때에만 True 를 출력하는 프로그램을 작성해보자.

예시
a, b = input().split()
print(bool(int(a)) and bool(int(b)))

참고
and 예약어는 주어진 두 불 값이 모두 True 일 때에만 True 로 계산하고, 나머지 경우는 False 로 계산한다.
이러한 논리연산을 AND 연산(boolean AND)이라고도 부르고, · 으로 표시하거나 생략하며, 집합 기호 ∩(교집합, intersection)로 표시하기도 한다. 
모두 같은 의미이다.

참, 거짓의 논리값 인 불(boolean) 값을 다루어주는 예약어는 not, and, or 이 있고,
불 값들 사이의 논리(not, and, or) 연산 결과도 마찬가지로 True 또는 False 의 불 값으로 계산된다.



#6056 : [기초-논리연산] 참/거짓이 서로 다를 때에만 참 출력하기(설명)(py)

a,b=input().split()

a=bool(int(a))

b=bool(int(b))

print((a and (not b)) or ((not a) and b))

* XOR
  * 베타적 논리 합 : 논리연산의 한 ㅈ동류
  * 파이썬에서 제공하지 않는 논리연산입니다
    * and, or, not
    * and, or, not 을 조합해서 새로운 논리연산을 표현
* 두 명제가 서로 다를 경우에만 참이되는 연산
* 정수에 대한 불리언 연산
  * 파이썬의 모든 객체는 참, 거짓으로 구분 가능
  * 거짓이 되는 경우 : 0 또는 빈 객체![img](https://codeup.kr/upload/pimg6221_1.png)

\#6057 : [기초-논리연산] 참/거짓이 서로 같을 때에만 참 출력하기(설명)(py)

a,b=input().split()

a=bool(int(a))

b=bool(int(b))

print((a and b) or ((not a) and (not b)))

0 0

True

![img](https://codeup.kr/upload/pimg6222_1.png).

\#6058 : [기초-논리연산] 둘 다 거짓일 경우만 참 출력하기(py)

a,b=input().split()

a=bool(int(a))

b=bool(int(b))

print(not(a or b))

0 0 

True

![img](https://codeup.kr/upload/pimg6223_1.png)

\#6065 : [기초-조건/선택실행구조] 정수 3개 입력받아 짝수만 출력하기(설명)(py)

a,b,c=map(int,input().split())

if(a%2==0):

 print(a)

if(b%2==0):

 print(b)

if(c%2==0):

 print(c)

1 2 4

2

4



\#6066 : [기초-조건/선택실행구조] 정수 3개 입력받아 짝/홀 출력하기(설명)(py)

a,b,c=map(int,input().split())

if (a%2==0):

 print('even')

else:

 print('odd')

if (b%2==0):

 print('even')

else:

 print('odd')

if (c%2==0):

 print('even')

else:

 print('odd')

1 2 8

odd

even

even

* a=2 (거짓)
* if not a % 2 : print(a)  <--- 거짓이 아니므로 짝수 출력



\#6068 : [기초-조건/선택실행구조] 점수 입력받아 평가 출력하기(설명)(py)

a=int(input())

if a>=90:

 print('A')

elif a>=70:

 print('B')

elif a>=40:

 print('C')

elif a<=39:

  print('D')

73

B



\#6069 : [기초-조건/선택실행구조] 평가 입력받아 다르게 출력하기(py)

a=input()

if a=='A':

 print('best!!!')

elif a=='B':

 print('good!!')

elif a=='C':

 print('run!')

elif a=='D':

 print('slowly~')

elif a=='F':

 print('what?')



\#6070 : [기초-조건/선택실행구조] 월 입력받아 계절 출력하기(설명)(py)

a=int(input())

if a==12 or a==1 or a==2:

 print('winter')

if a==3 or a==4 or a==5:

 print('spring')

if a==6 or a==7 or a==8:

 print('summer')

elif a==9 or a==10 or a==11:

 print('fall')

1

winter



\#6071 : [기초-반복실행구조] 0 입력될 때까지 무한 출력하기(설명)(py)

\# 모든 임력을 한 번에 받아서 일괄적으로 처리할 필요가 없음.

\# 각각의 주어진 입력을 서로 다른 테스트 케이스로 보고 처리하면 됨.

\# 0이 입력되면 더 이상 입력을 받지 않아도 됨.

#input 은 모든 입력을 문자열 형태로 반환 (LF, 뉴라인 까지 입력을 받음)



```
while True :
  n=int(input())
  if n !=0:
    print(n)
  else:
    break
1
1
10
10
0
```





\#6072 : [기초-반복실행구조] 정수 1개 입력받아 카운트다운 출력하기1(설명)(py)

a=int(input())

while True:

 print(a)

 a=a-1

 if (a==0):

  break

5

5

4

3

2

1



### ''반복문과+리스트 ''를 얼마나 잘 다룰것인가? (코딩 테스트 중요)



#6073 : [기초-반복실행구조] 정수 1개 입력받아 카운트다운 출력하기2(py) 해결

a=int(input())

while True:

 a=a-1

 print(a)

 if (a==0):

  break

5

4

3

2

1

0

```
#6073 다른 풀이
n=int(input())
while True:
  if n>=0:
    print(n)
    n=n-1   # n -=1
  else:
    break
```





\#6074 : [기초-반복실행구조] 문자 1개 입력받아 알파벳 출력하기(설명)(py)

c=input()

b=ord('a')

c=ord(c)

while b<=c:

 print(chr(b), end=' ')

 b+=1

f

a b c d e f 



```
#6074
#n=input()
#n=ord(n)

#print(n)
#print(chr(n))

n=ord(input())
for ch in range(97, n+1):
  print(chr(ch))
f
a
b
c
d
e
f
```



```

n=ord(input())
for ch in range(97, n+1):
  print(chr(ch), end=' ' )

f
a b c d e f
```





\#6075 : [기초-반복실행구조] 정수 1개 입력받아 그 수까지 출력하기1(py)

a=int(input())

i=0

while i<=a:

 print(i)

 i+=1

5

0

1

2

3

4

5

```
#6075 2
# while 의 경우 for을 사용할 수 없겠다 싶으면 while 사용
n = int(input())
for i in range(n+1):
  print(i)

```



\#6076 : [기초-반복실행구조] 정수 1개 입력받아 그 수까지 출력하기2(설명)(py)

a=int(input())

for i in range(a+1):

 print(i)

4

0

1

2

3

4



## 파이썬에서 for, while 의 차이점

- for 
  - 이터레이블(반복가능한 자료) 객체에 대해서 반복적인 연산이 가능
  - 반드시 이터레이블 객체가 있어야 합니다.
  - while 의 경우 for을 사용할 수 없겠다 싶으면 while 사용
- while
  - 이터레이블이 아닌 경우에 반복이 필요하다면 사용

