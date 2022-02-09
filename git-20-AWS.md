# AWS 서버 구축

![image-20220209115202537](git-20-AWS.assets/image-20220209115202537.png)





- 서울 서버의 경우 과부하가 심하여 <u>**도쿄 리전 사용**</u>(실습이 아직 어려움)
- 서버 운영시간은 평일 ~18:30, 주말 추석 연휴, 멘토링 일정 없는 토요일과 일요일 사용 불가.

- 데이터 엔지니어 코드 : 665820218380

- ID : e-lab30
- PW : multi1234

- putty 로그인시, ip, port 을 save 한뒤, auth 경로로 프라이빗키(ppk, 개별 다운로드) 지정 후 로그인
  - id : lab30 	(패스워드는 필요 없음)
- 인스턴스 시작(자신과 맞는 이름) 후 새로고짐 진행



```
# 주피터 내에서

conda info --envs
conda activate python3 (권장)

# 백그라운드에서 실행 (입력시 port 는 개인번호 입력)
 nohup jupyter-notebook --ip=0.0.0.0 --no-browser --port=8930 &

# 주피터 주소로 들어가기
 원격접속 쥬피터 노트북 접속 url : http://3.113.137.203:8930
 
# 비밀번호 : multi1234!
```

- 백그라운드 실행 후 putty 는 종료해도 상관 없음
- 서버 접속 IP (putty) : 3.113.137.201
- 원격접속 쥬피터 노트북 접속 url : http://3.113.137.203:8930
- python --version
- conda activate python3
- conda create -n test python=3.6 jupyter tensorflow

```
# 주피터 상에서
!pip install pandas

import pandas as pd
```

![image-20220209151444046](git-20-AWS.assets/image-20220209151444046.png)



------------------------------------------------------------

2번째 프로젝트 (3조 - 이현호, 권민찬, 김소영, 이세진)





```
import pandas as pd

캐글에서 데이터를 받은 뒤 aws 에 업로드

titanic_df = pd.read_csv("./Data/titanic_train.csv")
```

