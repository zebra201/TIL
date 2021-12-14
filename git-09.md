## 공공 데이터 분석 및 시각화  2





## 기초 통계 분석

- 관찰(수집)된 자료(현상/상태)에 대해서 통계적 (수치적)으로 처리하고 연구
- 기술통계와 추론통계



### 기술통계

- 기초통계를 이용해서 자료의 성질(특성)을 확인(설명)하는 것
- 자료의 요약된 정보
  - 자료의 자세한 정보까지는 확인할 수 없음.
    - 자료의 세세한 정보까지 확인이 가능하면, 통계 없이 확인 가능한 정도로 아주 작은 파일
    - 즉, 빅데이터에서는 아주아주 큰 파일에 대해서 확인할 수 있는 방법 통계외에는 접근하는 방법조차 없음
    - 자료의 아주 세세한 정보는 통계에 있어서는 큰 관심사가 되지 않습니다.
  - 자료의 커다란 특성을 확인할 수 있습니다.
  - 통계가 아니고는 대용량의 자료를 설명할 방법이 없습니다.

- 통계적 수치(통계량)
  - 중심에 대한 통계(교재 : p.33, 2.1 데이터 중심의 지표)
  - 산포에 대한 통계(교재 : p.39, 2.2 데이터의 산포도 지표)
  - 관계에 대한 통계(교재 : p.70, 3.1 두 데이터 사이의 관계를 나타내는 지표)
  - 형태에 대한 통계



### 중심에 대한 통계

- 자료의 중심에 대한 경향을 나타내는 수치
- 평균 : 자료에 대한 평균(모평균/표본평균/샘플 평균)
- 중앙값 : 자료의 50%에 해당하는 값
  - 자료를 정렬했을 때, 가운데 오는 값
- 최빈값 : 가장 많이 등장한은 값



### 산포에 대한 통계(교재 p.39)

- 자료의 변동성을 나타내는 수치
  - 자료들이 중심으로부터 얼마나 멀리 떨어져 있는가의 정도를 나타내는 수치
- 편차(deviation) : 관측(수집) 값과 평균의 차이
  - 평균(중심)으로부터 얼마나 멀리 떨어져 있는가
- 변동(variation) : 편차의 제곱들의  합
- 분산(variance) : 변동을 데이터의 수로 나눈 값
- 표준편차(Standard Deviation) : 분산의 제곱근



#### 편차 구하기

\# 편차 구하기



\# 관측(수집)값과 평균의 차이

mean = np.mean(scores)

deviation = mean - scores

deviation

```
array([ 13., -14.,  -1.,  14.,  -2.,   7., -10.,   6., -10.,  -3.])
```



------

```
# 변동 구하기
# 편차에서 음수값도 있으므로, 제곱하여 양수로 바꾼 뒤 더한다.
# 편차가 클때마다 패널티를 줌
# (편차)의 제곱들의 합 = 변동

variation = np.sum(deviation ** 2 )
variation

860.0

```



### 표준편차

- 실제 값들의 차이를 구할 수 있음
- 판다스는 이러한 통계량을 한 번에 계산



####  표준화와 편차

- 데이터에서 평균을 빼고 표준편차로 나누는 작업
  - 자료들이 서로 다른 분포를 가지고 있다면, 비교 작업이 어렵다.
  - 자료들이 정규분포임을 가정, 즉 정규분포가 아니라면 최선이 아닐 수 있음.
- 최소/최대

```
# 표준화 작업 -> 표준화와 편차
# (전체 점수 - 평균) / 표준편차

z = (scores - mean) / np.std(scores)
z

array([-1.40182605,  1.50965882,  0.10783277, -1.50965882,  0.21566555,
       -0.75482941,  1.07832773, -0.64699664,  1.07832773,  0.32349832])
```



```
# 표준화 작업 -> 표준화와 편차
# (전체 점수 - 평균) / 표준편차

z = (scores - mean) / np.std(scores)
z
array([-1.40182605,  1.50965882,  0.10783277, -1.50965882,  0.21566555,
       -0.75482941,  1.07832773, -0.64699664,  1.07832773,  0.32349832])
```

```
# 평균이 0이고, 표준편차는 1이 됩니다.

np.mean(z), np.std(z)
(-1.6653345369377347e-17, 0.9999999999999999)
```



