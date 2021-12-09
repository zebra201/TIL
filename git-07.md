### 파이썬 Numpy 

- 저차원의 배열을 고차원의 배열로 변경
- 고차원의 배열을 저차원의 배열로 변경
  - 저차원은 1차원 배열로 변경이 가능합니다.
- 변경전의 크기와 변경 후의 크기가 달라지면 안됩니다.
  - 자료의 개수가 반드시 일치



```
arr1D=np.random.randint(0,10, size=4)
arr1D

array([2, 1, 6, 9])

```

```
display( arr1D.reshape(2, 2) )
display( arr1D.reshape(4, 1) )

# 열의 크기를 정해 놓으면 나머지는 자동으로 계산 (열에 맞춰 놓으면 됨)
display( arr1D.reshape(-1, 2) )
display( arr1D.reshape(-1, 1) )

array([[2, 1],
       [6, 9]])
array([[2],
       [1],
       [6],
       [9]])
array([[2, 1],
       [6, 9]])
array([[2],
       [1],
       [6],
       [9]])

```

```
# 고차원의 배열을 저차원으로 변경

arr2D = np.random.randint(1, 10, size=(3, 3))
arr2D

# 행 기준 변환
display(arr2D.flatten())
display(arr2D.ravel())

# 열 기준 변환 (F 파라미터 이용)
display( arr2D.flatten(order='F') )


array([9, 9, 3, 5, 8, 1, 3, 1, 3])
array([9, 9, 3, 5, 8, 1, 3, 1, 3])
array([9, 5, 3, 9, 8, 1, 3, 1, 3])
```



### 행렬(Matrix)

- 여러개의 벡터가 모여서 하나의 행렬을 이루게 입니다.

```
# 행이 n개이고, 열이 m개인 배열을 행렬이라고 보면 됩니다. 
mat = np.random.randint(1, 10, size=(3, 5) )
mat


# (9,4,7), (7,1,6) 을 하나의 벡터로 보고, 이들이 모여 행렬을 구성
array([[9, 7, 6, 7, 9],
       [4, 1, 8, 7, 3],
       [7, 8, 1, 6, 4]])
```



## 타입이 다른 피연산자간의 연산

- 사칙연산만 다룹니다.
- 크기가 서로 같기만 하다면, 문제가 없는데
- 크기가 다른 경우에는 문제가 됩니다.
  - 브로드캐스팅이 되는 경우와 그렇지 않은 경우로 나눠서 보면 됩니다.

```
# 스칼라와 벡터의 연산
# 작은쪽의 크기를 큰 쪽의 크기에 맞춰서 확장(브로드캐스팅)
# 같은 위치의 값들끼리 연산
vector = np.random.randint(1, 10, size=(4,1))
vector
array([[1],
       [3],
       [2],
       [9]])
```

```
스칼라를 연산하려는 벡터의 크기에 맞춰서 확장
2 * vector


array([[ 2],
       [ 6],
       [ 4],
       [18]])

# 이를 브로드캐스팅이라고 함.
2  x  1
2  x  3
2  x  2
2  x  9
```

```
# 스칼라와 행렬의 연산
# 마찬가지로 브로드캐스팅 후에 같은 위치끼리 연산
mat = np.random.randint(1, 10, size=(3, 4))
mat

array([[9, 8, 8, 5],
       [9, 3, 5, 2],
       [9, 3, 6, 4]])
       
2 * mat

array([[18, 16, 16, 10],
       [18,  6, 10,  4],
       [18,  6, 12,  8]])
```

```
vector = np.random.randint(1, 10, size=(3,1))
vector
array([[3],
       [9],
       [3]])
```

```
# 벡터와 벡터의 연산은 브로드캐스팅이 되지 않기 때문에, 크기가 반드시 같아야 합니다.
vec1 = np.random.randint(1, 10, size=(3, 1))
vec2 = np.random.randint(1, 10, size=(4, 1))
display( vec1, vec2 )

array([[4],
       [8],
       [5]])
array([[2],
       [9],
       [8],
       [5]])
```

```
# 크기가 같다면, 연산이 가능합니다. 
vec1 = np.random.randint(1, 10, size=(3, 1))
vec2 = np.random.randint(1, 10, size=(3, 1))
display( vec1, vec2 )

array([[4],
       [7],
       [8]])
array([[7],
       [3],
       [9]])
```

```
vec1 * vec2

array([[28],
       [21],
       [72]])
```

