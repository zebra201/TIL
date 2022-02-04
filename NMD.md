## 2021.12.07 노마드 코드 (파이썬 웹 스크롤링)



1. 이론, 파이썬 이론, 프로그래밍 언어  이론
2. 웹스크래핑(웹사이트 자동 수집)
3. Django

- HTML 을 알면 도움이 됨. 

- 구글 크롬 사용!(온라인 컴파일러가 크롬에서 작동)

- 노마드 아카데미에 질문 가능

(제대로 질문하는 법이 중요, 코드가 작동이 안되요-> 목적,무엇을 하였는가,했는데 안되는지 , 어떤 에러인가)

## 1. 이론

### 1-1. Data Types of Python

* variable(변수) : a=2, b=3 과 같은
* print() 는 function() 함수가 하는일은 터미널에 결과를 출력하는 것

- 문자열(like this)은 정의되어 있지 않으므로 ''(따옴표,혹은 쌍따옴표) 로 둘러 쌓여야 함.
- 숫자, 문자(text=string이라고함), 참 거짓
- 변수에 넣을 수 있는것은 참(True) 혹은 거짓(False)이며, 파이썬에서는 문자열이 아닌 참 과 거짓으로 인식한다.(코딩할때 0(False)을 제외한 모든 정수는 True), c='False' 일때 여기서 False 는 string을 나타냄.
- (str) a_string='like this'
- (int) a_number=3 
- (float) a_float=3.12 (소수점이하 자리수가 있는 숫자)
- (bool) a_boolean=False (참, 거짓)
- (none) a_none = None (''존재하지 않는다'', ''없다''를 의미, 파이썬에만 존재, 자바로 치면 null)

- 언더바 는 파이썬 유저의 암묵적인 룰 'super_long_variable' 과 같음 <- snake case 라고 부름

## 1-1. Lists in Python