#### 편차값

- 평균이 50, 표준편차가 10이 되도록 정규화
- 편차값이 50이면 평균적인 결과
- 50보다 클 수록 상위 결과라는 의미로 해석

```
z=50 + 10 * (scores-mean) / np.std(scores)
z
array([35.98173948, 65.09658825, 51.07832773, 34.90341175, 52.15665546,
       42.45170588, 60.78327732, 43.53003361, 60.78327732, 53.2349832 ])
```

* 결과를 보면 64.0965 나온 학생 성적이 젤 좋다. 평균 50에 비해 훨씬 높음.



### 관계에 대한 통계

- 자료와 자료간의 관계를 나타내는 수치
  - 수치일 뿐, 실제 관계를 수치만 가지고 정확하게 표현할 수 없다.
  - 수치를 가지고 해석하는 것은 분석하는 사람의 몫(관계가 있는가, 없는가)

1. 상관관계

- 공분산(Co-variance)
- 두 변수 사이의 분산
  - 결과적으로 두 변수의 분산이 같이 커지거나, 작아지면 상관성이 있다라고 해석
  - 혹은 분산이 커지는데, 반대로 작아지거나, 분산이 작아지는데, 분산이 커지거나 상관성이 있다로 해석

### 관계에 대한 통계
- 자료와 자료간의 관계를 나타내는 수치
  - 수치일 뿐, 실제 관계를 수치만 가지고 정확하게 표현할 수 없다.
  - 수치를 가지고 해석하는 것은 분석하는 사람의 몫

1. 상관관계
- 공분산(Co-variance)
- 두 변수 사이의 분산 
  - 결과적으로 두 변수의 분산이 같이 커지거나, 작아지면 상관성이 있다라고 해석
  - 혹은 분산이 커지는데, 반대로 작아지거나, 분산이 작아지는에, 분산이 커지거나 상관성이 있다로 해석

$$
cov(x, y) = \frac{\sum(x-\bar{x})(y-\bar{y})
}{n-1}
$$

- 공분산의 해석은 다음과 같다

  - cov > 0  : x 가 큰값(작은값)을 가질 떄, y 도 큰값(작은값)을 가지는 경우

    - x의 분산이 커질 때, y의 분산이 같이 커는 경우
    - x의 분산이 작아질 때, y의 분산이 같이 작아지는 경우
    - 즉, x와 y 사이에 양의 상관성이 있다고 해석
    - 수가 크면 클수록 관계가 있다는 것을 공분산으로 본다

  - cov < 0 : x 와 y 가

    - x의 분산이 작아질 때, y의 분산이 커지거나

    - x의 분산이 커질 때, y의 분산이 작아지거나
    - 이런 경우에는 x 와 y 사이에 음의 상관성이 있다로 해석

  - cov = 0 인경우, 0에 가까운 경우

    - x의 분산과 상관없이 y가 존재하는 경우
      - 음수와 양수가 섞이기 때문에, 0에 가까운 값을 가지게 됩니다
      - 두 변수는 상관성이 적다로 해석

  - 단점

    - 두 변수 사이의 상관성이 낮아도 수치가 크면, 공분산 값이 크게 나올 수 있다
    - 반대로, 두 변수 사이의 상관성이 높아도 수치가 낮으면, 공분산 값은 작게 나올 가능성이 있다.
    - 그래서 나온것이 상관계수
    - 상관계수 : 공분산의 값을 -1 과 1 사이의 값으로 표준화 한 값.
      - **-1 과 1 에 가까울 수록 상관성이 높다고 해석**
      - **0에 가까울 수록 상관성이 낮다고 해석**

2. 인과관계

- 보통 추론통계에서 확인하고자 하는 것이 인과성이 될 수 있습니다.

- 어떤 자료가 다른 자료의 원인이 되는 경우

  - 모든 변수가 무조건 원인이 될 수 있는 것은 아닙니다.

    

- 두 변수의 상관성을 확인하기 좋은 시각화  pair_plot 을 이용해볼 수 있음.

  - pair_plot 은 변수가 많아지면, 굉장히 느려지기 때문에, 주의 해야 합니다.

  ```
  sns.pairplot(df[['english', 'mathematics']])
  ```

![img](data:image/png;base64,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)



### 형태에 대한 통계