```
# 행렬과 행렬의 연산
# 차원이 같으면, 벡터와 마찬가지로 브로드캐스팅 되지 않습니다. 
# 차원이 다르면, 저차원 행렬이 고차원의 행렬로 브로드캐스팅 가능하면 연산이 가능
# 같은 차원이라면, 반드시 두 행렬의 크기가 같아야 합니다. 
mat1 = np.random.randint(1, 10, size=(2, 2))
mat2 = np.random.randint(1, 10, size=(2, 2))
display( mat1, mat2 )

array([[6, 8],
       [8, 2]])
array([[6, 6],
       [1, 8]])
```



```
mat1 * mat2

array([[36, 48],
       [ 8, 16]])
```



## 판다스



```
# 데이터 분석용 필수 패키지들 입니다. 
# 사용하지 않더라도 일단 가져오고 봅니다
import numpy as np
import pandas as pd
```



# 판다스란?

- 파이썬에서 사용할 수 있는 데이터 전처리용 패키지 입니다.
  - 엑셀처럼 파일을 다룰 수 있게 해주는 도구 입니다.
  - 엑셀과의 가장 큰 차이점은 아주 큰 파일도 처리가 가능
    - 일반적으로 100MB만 넘어가도 잘 안열립니다
    - 판다스는 1GB 넘어가는 아주 큰 파일도 빠르게 처리가 가능
  - 엑셀보다 더 복잡한 처리, 디비와 연동 등의 기능을 제공
- 데이터 분석
  - 분석 업무의 80%는 전처리 입니다.
  - 잘 정제되지 않은 데이터는 분석을 아무리 잘해도 의미가 없습니다



## Series

- 1차원 구조를 표현



```
# 인덱스와 함께 표현되서 2차원 처럼 보이지만, 1차원 입니다. 
series = pd.Series( [10, 20, 30, 40] )
series

0    10
1    20
2    30
3    40
dtype: int64
```

```
display( series.ndim )
display( series.shape )

1
(4,)
```



## DataFrame

- 2차원 구조
- 여러개의 시리즈가 모여서 하나의 데이터프레임이 됩니다.

```
weight = pd.DataFrame([
  [76.4, 'kg'],
  [75.7, 'kg'],
  [76, 'kg'],
  [76.2, 'kg']
])
weight


       0	1
0	76.4	kg
1	75.7	kg
2	76.0	kg
3	76.2	kg
```

```
display( weight.ndim )
display( weight.shape )

2
(4, 2)
```



- 로그
  - 정제되어 있지 않은 날 것의 자료
- 전처리
  - 횡단면 자료
  - 시계열 자료
- 분석 가능한 자료가 되려면
  - 타입도 일치
  - 결측치가 있으면 안된다.





```
## 다중조건
# - 판다스에서는 기호를 쓰지 않음
- and, or, not
 - 판다스는 &(앰퍼샌드), |(파이프라인), ~(틸드) 문자를 사용해서 표현.
```



### 이상치(outlier)

- 특별히 크거나, 작은 값
  - 얼마나 크거나, 작아야 이상치라고 할 수 있는가?
- 이상치를 찾는 경우가 아니라면, 이상치는 제거하고 분석을 진행한다.



### 중복 데이터 검사

- duplicated 를 이용하여 중복된 자료 검사

- ```
  rawData[ duplicated(subset=['지점']) ]
  ```

- 



### 통계분석

- 판다스에서 제공하는 통계관련된 기능들
  - pivot(엑셀에서 사용하는 피봇 기능과 동일한 기능)
  - crosstab
  - 그룹화 



### 그룹화를 통한 통계적 수치



## 공공데이터를 이용하여 Pandas 사용한 시각화 예정





### 데이터 프레임 조작하기

- 추가,  수정, 삭제
  - 컬럼을 추가하거나, 수정하는데는 큰 기능이 필요하지 않음
- 데이터 프레임에 컬럼이 존재하지 않으면 새로 생성

```
# 기존 데이터에 컬럼 '지역'을 '서울'추가
rawData['지역'] = '서울'
rawData

회차	이름	측정일	몸무게	단위	담당	지점	지역
0	1	홍길동	2020-03-01	76.4	kg	박현경	관악구	서울
1	2	홍길동	2020-03-02	75.7	kg	김현경	관악구	서울
2	3	홍길동	2020-03-03	76.0	kg	최현경	여의도	서울
3	4	홍길동	2020-03-04	NaN	kg	최현경	여의도	서울
4	5	홍길동	2020-03-05	76.2	kg	김현경	강남구	서울
5	6	홍길동	2020-03-06	75.7	kg	최현경	서초구	서울
6	7	홍길동	2020-03-07	NaN	kg	최현경	서초구	서울
7	8	홍길동	2020-03-08	NaN	kg	김현경	서초구	서울
8	9	홍길동	2020-03-09	75.0	kg	김현경	서초구	서울
```



