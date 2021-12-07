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



## 1-3