- 자료의 분포나 왜곡된 형태
  - 왜도(Skewness) : 편향, 중심을 기준으로 좌우의 데이터가 편향되어 있는 형태를 나타내는 수치
  - 첨도(kurtosis) : 뾰족함의 정도

![img](https://t1.daumcdn.net/cfile/tistory/994FDB3F5D65168524)

- 우리가 원하는 데이터는 4번째 데이터



### 추론 통계

- 표본을 통해서 모집단을 추론하는 과정
- 전체를 다 조사할 수 없으므로 표본을 선정하여 진행 -> 이를 추론 통계라고 함
  - 선택한 표본이 과연 모집단을 대표할 대표성이 있는가?

![img](https://phhp-faculty-cantrell.sites.medinfo.ufl.edu/files/2012/07/big_picture_producing_data.gif)



- 통계를 대하는 자세
  - 마크 트웨인
    - 거짓말의 3가지 종류 : 거짓말, 새빨간 거짓말, 그리고 통계
    - 통계가 모집단의 모든 특징을 설명할 수는 없다.
  - 통계의 한계
    - 일단! 모집단의 특성을 표본을 통해서 통계로 설명한다는 것은 매우 괜찮은 생각입니다.
    - But 표본의 특성이 꼭 모집단과 같을거라는 보장이 없다.
    - 표본이 모집단을 대표하는 특성인지 아닌지, 알 수 있는 방법도 없다.
    - 표본을 통해서 모집단의 평균은 알 수 없지만, 추측은 가능하다
    - 추측이니 99%의 확률로 맞을수도 있지만, 1%의 확률로 틀렸을 가능성 또한 반드시 존재
      - 모집단은 시간이 지나면서 변하기때문, 표본이 모집단을 완벽히 설명하는 것은 불가능.
    - 일반적으로  ML/DL 에서 하려는 건 과거의 데이터를 이용해서 현재나, 미래를 설명하고 싶은 것
  - 수업시간에서 확률과 통계는 모집단을 가정하고 진행
  - 통계를 사용하지 않을 수는 없다
    - 통계가 아니고는 대규모의 데이터를 해석할 수도 없고, 설명도 안됨
    - 자료간의 다소의 차이가 있겠지만, 공통적인 특징은 확인할 수 있습니다.
      - 코로나 백신의 효능을 증명하려면?
        - 화이자나, 얀센등의 효과는 어떻게 나온 것인가?
        - 표본지역을 정해놓고 먼저 접종을 진행한 후에 감염되는 사람 수를 셈.

- 통계는 항상 거짓말로부터 출발한다는 사실을 알고 있어야 함
  - 그래서 스스로 입증해야함
- 잘 쓰면 굉장한 무기가 되지만, 그렇지 않으면?
- 주사위 문제, 동전 던지기
  - 주사위나 동전을 던져서 확률적 데이터를 얻는다고 가정
  - 이 때 이 주사위나, 동전은 공정할 것인가?
- 컴퓨터가 계산하는 난수는 난수가 될 수 없다. 컴퓨터는 1씩 증가(감소)할 수는 있지만





## 모집단과 표본 (교재 p.92)



- 복원 추출과 비복원 추출

- ```
  np.random.choice(scores, 20)
  
  array([85, 75, 80, 91, 73, 64, 62, 46, 64, 54, 83, 72, 91, 64, 74, 52, 92,
         34, 66, 56])
  ```

- ```
  # 책에서는 비복원 추출이라고 함
  np.random.choice(scores, 20, replace=False)
  
  array([90, 74, 68, 65, 58, 43, 50, 69, 55, 64, 68, 61, 85, 56, 60, 57, 96,
         71, 73, 92])
  ```

- ```
  for i in range(5):
    sample = np.random.choice(scores,20)
    print('{} 번째 무작위 추출 얻은 표본평균 : {}'.format(i+1, sample.mean()))
    
  1 번째 무작위 추출 얻은 표본평균 : 73.25
  2 번째 무작위 추출 얻은 표본평균 : 68.05
  3 번째 무작위 추출 얻은 표본평균 : 72.35
  4 번째 무작위 추출 얻은 표본평균 : 73.8
  5 번째 무작위 추출 얻은 표본평균 : 72.3
  ```

- ```
  # 모집단의 평균
  scores.mean()
  ```

- 