```
# 해당 컬럼이 존재하면 수정이 됨
rawData['지역'] = 'Seoul'
rawData

회차	이름	측정일	몸무게	단위	담당	지점	지역
0	1	홍길동	2020-03-01	76.4	kg	박현경	관악구	Seoul
1	2	홍길동	2020-03-02	75.7	kg	김현경	관악구	Seoul
2	3	홍길동	2020-03-03	76.0	kg	최현경	여의도	Seoul
3	4	홍길동	2020-03-04	NaN	kg	최현경	여의도	Seoul
4	5	홍길동	2020-03-05	76.2	kg	김현경	강남구	Seoul
5	6	홍길동	2020-03-06	75.7	kg	최현경	서초구	Seoul
6	7	홍길동	2020-03-07	NaN	kg	최현경	서초구	Seoul
7	8	홍길동	2020-03-08	NaN	kg	김현경	서초구	Seoul
8	9	홍길동	2020-03-09	75.0	kg	김현경	서초구	Seoul

```



###  컬럼 삭제

- 삭제는 신중하게 진행해야 합니다
  - 귀찮아도 원본 데이터는 삭제하지 않는 것이 좋습니다.

```
rawData.drop(columns=['지역'])


회차	이름	측정일	몸무게	단위	담당	지점	상태
0	1	홍길동	2020-03-01	76.4	kg	박현경	관악구	비만
1	2	홍길동	2020-03-02	75.7	kg	김현경	관악구	정상
2	3	홍길동	2020-03-03	76.0	kg	최현경	여의도	비만
3	4	홍길동	2020-03-04	NaN	kg	최현경	여의도	NaN
4	5	홍길동	2020-03-05	76.2	kg	김현경	강남구	비만
5	6	홍길동	2020-03-06	75.7	kg	최현경	서초구	정상
6	7	홍길동	2020-03-07	NaN	kg	최현경	서초구	NaN
7	8	홍길동	2020-03-08	NaN	kg	김현경	서초구	NaN
8	9	홍길동	2020-03-09	75.0	kg	김현경	서초구	정상
```

```
# 원본은 바뀌지 않습니다
rawData


회차	이름	측정일	몸무게	단위	담당	지점	지역	상태
0	1	홍길동	2020-03-01	76.4	kg	박현경	관악구	Seoul	비만
1	2	홍길동	2020-03-02	75.7	kg	김현경	관악구	Seoul	정상
2	3	홍길동	2020-03-03	76.0	kg	최현경	여의도	Seoul	비만
3	4	홍길동	2020-03-04	NaN	kg	최현경	여의도	Seoul	NaN
4	5	홍길동	2020-03-05	76.2	kg	김현경	강남구	Seoul	비만
5	6	홍길동	2020-03-06	75.7	kg	최현경	서초구	Seoul	정상
6	7	홍길동	2020-03-07	NaN	kg	최현경	서초구	Seoul	NaN
7	8	홍길동	2020-03-08	NaN	kg	김현경	서초구	Seoul	NaN
8	9	홍길동	2020-03-09	75.0	kg	김현경	서초구	Seoul	정상
```



```
# 원본에서 바로 삭제할 수 있습니다.
# 따로, 반환되지 않습니다.
rawData.drop(columns=['지역'], inplace =True)

# inplace 파라미터를 True로 하면, 해당 데이터 프레임에서 바로 삭제

rawData

회차	이름	측정일	몸무게	단위	담당	지점	상태
0	1	홍길동	2020-03-01	76.4	kg	박현경	관악구	비만
1	2	홍길동	2020-03-02	75.7	kg	김현경	관악구	정상
2	3	홍길동	2020-03-03	76.0	kg	최현경	여의도	비만
3	4	홍길동	2020-03-04	NaN	kg	최현경	여의도	NaN
4	5	홍길동	2020-03-05	76.2	kg	김현경	강남구	비만
5	6	홍길동	2020-03-06	75.7	kg	최현경	서초구	정상
6	7	홍길동	2020-03-07	NaN	kg	최현경	서초구	NaN
7	8	홍길동	2020-03-08	NaN	kg	김현경	서초구	NaN
8	9	홍길동	2020-03-09	75.0	kg	김현경	서초구	정상
```



### 행 추가와 수정, 삭제

```
# 행이 존재 
```



### Apply

```
## apply
- 자료를 원하는 대로 다루기는 쉽지 않음.(자료가 정리되어 있지 않고, 워낙 많음)
- 상당히 어려움
- 판다스에서 사용 가능한 반복문 정도로 이해
- 모든 행, 열에 대해서 동일한 함수를 반복적으로 적용
```



