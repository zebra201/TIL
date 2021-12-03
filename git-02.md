## Github 특강 2일차

* get remote -h : remote 관련 도움말

* 리모트 저장소를 많이 저장할 수 있다 -> 이는 하나의 사진(Git)을 여러 장소에 백업할 수 있는 것과 같다
* git remote remove <name> : 하나씩 주소 삭제 가능
* git push origin master : 원격 저장소에 Push 하기
* git log --oneline : 요약하여 log 기록 보기
* (origin/master) : '커밋'한 내용만 Github 에 올라가 있음.(Head->master 는 내 컴퓨터에만 최신임을 의미한다)



#### GIt 푸시 절차 요약

* **시작 전 항상 자신의 위치를 확인할것**
*  수정 -> add -> 커밋 -> push

1. git status
2. git add . (스테이징)
3. git status
4. git commit -m '~' (커밋할 내용 확인)
5. git stats (녹색으로 표시되는지 확인)
6. git log --oneline (로그 기록 요약하여 보기)
7. git push origin master (깃헙에 푸시하기)



### Github 올릴 시 '중요 및 보안 파일 제외하기

| 목    록                         | 내   용                                                      |
| -------------------------------- | ------------------------------------------------------------ |
| ```touch README.md .gitignore``` | 'git init' 실행 전 반드시 사전에  입력할것<br /> 처음 프로젝트 생성시 무조건 같이 생성할 것<br />README.md (대문)<br />.gitignore(보안이 필요한 내용을 모아놓은 곳) |
|                                  |                                                              |