* 파이썬에는 sequence type (열거형 타입) (List와 Tuple)
  * 누군가 요일을 물어보고, 3번째 요일을 물어본다면?
  * 많은 값을 하나의 list 에 저장하고 싶다, list 를 가지고 연산할 수 있다. 많은 value 를 열거
  * [대괄호]로 구분해주며, ''콤마''로 구분한다 ( ex : days=['Mon', Tue','Wed'] )
  * 여기서 days 는 더이상 string 이 아닌 list 로 변함.
  * 즉, 여러가지의 개별 string을 대괄호 안에 가지게 됨

``` 
days=['Mon','Tue','Wed','Thur','Fri']
print(type(days)) 
<class 'list'>
```

``` print('Mon'in days)
print('Mon'in days)
True
```

``` 
print(days[3])
Thur
* index 는 0부터 시작하므로 4번째 요일을 물어본 것과 같음.
```

```
길이를 알고 싶다면
print(len(days))
5
```



## 1-2 Tuples and Dicts

```
print(days)
days.append("Sat")
print(days)

['Mon', 'Tue', 'Wed', 'Thur', 'Fri']
['Mon', 'Tue', 'Wed', 'Thur', 'Fri', 'Sat']
```

```
days.reverse()
print(days)
['Sat', 'Fri', 'Thur', 'Wed', 'Tue', 'Mon']
```

- Mutable(수정가능) : 가변 시퀀스형(값 변경 가능)
- list는 시퀀스이지만 Mutable (값을 수정할 수 있음)
- list는 또한 공통, 가변연산자 둘다 사용 가능

- Immutable(수정 불가능) : 불가변 시퀀스
- Tuple 은 list 와는 다르게 공통 연산자만 가능

```
<대괄호 대신 소괄호로 묶는다. 튜플>
days=('Mon','Tue','Wed','Thur','Fri')
print(type(days)) 
<class 'tuple'>
```



- 아무도 변경 할 수 없는 데이터 값을 원할때 튜플 사용

- tuple 에서는 list 와 같은 것을 50% 정도 사용할 수 있음

```
name='Nico'
age=29
korean=True
fav_food=['Kimchi','Sashimi']

   * dictionary를 만들때에는 중괄호 {} 사용,
     그리고 변수명을 스트링으로 변환하고 = 을 : 로 변환 후 , 추가
nico = {"name" : 'Nico',
"age" : 29,
"korean" : True,
"fav_food" : ['Kimchi','Sashimi']}

print(nico)
{'name': 'Nico', 'age': 29, 'korean': True, 'fav_food': ['Kimchi', 'Sashimi']}

* 만약 음식만 가져오고 싶다면
print(nico['fav_food'])
['Kimchi', 'Sashimi']

* nico 에 변수를 추가하고 싶다면
nico['handsome']=True
print(nico)
{'name': 'Nico', 'age': 29, 'korean': True, 'fav_food': ['Kimchi', 'Sashimi'], 'handsome': True}

```

* list, tuple, dictionary 는 각각의 방식으로 유용함.
* 위에선 dictionary 안에 list로 정보 저장



## 1-3 Built in Function

- function : 어떤 행동(기능)을 가지고 있고 이를 계속 반복할 수 있음

- ```python
  age="18"
  print(age)
  print(type(age))
  
  n_age=int(age)
  print(n_age)
  print(type(n_age))
  
  18
  <class 'str'>
  18
  <class 'int'>
  
  ```



## 1-4 Creating a Your First Python Fuction

- 파이썬에서는 function을 define(정의)한다고 함.

- ```
  def say_hello():
    print('hello')
    print('bye')
  
  say_hello()
  
  hello
  bye
  ```

- 들여쓰기, 내어쓰기가 맞지 않으면 function 이 작동하지 않음

- say_hello 에서 괄호(스위치 역할)이 없다면 hello, bye는 출력되지 않음



## 1-5 Fuction Arguments

```
def say_hello(who):
  print('hello', who)

say_hello('Lee')

hello Lee

```

```
def plus(a,b):
  print(a+b)

plus(2,5)
7
```

```
def minus(a,b):
  print(a-b)
minus(5,2)
3
```



- 디폴트 값 지정해주기

```
def say_hello(name='annoymous'):
  print('hello', name)

say_hello()
say_hello('Lee')

hello annoymous
hello Lee
```



## 1-6 Returns

- function 의 호출하는 대부분의 경우 결과를 더 신경써야 함. function 을 더 많이 사용

- ```
  def p_plus(a,b):
    print (a+b)
  
  def r_plus(a,b):
    return a+b
  
  p_result = p_plus(2,3)
  r_result = r_plus(2,3)
  
  print(p_result, r_result)
  
  5
  None 5
  ```

- return 키워드를 사용하면, function 을 호출할때, funtion이 return 값으로 치환되어 r_plus(2,3)을 5로 치환 하여 출력함.

- 반면, p_result 의 경우  print 만 함.

- 또한 return 은 function 을 종료함

  

```python
def r_plus(a,b):
  return a+b
  print("asdfasdf")
  
r_result = r_plus(2,4)

print(r_result)
6
```

- 코드에서 보다시피 print('asdfasdf') 는 출력되지 않음
- 파이썬에서는 리턴하는 순간 function은 종료가 됨. 오직 한번에 하나의 function 값만 리턴할 수 있음
- 즉, return 아래에 있는 print 는 없는 것과 마찬가지
- print 는 나타난 값을 쓸 수 없다는 의미 (None, 아무것도 아님)



## 1-7, 1-8 Keyworded Arguments

- 지금껏 Positional Argunment(인자)를 사용함. 위치에 의존함

- Keyword Argunment 는 이름으로 쌍을 이뤄줌. 예를 들어 result=plus(b=30,a=1)

- ```
  def plus(a,b)
    return a-b
    
  result=plus(b=30, a=1)
  print(result)
  -29
  ```

- 인자의 순서를 신경 쓰지 않아도 됨.

- ```python
  def say_hello(name, age):
    return 'hello name you are age years old'
  
  hello = say_hello('Lee', '20')
  print(hello)
  
  hello name you are age years old
  
  이건 텍스트이므로 변수가 아직 포함되어 있지 않음
  변수를 포함시키고 싶으면
  f string 추가 해야 함(f는 format을 의미)
  ```

- ```python
  def say_hello(name, age):
    return f'hello {name} you are {age} years old'
  # 혹은 return 'hello '+ name + ' you are ' + age + ' years old '
  
  hello = say_hello('Lee', '20')
  # key argument 를 적용한다면 hello = say_hello(name='Lee', age='20')
  print(hello)
  ```

- 변수가 많아질수록 key argument를 사용하는 것이 좋다



## 1-9 코드 챌린지 - 7 function

- 계산기 만들기



## 1-10 Conditionals Part One

```
def plus(a,b):
  if type(b) is int or type(b) is float : 
    return a + b
  else :
    return None

print(plus(12, 1.2))
```

- if 조건



## 1-11. if else and or

- and, or, not

```
def age_check(age):
  print(f"you are {age}")

age_check(18)

you are 18

```



```
def age_check(age):
  print(f"you are {age}")
  if age < 18:
    print("you cant drink")
  else:
    print("enjoy your drink")

age_check(18)
```



```
def age_check(age):
  print(f"you are {age}")
  if age < 18:
    print("you cant drink")
  elif age == 18:
    print("your are new to this!")
  else:
    print("enjoy your drink")

age_check(18)
```



````
def age_check(age):
  print(f"you are {age}")
  if age < 18:
    print("you cant drink")
  elif age == 18:                     # elif = else if
    print("your are new to this!")
  elif age >20 and age < 25 :         # and 는 둘다 true 여야 함, or는 둘 중 하나
    print("you are still kind of young")
  else:
    print("enjoy your drink")

age_check(23)
````



## 1-12. for in

- 

```
days = ("Mon", "Tue", "Wed", "Thu", "Fri")

# 각 요일을 출력하되 한 줄씩 출력하려면 for 을 사용해야함
# for 을 사용하면 각 아이템을 순서대로, 하나씩 작업할 수 있음

for x in days:    # x 는 변수값은 Mon, Tue ~ Fri 값, 계속 값이 변함, 중요한 것은 in 뒤의 days  	print(x)


Mon
Tue
Wed
Thu
Fri
```



```
days = ("Mon", "Tue", "Wed", "Thu", "Fri")

# 각 요일을 출력하되 한 줄씩 출력하려면 for 을 사용해야함
# for 을 사용하면 각 아이템을 순서대로, 하나씩 작업할 수 있음

for x in [1,2,3,4,5]:    # 중요한 것은 in 뒤의 days
  print(x)

1
2
3
4
5

```



````
days = ("Mon", "Tue", "Wed", "Thu", "Fri")

for x in days:
  if x is "Wed":
    break
  else :
    print(x)

Mon
Tue

````

- string 도 배열(sequence)





### 1-13 Modules

- 파이썬에서는 모듈이 존재하며 프로그램에 import 하여 사용 가능

```
import math

print(math.ceil(1.2))    # ceil -> 값을 반올림해줌. 그전에 math 모듈을 import 해야함
print(math.fabs(-1.2))   # fabs -> 절대값

2
1.2
```



- import 시 전부 할 필요 없음. 필요한 것만 임포트 가능

~~~
from math import ceil, fsum

print(ceil(1.2))
print(fsum([1,2,3,4,5,6,7]))

2
28.0
~~~



- fsum 의 이름을 변경할 수도 있음

```
from math import fsum as Lee_sum

print(Lee_sum([1,2,3,4,5,6,7]))

28.0

```



- 다른 파일에서 정의된 기능을 불러와서 사용하는 것도 가능

```
# calculator 파일

def plus (a,b):
  return a+b
def minus(a,b):
  return a-b	


# 다른 파일에서 import 해서 사용 가능.(.py 없이 파일명만 붙여서 사용)

from calculator import plus, minus

print(plus(1,2))
print(minus(1,2))


```





## 2.0 What is Web Scrapping?

- 웹 상의 데이터를 추출하는 것을 의미함
- 구글에서도 검색시 다른 홈페이지에서 스크래핑(추출)하여 보여줌.
- 여러 홈페이지에서 일정 시간에 추출 기능을 실행하여 중요한 정보를 웹사이트로 가져와서 이메일로 보낼 수 있음.



## 2.1 What are we Building?

- 프로젝트에서는 파이썬 관련 일자리를 찾는 다면? indeed or stackoverflow 에서 페이지를 넘겨보면 요약 정보를 볼 수 있고 클릭 시 디테일 정보가 나옴.
- 스크래퍼를 만들어서 두 홈페이지에서 들어간 뒤 모든 페이지의 일자리를 추출할 예정
- 홈페이지에서는 모든 정보를 보여주지 않음.
- 이 후 일자리를 엑셀 시트로 옮길 예정.(한줄 한줄 표현될 예정)



## 2.2 Navigating with Python

- 사용전 requests 함수를 불러와야함 (import requests)

```
HTML 가져오기

import requests

indeed_result = requests.get("https://www.indeed.com/jobs?as_and=python&limit=50")
                             
print(indeed_result.text)
```

- HTML 을 전부 불러온 뒤 원하느 정보를 가져와야 함. (그중에서 페이지를 불러오자)
- 수동으로 하면 느리므로 BeautifulSoup 사용예정(아주 유용한 패키지임)
- 최대 페이지를 코드에 알려줘서 페이지 20까지 갈 수 있도록 할 예정.



## 2.3 Extracting Indeed Pages