## 프레임 합치기

- 서로 다른 두 자료(데이터 프레임)를 하나의 데이터 프레임으로 합치는 방법
- 여러 소스(출처)부터 가져온 데이터를 분석을 하기 위해서는 반드시 하나의 데이터 프레임 이어야만 함.
- 데이터를 합치는 방법

![img](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Foecbm%2FbtqRolfgnC4%2FROZxkKlASUIqWLx1SLd7xK%2Fimg.png)

#### Inner Join

- merge 함수를 통해서 join을 해볼 수 있음
- merge의 기본 동작은 inner join 임.
- Inner Join 은 기본적으로 자료의 크기가 훨씬 줄어들게 됩니다.
  - user_usage : 240개
  - user_device : 270개
    - 두 자료를 하나로 합쳤을 경우 240개를 넘어가지는 않습니다.
    - 양쪽자료 모두에 존재하지 않는 자료가 있다면?

```
display(len(user_usage))
display(len(user_device))
240
272
```

```
pd.merge(left=user_usage, right=user_device, on='use_id')



outgoing_mins_per_month	outgoing_sms_per_month	monthly_mb	use_id	user_id	platform	platform_version	device	use_type_id
0	21.97	4.82	1557.33	22787	12921	android	4.3	GT-I9505	1
1	1710.08	136.88	7267.55	22788	28714	android	6.0	SM-G930F	1
2	1710.08	136.88	7267.55	22789	28714	android	6.0	SM-G930F	1
3	94.46	35.17	519.12	22790	29592	android	5.1	D2303	1
4	71.59	79.26	1557.33	22792	28217	android	5.1	SM-G361F	1
...	...	...	...	...	...	...	...	...	...
154	198.59	90.49	5191.12	23043	28953	android	6.0	SM-G900F	1
155	198.59	90.49	3114.67	23044	28953	android	6.0	SM-G900F	1
156	106.65	82.13	5191.12	23046	29454	android	6.0	Moto G (4)	1
157	344.53	20.53	519.12	23049	29725	android	6.0	SM-G900F	1
158	42.75	46.83	5191.12	23053	20257	android	5.1	Vodafone Smart ultra 6	1
159 rows × 9 columns
```



#### Left join

~~~
## left join
# - left 자료를 기준으로 합쳐줌
# - 결측치가 발생할 수 있음.
# - right 에 없는 자료는 결측치로 채워지게 됨.

pd.merge(left=user_usage, right=user_device, on='use_id', how='left')


outgoing_mins_per_month	outgoing_sms_per_month	monthly_mb	use_id	user_id	platform	platform_version	device	use_type_id
0	21.97	4.82	1557.33	22787	12921.0	android	4.3	GT-I9505	1.0
1	1710.08	136.88	7267.55	22788	28714.0	android	6.0	SM-G930F	1.0
2	1710.08	136.88	7267.55	22789	28714.0	android	6.0	SM-G930F	1.0
3	94.46	35.17	519.12	22790	29592.0	android	5.1	D2303	1.0
4	71.59	79.26	1557.33	22792	28217.0	android	5.1	SM-G361F	1.0
...	...	...	...	...	...	...	...	...	...
235	260.66	68.44	896.96	25008	NaN	NaN	NaN	NaN	NaN
236	97.12	36.50	2815.00	25040	NaN	NaN	NaN	NaN	NaN
237	355.93	12.37	6828.09	25046	NaN	NaN	NaN	NaN	NaN
238	632.06	120.46	1453.16	25058	NaN	NaN	NaN	NaN	NaN
239	488.70	906.92	3089.85	25220	NaN	NaN	NaN	NaN	NaN
240 rows × 9 columns
~~~







```
## Full outer join

pd.merge(left=user_usage, right=user_device, on='use_id', how='outer')


outgoing_mins_per_month	outgoing_sms_per_month	monthly_mb	use_id	user_id	platform	platform_version	device	use_type_id
0	21.97	4.82	1557.33	22787	12921.0	android	4.3	GT-I9505	1.0
1	1710.08	136.88	7267.55	22788	28714.0	android	6.0	SM-G930F	1.0
2	1710.08	136.88	7267.55	22789	28714.0	android	6.0	SM-G930F	1.0
3	94.46	35.17	519.12	22790	29592.0	android	5.1	D2303	1.0
4	71.59	79.26	1557.33	22792	28217.0	android	5.1	SM-G361F	1.0
...	...	...	...	...	...	...	...	...	...
348	NaN	NaN	NaN	23047	29720.0	ios	10.2	iPhone7,1	2.0
349	NaN	NaN	NaN	23048	29724.0	android	6.0	ONEPLUS A3003	3.0
350	NaN	NaN	NaN	23050	29726.0	ios	10.2	iPhone7,2	3.0
351	NaN	NaN	NaN	23051	29726.0	ios	10.2	iPhone7,2	3.0
352	NaN	NaN	NaN	23052	29727.0	ios	10.1	iPhone8,4	3.0
353 rows × 9 columns
```



