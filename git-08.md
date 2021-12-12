## 시각화(맷플랏, 시본) 2



### 그래프를 그리는 기준

- 통계분석 에서도 동일한 기준으로 분석을 합니다.

  1. 자료의 형태(변수의 종류)
    - 범주형과 연속형 자료로 구분해볼 수 있습니다. 
    - 질적변수 Vs. 양적변수
      - 질적변수(Qualitative Variable): 변수의 값이 비 수치적, 특정 카테고리에 포함되는 경우
        - 명목형: 특정 범주에 포함되지만, 순위를 갖지 않는 경우(성별, 혈액형, ... )
        - 순위형: 특정 범주에 포함되지만, 순위를 갖는 경우(성적, 등급, ... )
      - 양적변수(Quantitative Variable): 변수의 값이 수칙적이고, 연속적인 경우(키, 나이, ... )
        - 이산형: 셀 수 있는 경우(정수인 경우) 
        - 연속형: 셀 수 없는 경우(실수인 경우)

  2. 자료의 차원
    - 변수의 개수는 차원이 됩니다.
    - 차원이 높으면, 시각화를 해볼 수 없습니다. 
      - 최대 2차원의 화면에서 3차원 까지만 나타낼 수 있습니다. 
    - 1차원
      - 일변수(일변량): 변수 하나에 대한 시각화
      - 변수의 분포 등을 확인
    - 2차원
      - 이변수(이변량): 변수와 변수의 관계를 확인하고 싶은 경우
        - 연속형 변수와 연속형 변수
        - 연속형 변수와 이산형 변수
        - 이산형 변수와 이산형 변수



2. 자료의 차원

- 변수의 개수는 차원이 됩니다.
- 차원이 높으면, 시각화를 해볼 수 없습니다.
  - 최대 2차원의 화면에서 3차원 까지만 나타낼 수 있습니다.
- 1차원
  - 일변수(일변량): 변수 하나에 대한 시각화
  - 변수의 분포 등을 확인
- 2차원
  - 이변수(이변량): 변수와 변수의 관계를 확인하고 싶은 경우
    - 연속형 변수와 연속형 변수
    - 연속형 변수와 이산형 변수
    - 이산형 변수와 이산형 변수



## 1차원 시각화

- 변수 1개인 경우
  - 범주형인 경우: countplot(빈도 확인)
  - 연속형인 경우: histplot, displot

```
rawData.describe(include='all').T
```



### 범주형

- 샘플 자료에서는 비수치적인 자료는 없습니다.
  - 수치적인 자료들(이산형) 중에서 범주형에 해당하는 변수를 확인
  - `흡연상태`, `구강검진 수검여부`, `치석`, `성별코드`

```
rawData['흡연상태'].unique()
array([3., 1., 2.])

```

### 이산형

- 셀수 있는 형태의 정수형 자료







# 공공데이터 분석 시각화



### 프로젝트

- 조별 구성
- 주제가 있다면 => 주제 공개 => 관심이 있다면 참여
- 익명으로 진행



### 첫 프로젝트 주제

- 공공데이터 분석 및 시각화



### 코딩 테스트 준비 어떻게 하는가

- 결론 : 많은 문제를 풀어봐야 하는것은 맞는데
- 아무것도 모르는데 무조건 문제를 푼다고 해결이 되진 않음
  - 혼자서 하게되는 경우 시간이 매우 오래 걸릴 것
  - 문제 푸는 방법을 배우고 그 다음에 많은 문제를 풀어보면서 익히는 것
- 코딩 테스트 스터디  =>  강사님에게 의견 전달