### 결론(판다스 마무리)

- 데이터 전처리 작업의 핵심은 합치고 , 나누고, 붙이고, 자르는 작업
  - 무한히 반복
  - 인공지능이라는 개념이 나오면서 더더욱 오해가 심해져 감
    - 뭔가 업무가 스마트할 것 같고, 있어보이는 이런 직업
    - 실제 작업은 그렇게 스마트하지 않음.
  - 실제 업무의 80%는 다 이런 작업......





## 시각화

```
import numpy as np
import pandas as pd

# 파이썬의 대표적인 시각화 라이브러리
import matplotlib.pyplot as plt
import seaborn as sns
```





- 자료 분석의 기본은 통계와 그래프
  - 통계는 수치를 통해서 자료를 이해
  - 시각화는 자료에 대한 직관적인 이해
- 시각화 하는 방법은 정해져 있습니다
  - 자료(변수)의 형태에 따라서, 그릴 수 있는 그래프는 이미 결정
  - 자료(변수)의 갯수에 따라서, 그릴 수 있는 그래프는 이미 결정
    - 1변수, 다변수(2변수 이상인 경우)
    - 전통적인 통계적인 분석에서 3변수 이상은 잘 다루지 않음.
    - 현재 빅데이터는 아주아주 많은 변수를 다룬다고 보면 됨.

```
matplotlib

seaborn

plotly(아름답고, 편하다.(특히 3차원) 인터렉티브 가능, 그러나 무거움)
```



## 파이썬에서의 데이터 시각화

- [matplotlib](https://matplotlib.org/)
  - 가장 기본적인 시각화 라이브러리
  - 파이썬에서 제공하는 대부분의 다른 시각화 라이브러리들도 `matplotlib`을 기반으로 구현
- [seaborn](https://seaborn.pydata.org/)
  - matplitlib을 기반으로 만들어진 라이브러리
  - 사용하기 쉽고, 예쁘게 만들어졌어요
  - 주로, 자료의 시각화를 하는 경우에 많이 사용
- [plotly](https://plotly.com/python/)
  - 장점은 예쁘고, 사용하기 편해요, 특히 3차원 그래프도 편하게 그릴수 있습니다.
  - 인터렉티브한 사용이 가능(회전, 확대, 클릭, ... )
  - 단점은 많이 무거워요(느리다)



### 한글화

- 기본적으로 matplotlib은 한글을 지원하지 않습니다.

  - matplotlib이 사용하는 폰트가 한글을 지원하지 않는 폰트를 사용
  - 결국, 폰트를 바꿔줘야 합니다.
  - 콜랩에서는 폰트를 바꾸는 작업이 까다롭습니다.
    - 가상환경(클라우드)이라서, 작업을 하면, 작업 내용이 저장되지 않습니다
    - 폰트를 설치해도, 다음에 다시 실행하면, 폰트를 다시 설치해야 합니다

- ```
  # 일단 그래프 그려볼게요
  x = np.linspace(1, 10, 1000)
  y = x * x ** 2
  plt.plot(x, y)
  plt.title('한글이 나오지 않습니다')
  
  => 출력값 깨짐
  ```

- ```
  따라서 폰트를 설치해야함 (2번씩!)
  
  1. 폰트 설정을 위한 라이브러리 임포트
  from matplotlib import font_manager, rcParams
  
  2. 한글 표현이 가능한 폰트를 설치
  !apt-get install fonts-nanum*
  
  3. 설치된 폰트를 확인
  font_manager.findSystemFonts(fontext='ttf')
  
  4. 사용하고 싶은 폰트 이름 확인.
  font_manager.FontProperties( fname='/usr/share/fonts/truetype/nanum/NanumGothicCoding.ttf').get_name()
  
  5. 폰트 설정하기
  rcParams['font.family'] = 'NanumGothicCoding'
  
  6. - 부호도 깨져서 나오기 때문에, 같이 설정
  rcParams['axes.unicode_minus'] = False
  
  7. 런타임 재시작
  메뉴
  ```

- ```
  로드 중...
  시각화.ipynb
  시각화.ipynb_
  [ ]
  import numpy as np
  import pandas as pd
  
  # 파이썬의 대표적인 시각화 라이브러리
  import matplotlib.pyplot as plt
  import seaborn as sns
  [ ]
  rawData = pd.read_csv('/content/drive/MyDrive/멀티캠퍼스/data/health_2016.csv')
  rawData
  
  
  시각화
  자료 분석의 기본은 통계와 그래프 입니다.
  
  통계는 수치를 통해서 자료를 이해
  시각화는 자료에 대한 직관적인 이해
  시각화 하는 방법은 정해져 있습니다.
  
  자료(변수)의 형태에 따라서, 그릴 수 있는 그래프는 이미 결정
  자료(변수)의 갯수에 따라서, 그릴 수 있는 그래프는 이미 결정
  1변수, 다변수(2변수 이상인 경우)
  전통적인 통계적인 분석에서 3변수 이상은 잘 다루지 않습니다.
  현재 빅 데이터는 아주아주 많은 변수를 다룬다고 보면 됩니다.
  파이썬에서의 데이터 시각화
  matplotlib
  
  가장 기본적인 시각화 라이브러리
  파이썬에서 제공하는 대부분의 다른 시각화 라이브러리들도 matplotlib을 기반으로 구현
  seaborn
  
  matplitlib을 기반으로 만들어진 라이브러리
  사용하기 쉽고, 예쁘게 만들어졌어요
  주로, 자료의 시각화를 하는 경우에 많이 사용
  plotly
  
  장점은 예쁘고, 사용하기 편해요, 특히 3차원 그래프도 편하게 그릴수 있습니다.
  인터렉티브한 사용이 가능(회전, 확대, 클릭, ... )
  단점은 많이 무거워요(느리다)
  한글화
  기본적으로 matplotlib은 한글을 지원하지 않습니다.
  matplotlib이 사용하는 폰트가 한글을 지원하지 않는 폰트를 사용
  결국, 폰트를 바꿔줘야 합니다.
  콜랩에서는 폰트를 바꾸는 작업이 까다롭습니다.
  가상환경(클라우드)이라서, 작업을 하면, 작업 내용이 저장되지 않습니다
  폰트를 설치해도, 다음에 다시 실행하면, 폰트를 다시 설치해야 됩니다.
  [ ]
  # 일단 그래프 그려볼게요
  x = np.linspace(1, 10, 1000)
  y = x * x ** 2
  plt.plot(x, y)
  plt.title('한글이 나오지 않습니다')
  
  
  1.라이브러리 임포트
  [ ]
  # 폰트 설정을 위한 라이브러리 임포트
  from matplotlib import font_manager, rcParams
  2.한글 폰트 설치
  [ ]
  # 한글 표현이 가능한 폰트를 설치
  !apt-get install fonts-nanum*
  
  Reading package lists... Done
  Building dependency tree       
  Reading state information... Done
  Note, selecting 'fonts-nanum-eco' for glob 'fonts-nanum*'
  Note, selecting 'fonts-nanum' for glob 'fonts-nanum*'
  Note, selecting 'fonts-nanum-gothic-light' for glob 'fonts-nanum*'
  Note, selecting 'fonts-nanum-coding' for glob 'fonts-nanum*'
  Note, selecting 'fonts-nanum-extra' for glob 'fonts-nanum*'
  fonts-nanum is already the newest version (20170925-1).
  fonts-nanum-coding is already the newest version (2.5-1).
  fonts-nanum-eco is already the newest version (1.000-6).
  fonts-nanum-extra is already the newest version (20170925-1).
  0 upgraded, 0 newly installed, 0 to remove and 37 not upgraded.
  3.설치된 폰트를 확인
  [ ]
  font_manager.findSystemFonts(fontext='ttf')
  
  ['/usr/share/fonts/truetype/liberation/LiberationSansNarrow-Bold.ttf',
   '/usr/share/fonts/truetype/nanum/NanumSquareRoundB.ttf',
   '/usr/share/fonts/truetype/liberation/LiberationMono-Bold.ttf',
   '/usr/share/fonts/truetype/nanum/NanumSquareB.ttf',
   '/usr/share/fonts/truetype/nanum/NanumBarunpenR.ttf',
   '/usr/share/fonts/truetype/nanum/NanumGothicCoding-Bold.ttf',
   '/usr/share/fonts/truetype/liberation/LiberationMono-Regular.ttf',
   '/usr/share/fonts/truetype/nanum/NanumMyeongjoEco.ttf',
   '/usr/share/fonts/truetype/liberation/LiberationSansNarrow-Regular.ttf',
   '/usr/share/fonts/truetype/nanum/NanumBarunGothicLight.ttf',
   '/usr/share/fonts/truetype/liberation/LiberationSans-Regular.ttf',
   '/usr/share/fonts/truetype/nanum/NanumSquareR.ttf',
   '/usr/share/fonts/truetype/nanum/NanumSquareRoundL.ttf',
   '/usr/share/fonts/truetype/nanum/NanumBrush.ttf',
   '/usr/share/fonts/truetype/nanum/NanumGothicEcoExtraBold.ttf',
   '/usr/share/fonts/truetype/liberation/LiberationSansNarrow-Italic.ttf',
   '/usr/share/fonts/truetype/nanum/NanumPen.ttf',
   '/usr/share/fonts/truetype/liberation/LiberationSerif-Bold.ttf',
   '/usr/share/fonts/truetype/nanum/NanumGothicLight.ttf',
   '/usr/share/fonts/truetype/nanum/NanumMyeongjoBold.ttf',
   '/usr/share/fonts/truetype/humor-sans/Humor-Sans.ttf',
   '/usr/share/fonts/truetype/nanum/NanumMyeongjo.ttf',
   '/usr/share/fonts/truetype/nanum/NanumBarunpenB.ttf',
   '/usr/share/fonts/truetype/nanum/NanumSquareRoundR.ttf',
   '/usr/share/fonts/truetype/liberation/LiberationSansNarrow-BoldItalic.ttf',
   '/usr/share/fonts/truetype/liberation/LiberationSans-Italic.ttf',
   '/usr/share/fonts/truetype/nanum/NanumGothic.ttf',
   '/usr/share/fonts/truetype/liberation/LiberationSans-BoldItalic.ttf',
   '/usr/share/fonts/truetype/nanum/NanumSquareL.ttf',
   '/usr/share/fonts/truetype/liberation/LiberationSerif-BoldItalic.ttf',
   '/usr/share/fonts/truetype/nanum/NanumGothicExtraBold.ttf',
   '/usr/share/fonts/truetype/nanum/NanumMyeongjoEcoBold.ttf',
   '/usr/share/fonts/truetype/nanum/NanumBarunGothic.ttf',
   '/usr/share/fonts/truetype/nanum/NanumMyeongjoExtraBold.ttf',
   '/usr/share/fonts/truetype/nanum/NanumSquareEB.ttf',
   '/usr/share/fonts/truetype/nanum/NanumMyeongjoEcoExtraBold.ttf',
   '/usr/share/fonts/truetype/nanum/NanumGothicEcoBold.ttf',
   '/usr/share/fonts/truetype/liberation/LiberationMono-BoldItalic.ttf',
   '/usr/share/fonts/truetype/nanum/NanumSquareRoundEB.ttf',
   '/usr/share/fonts/truetype/nanum/NanumGothicCoding.ttf',
   '/usr/share/fonts/truetype/nanum/NanumGothicEco.ttf',
   '/usr/share/fonts/truetype/liberation/LiberationMono-Italic.ttf',
   '/usr/share/fonts/truetype/nanum/NanumBarunGothicBold.ttf',
   '/usr/share/fonts/truetype/liberation/LiberationSerif-Regular.ttf',
   '/usr/share/fonts/truetype/liberation/LiberationSerif-Italic.ttf',
   '/usr/share/fonts/truetype/nanum/NanumBarunGothicUltraLight.ttf',
   '/usr/share/fonts/truetype/liberation/LiberationSans-Bold.ttf',
   '/usr/share/fonts/truetype/nanum/NanumGothicBold.ttf']
  4.설치된 폰트의 이름 확인
  [ ]
  font_manager.FontProperties( fname='/usr/share/fonts/truetype/nanum/NanumGothicCoding.ttf').get_name()
  
  
  5.폰트설정
  [ ]
  # 폰트를 변경
  rcParams['font.family'] = 'NanumGothicCoding'
  
  # - 부호도 깨져서 나오기 때문에, 같이 설정
  rcParams['axes.unicode_minus'] = False
  [ ]
  # 설정을 변경했으면, rebuild를 통해서 변경된 설정을 적용
  font_manager._rebuild()
  [ ]
  x = np.linspace(1, 10, 1000)
  y = x * x ** 2
  plt.plot(x, y)
  plt.title('한글이 나오지 않습니다')
  
  
  전체 코드
  아래의 명령을 두 번 실행해야 합니다.
  아래 셀의 명령어들을 한 번 실행한 이후에
  런타임 => 다시 시작 및 모두 실행을 클릭하여 런타임 재시작 이후에 모든 셀의 명령을 다시 실행해 주세요
  
  from matplotlib import font_manager, rcParams
  !apt-get install fonts-nanum*
  rcParams['font.family'] = 'NanumGothicCoding'
  rcParams['axes.unicode_minus'] = False
  font_manager._rebuild()
  
  
  from matplotlib import font_manager, rcParams
  !apt-get install fonts-nanum*
  rcParams['font.family'] = 'NanumGothicCoding'
  rcParams['axes.unicode_minus'] = False
  font_manager._rebuild()
  ```

- 



```
#파이썬의 대표적인 시각화 라이브러리

import numpy as np
import pandas as pd


import matplotlib.pyplot as pit
import seaborn as sns


rawData = pd.read_csv('/content/drive/MyDrive/멀티캠퍼스/data/health_2016.csv')
rawData


기준년도	가입자일련번호	성별코드	연령대코드(5세단위)	시도코드	신장(5Cm단위)	체중(5Kg단위)	허리둘레	시력(좌)	시력(우)	청력(좌)	청력(우)	수축기혈압	이완기혈압	식전혈당(공복혈당)	총콜레스테롤	트리글리세라이드	HDL콜레스테롤	LDL콜레스테롤	혈색소	요단백	혈청크레아티닌	(혈청지오티)AST	(혈청지오티)ALT	감마지티피	흡연상태	음주여부	구강검진 수검여부	치아우식증유무	결손치유무	치아마모증유무	제3대구치(사랑니)이상	치석	데이터공개일자
0	2016	465969	1	8	41	170.0	70.0	74.0	0.7	0.7	1.0	1.0	118.0	70.0	85.0	194.0	97.0	54.0	120.0	14.6	2.0	1.1	31.0	36.0	96.0	3.0	NaN	1	NaN	NaN	NaN	NaN	2.0	20171219
1	2016	565871	1	10	41	160.0	60.0	81.0	1.2	1.0	1.0	1.0	134.0	84.0	105.0	143.0	84.0	33.0	93.0	16.2	1.0	1.0	20.0	23.0	14.0	1.0	NaN	0	NaN	NaN	NaN	NaN	NaN	20171219
2	2016	115718	2	11	11	160.0	55.0	71.0	1.0	1.0	1.0	1.0	129.0	85.0	86.0	203.0	52.0	51.0	141.0	14.0	1.0	0.8	17.0	14.0	20.0	1.0	NaN	1	NaN	NaN	NaN	NaN	0.0	20171219
3	2016	767524	1	6	28	180.0	70.0	79.0	1.0	0.9	1.0	1.0	137.0	78.0	92.0	154.0	53.0	55.0	94.0	14.6	1.0	1.0	21.0	23.0	16.0	1.0	NaN	0	NaN	NaN	NaN	NaN	NaN	20171219
4	2016	482178	2	9	11	160.0	60.0	85.0	0.8	1.2	1.0	1.0	92.0	60.0	90.0	239.0	148.0	46.0	163.0	10.3	1.0	0.9	17.0	12.0	13.0	1.0	NaN	1	NaN	NaN	NaN	NaN	0.0	20171219
...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...	...
995	2016	206725	2	12	41	150.0	60.0	86.0	0.8	0.8	1.0	1.0	117.0	80.0	121.0	226.0	103.0	73.0	132.0	13.6	1.0	0.9	24.0	36.0	34.0	1.0	NaN	0	NaN	NaN	NaN	NaN	NaN	20171219
996	2016	339681	2	12	48	155.0	55.0	66.0	0.8	0.7	1.0	1.0	122.0	85.0	103.0	181.0	70.0	81.0	86.0	11.0	1.0	0.7	24.0	20.0	21.0	1.0	NaN	0	NaN	NaN	NaN	NaN	NaN	20171219
997	2016	653494	2	11	11	155.0	45.0	66.0	1.2	1.0	1.0	1.0	104.0	71.0	80.0	222.0	46.0	61.0	152.0	13.2	1.0	0.8	18.0	14.0	16.0	1.0	NaN	1	NaN	NaN	NaN	NaN	0.0	20171219
998	2016	190984	2	14	41	145.0	50.0	80.0	0.5	0.5	1.0	1.0	133.0	68.0	91.0	164.0	101.0	52.0	91.0	13.9	1.0	0.8	37.0	25.0	17.0	1.0	NaN	0	NaN	NaN	NaN	NaN	NaN	20171219
999	2016	548105	1	6	41	170.0	80.0	85.0	1.2	1.5	1.0	1.0	121.0	72.0	94.0	202.0	82.0	42.0	144.0	15.6	1.0	1.0	18.0	19.0	33.0	3.0	NaN	1	NaN	NaN	NaN	NaN	0.0	20171219
1000 rows × 34 columns
```



