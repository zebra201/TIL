### 윈도우에서 리눅스 환경 구축하기

옵션

1. 검색창에 windows 기능 검색 => windsows 기능 켜기 끄기 선택 => Linux용 Windows 하위 시스템 항목 체크 재부팅
2. 검색창에 store 입력 후 Microsoft Store 클릭 => ubuntu 검색 후 ubuntu 20.04 lts 설치
3. 검색창에 ubuntu 검색 => 클릭하면 실행가능 => 편의를 위해 작업표시줄에 고정
4. 리눅스 환경 구성 완료 ~! 윈도우에서도 우분투를 편하게 사용할 수 있습니다
5. 실행한뒤 유저네임, 비밀번호 설정
6. 업데이트 및 필요 패키지 설치

6 - 1 : sudo apt-get update

6 - 2 : sudo apt-get install -y make build-essential \
libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev \
wget curl llvm libncurses5-dev libncursesw5-dev \
xz-utils tk-dev git python-pip

6 - 1 명령어 한 번 실행
6 - 2 명령어 4줄 통째로 한번에 실행



### 리눅스 환경에 파이썬 가상환경 구성

옵션

\## 명령어 뒤에 {} 보일 시 {}는 제외하고 타이핑

1. 리눅스 접속

2. 폴더 생성 mkdir {폴더이름} ## 폴더 만들기
3. cd {폴더이름] ## 폴더로 들어가기
4. code . ## 해당 폴더에 vscode 설치 및 실행
5. vscode 및 리눅스 재실행
    ---------------- 본문 ------------------------------------
6. curl https://pyenv.run | bash ## pyenv 설치
    7.
    export PYENV_ROOT="$HOME/.pyenv"
    export PATH="$PYENV_ROOT/bin:$PATH"
    eval "$(pyenv init --path)"
    eval "$(pyenv virtualenv-init -)"
7. cd ~ 홈 디렉토리로 이동 후 code . ##vscode 실행
8. bashrc 파일 클릭 후 맨 아래에 7번 코드 4줄을 붙여넣은 뒤 저장
9. vscode 및 리눅스 재실행

10. pyenv --version ## 버전확인 잘 나오면 설치 성공



### 장고를 설치해보자

옵션

1. pyenv install --list ## 설치 가능한 파이썬 버전 확인
2. 파이썬 3.10 버전 대는 아직 불안정 ## 밑에서는 예시로 파이썬 버전을 설치
3. pyenv install 3.7.7
4. pyenv install 3.9.4
5. pyenv versions ## 설치한 파이썬 확인 가능
6. pyenv virturalenv {파이썬 버전} {가상 환경 이름}
6 - 1 예시 : pyenv virtualenv 3.7.7 pythonenv
6- 2 삭제 : pyenv uninstall {가상환경이름}
7. pyenv global 3.9.4 ## 글로벌로 설정
8. 원하는 폴더 생성 또는 해당 폴더로 이동 ## 이 폴더에 가상환경 구축
9. pyenv local {가상환경이름}
10. pip install django==2.2
11. django-admin --version ## 장고 버전(2.2)가 나와야 정상
--------------------------장고 실행 테스트 ----------------------------------
12. django-admin startproject {프로젝트 이름}
13. 프로젝트 이름으로 이동해서 ls ## manage.py 파일이 보일 것임
14. python manage.py runserver 실행
15. 웹 브라우저를 열고 주소창에 127.0.0.1:8000 이라고 친 뒤 실행
16. 로켓모양 나오면 장고 실행까지 완료 ~!



## HTML
- Hyper-Text Markup Language
  - `언어`라고 되어 있기는 한데 언어라고 볼 수는 없습니다. 
  - 제어문이 없습니다.(분기, 반복)
  - 정확하게 표현하자면, 문서의 구조를 표현
  - `자바스크립트`가 HTML의 부족한 부분을 대신하고 있다.



### HTML의 기본 구조

```
<!DOCTYPE html> <!-- HTML5 표준을 따르는 문서라는 표시 -->
<html>          <!-- HTML 문서의 시작 -->

    <!-- 
        화면에 보이지 않는 내용들 
        HTML 문서의 정보에 대한 내용들이 주로 들어가게 됩니다.
    -->
    <head>

    </head>

    <!-- 
        화면(웹 브라우저)에 보여지는 모든 내용들
    -->
    <body>
        <h1> 이렇게 해도 잘 되긴 할텐데 ... </h1>
    </body>

</html>
```



### TAG란?
- `<, >`를 이용해서 표현
- 내용(contents)에 대한 타입을 나타내는 용도
- 기본적으로는 1쌍으로 사용이 됩니다.

- 태그의 구조

```
  <opening tag> 내용 </closing tag>
  <tagName /> self closing
```

- 기본적으로 태그들은 계층적인 구조를 같이 표현
  - 최상위 태그는 항상 `HTML`이 됩니다. 
  - `head`와 `body`는 `HTML`의 하위 태그가 됩니다. 
  - 일반적으로 계층 표현을 `들여쓰기`를 이용해서 표현



### 속성(Attribute)
1. 일반속성
  - 태그별로 사용할 수 있는 속성들이 정해져 있습니다.
  - 속성에 따라서 태그를 다르게 표현
  - 태그별로 속성을 전부 외우는 것은 불가능 하니, 아래의 사이트를 참조해서 사용
  - [w3schools.com](https://www.w3schools.com/tags/ref_attributes.asp)

2. 글로벌 속성
  - [w3schools.com](https://www.w3schools.com/tags/ref_standardattributes.asp)
  - 모든 태그에서 공통적으로 사용할 수 있는 속성
  - class, id, ...
  - 이벤트 속성
  - 스타일 속성



### 기본태그
- 문서의 구조를 표현
  - 워드나 한글을 이용해서 작성할 수 있는 내용들
  - 제목, 본문, 표, 그림, 목차, ... 
  - 웹이 발전하면서, 원래 용도 보다는 현재는 응용된 형태로 더 많이 사용



#### Heading
- 제목을 표현하는 태그
- 6단계로 구분
  - `<h1> ~ <h6>`

- 사용법

```
        <h1> 가장 큰 제목 </h1>
        <h3> 중간 제목 </h3>
        <h5> 소제목 </h5>
```



#### Paragraph
- 문단, 본문, 단락, ... 표현 하는 용도
- 일반적으로는 문자를 표현할 때 주로 사용

- 사용법

```
  <p> 일반적으로 텍스트를 표현하는 용도로 사용이 됩니다 </p>
```

- Line Break
  - html은 엔터도 태그로 표현
  - `<br>` 태그 입니다. 내용이 없기 때문에 따로 태그를 닫지 않아도 됩니다. 

- 사용법

```
        <p> 
            일반적으로 텍스트를 표현하는 용도로 사용이 됩니다 <br>
            태그안에 들어있는 텍스트도 CRLF를 사용할 수 없습니다. <br>
        </p>
        텍스트를 반드시 p 태그에 넣을 필요는 없습니다. <br>
        문제는 HTML은 줄바꿈(엔터) 문자로 CRLF를 사용하지 않습니다. <br>
        어? 왜 줄바꿈이 안되지? <br>
```

- Non-breaking Space
  - `&nbsp;, &ensp;, &emsp;`
  - 공백 대신에 사용하는 공백문자
  - 문자열 이스케이프 정도로 해석
    - 예를 들면, 문자열 내에서 엔터를 표현할 수 없기 때문에 `\n`과 같은 문자가 있었던 것 처럼

- 사용법

```
  <p> 공백 문자도 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;HTML은 해석하지 않습니다.</p>
```



#### 리스트
- 목차, 목록 등을 표현할 때 사용할 수 있는 태그
- 현재는 응용해서 다른 형태로 더 많이 사용
- 정렬된 리스트: Ordered List => `<ol>`
- 비정렬 리스트: Unordered List => `<ul>`

- 사용법

```
        <ol> 순서있는 리스트 
            <li> 첫번째</li>
            <li> 두번째</li>
            <li> 세번째</li>
        </ol>

        <ul> 순서없는 리스트 
            <li> 첫번째</li>
            <li> 두번째</li>
            <li> 세번째</li>
        </ul>
```

- ol과 ul의 차이점은 리스트 아이템을 나열할 때 아이템의 순서를 아라비아 숫자로 표현하는 것과 안하는 것의 차이 정도이다. 



#### 이미지
- `<img>`는 내용이 없는 태그중에 하나 입니다. 
- 일반적인 사용법

```
  <img src='url/path' />
```

- `height`, `width` 속성 사용법

```
  <img src='url/path' width='px', height='px' />
```



#### anchor
- 하이퍼-링크
  - 지금의 웹이 만들어지는데 가장 중요한 기능
  - 봇(bot) - 자동화된 프로그램
    - 웹 페이지도 봇에 의해서 자동으로 수집
    - 시드(seed)페이지를 통해서 하이퍼-링크를 통해서 연결되어 있는 다른 웹 페이지를 찾는 방식
    - 전세계에 흩어져 있는 웹 페이지를 전부 수집
    - 이렇게 수집된 페이지에서 사용자가 원하는 페이지를 가장 빠르게 검색해서 제공하는 해주던 사이트가 바로 구글입니다. 

- 사용법

```
  <a> 연결된 페이지의 이름 </a>
```

- 속성
  - href: 연결된 페이지의 주소(URL/URI)
  - target: 연결되 페이지로 이동하는 방식 
    - _self(default): 현재 창에서 해당 페이지로 바로 이동
    - _blank: 새창에서 해당 페이지로 이동
    - _parent: 현재 창보다 상위 창에서 해당 페이지로 이동
    - _top: 최상위 창에서 해당 페이지로 이동



#### Block 기반의 태그
- `DIV`
  - `익명태그`라고 부릅니다.
  - 용도가 정해져 있지 않은 태그로, 활용성이 굉장히 높아서, 많이 사용

- 그 외의 블록기반의 태그들
  - p, ol, ul, li, table, h

- 실습 예제

```
<!DOCTYPE html>
<html style='border: 0.5px dashed blue'>
    <head>
    </head>

    <body style='border: 0.5px dashed red'>

        <!-- 블록기반의 태그들 -->
        <h1 style='border: 0.5px dashed green'> Heading </h1>
        <p style='border: 0.5px dashed yellow'> Paragraph </p>
        
        <div style='border: 0.5px dashed black; width:100px; height:100px'>
        </div>
        <div style='border: 0.5px dashed black; width:100px; height:100px'>
        </div>
        <div style='border: 0.5px dashed black; width:100px; height:100px'>
        </div>
    </body>
</html>
```

- 스타일 속성
  - border: 경계선(테두리)
    - 선의 굵기가 0.5px이고, 타입이 점선이고 컬러 지정
- 각 태그들이 브라우저에서 차지하는 영역을 확인
  - 즉, 지금 보여지는 박스들이 각 태그각 화면에서 차지하는 영역
- 블록기반의 태그의 특징
  - 태그 하나가 전체 너비를 모두 차지
  - 다음 라인에 태그의 내용이 표시
  - 즉, 블록기반의 태그들은 화면에 배치가 될 때, 한 줄에 하나씩 배치가 됩니다. 



#### Inline 기반의 태그
- `<span>`
  - 인라인 기반의 대표적인 태그로 `div`와 마찬가지로 `익명태그`중에 하나 입니다. 
  - 기본적으로는 div와 거의 동일하지만, `inline`기반이 차이점 입니다. 

- 그 외 인라인 기반의 태그들
  - img, a, ... 

- 실습용 코드

```
<!DOCTYPE html>
<html style='border: 0.5px dashed blue'>
    <head>
    </head>

    <body style='border: 0.5px dashed red'>

        <!-- 블록기반의 태그들 -->
        <h1 style='border: 0.5px dashed green'> Heading </h1>
        <p style='border: 0.5px dashed yellow'> Paragraph </p>
        
        <div style='border: 0.5px dashed black; width:100px; height:100px'>
            div1
        </div>
        <div style='border: 0.5px dashed black; width:100px; height:100px'>
            div2
        </div>
        <div style='border: 0.5px dashed black; width:100px; height:100px'>
            div3
        </div>

        <!-- 인라인 기반의 태그들 -->
        <span style='border: 0.5px dashed black;'>
            span1
        </span>
        <span style='border: 0.5px dashed black;'>
            span2
        </span>
        <span style='border: 0.5px dashed black;'>
            span3
        </span>
    </body>
</html>
```

### 레이아웃
- div를 통해서 배치
- semantic tag를 사용해서 배치
- table을 이용해서 배치
  - HTML5 표준부터 사용하지 않는 방법



#### iframe
- inline frame의 약자로, 웹 페이지 안에 또 다른 웹 페이지를 표현할 수 있는 방법

- 사용법 

```
<iframe src='https://www.daum.net'></iframe>
```



#### semantic tag
- HTML5 표준에서 새로 제공하는 태그들
  - 레이아웃만을 위해서 제공하는 태그
  - 태그가 의미를 가지고 있다는 뜻인데

- 레이아웃을 나타내는 시멘틱 태그
  - header, nav, main, section, article, asise, footer


- HTML5 표준 이전의 방식

```
<div id="header" role="banner">
<div id="container" role="main">
<div id="footer" role="contentinfo">
```

- HTML5 표준 이후의 방식

```
<header id="daumHead" class="head_daum" data-tiara-layer="header">
<main id="daumContent">
<footer id="daumFoot" class="foot_daum" data-tiara-layer="footer">
```

- 시맨틱 태그를 사용해도 배치가 자동으로 되지는 않습니다. 
  - 그냥 의미적으로만 사용될 뿐입니다. 
  - CSS를 통해서 직접 배치를 따로 해줘야 합니다. 

```
        <header >
            헤더 부분 입니다. 
        </header>
            
        <main>
            메인 부분 입니다. 
        </main>
        <footer>
            푸터 부분 입니다. 
        </footer>
```



### 입력 태그들
- 사용자로부터 웹 페이지를 입력을 받아서 서버에 전달하기 위한 용도



#### form
- POST 방식으로 서버에 데이터를 전달
  - 가장 많이 사용되는 경우가 로그인 처리와 같은 경우가 있습니다. 

- form 태그의 일반적인 형태는 다음과 같습니다. 

```
<form action='' method=''>
  <!-- 여러가지 입력 태그들이 올 수 있습니다 -->
</form>
```

- form의 주요 속성
  - action: 입력 데이터를 처리할 서버(백엔드/웹어플션케이션)의 URL
  - method: 데이터를 전달하는 방법(GET/POST)
    - GET 방식: URL/URI를 통해서 전달
      - 보내려는 데이터가 매우 쉽게 외부에 노출되기 때문에 보안에 취약하다고 얘기합니다. 
      - 별로 중요하지 않은 데이터를 전송하는 경우
    - POST 방식: 데이터를 별도의 방식으로 전달
      - 보내려는 데이터가 외부에 쉽게 노출되지 않음
      - 암호화된 통신(https)을 사용하면 보내려는 데이터가 암호화 되기 때문에, 더욱더 확인하기가 어렵다



#### input
- 입력받고자 하는 형태를 정의
  - text, radio button, checkbox, select, button, submit, ... 

- 실습용 코드 

```
        <input type='text' />
        <select>
            <option value='첫번째'>1</option>
            <option value='두번째'>2</option>
            <option value='세번째'>3</option>
        </select>
        <input type='hidden' />

        <input type='button' value='버튼'/>
        <input type='submit' value='제출'/>
```

- 속성
  - name
    - 각, 입력요소를 구분하는 중요한 속성
    - 데이터를 서버에 전달할 때, 변수의 이름으로 사용
    - 반드시, 정의해주는게 좋습니다. 



## 샘플 코드

```
<header class="header">
  <div class="container">
    <h1 class="title">Float and <br>Position</h1>
    <span class="span"> <em> Position is blar blar ... </em> for poisition is ... </span>
    <ul class="list">
			<li class="list-item">Overview</li>
			<li class="list-item">Download</li>
			<li class="list-item">News</li>
			<li class="list-item">Community</li>
		</ul>
  </div>
</header>

<div class="column1">
	<h2>column 1</h2>
	Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque ultrices vitae quam nec tempor. Aliquam et mattis tellus, vel aliquet ligula. In sem urna, tincidunt id molestie sit amet, viverra nec ligula. Orci varius natoque penatibus et magnis dis
	parturient montes, nascetur ridiculus mus. Phasellus pharetra ornare dolor non condimentum. Morbi pharetra ut felis sed gravida. Maecenas vitae dapibus lectus, et egestas erat. Vivamus at leo gravida odio scelerisque vestibulum ut at neque. Pellentesque
	dictum turpis sit amet leo blandit sagittis. Curabitur iaculis ex in dui vehicula rhoncus. Pellentesque vehicula libero mi, eu pharetra augue venenatis et. Maecenas ac erat sit amet purus interdum faucibus et quis nisl. Aenean in justo et nisl pharetra
	tempor. Suspendisse at bibendum urna, ut sagittis nibh. Aliquam lacinia quam porta, luctus enim ac, facilisis erat.

</div>
<div class="column2">
	<h2>column 2</h2>
	Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque ultrices vitae quam nec tempor. Aliquam et mattis tellus, vel aliquet ligula. In sem urna, tincidunt id molestie sit amet, viverra nec ligula. Orci varius natoque penatibus et magnis dis
	parturient montes, nascetur ridiculus mus. Phasellus pharetra ornare dolor non condimentum. Morbi pharetra ut felis sed gravida. Maecenas vitae dapibus lectus, et egestas erat. Vivamus at leo gravida odio scelerisque vestibulum ut at neque. Pellentesque
	dictum turpis sit amet leo blandit sagittis. Curabitur iaculis ex in dui vehicula rhoncus. Pellentesque vehicula libero mi, eu pharetra augue venenatis et. Maecenas ac erat sit amet purus interdum faucibus et quis nisl. Aenean in justo et nisl pharetra
	tempor. Suspendisse at bibendum urna, ut sagittis nibh. Aliquam lacinia quam porta, luctus enim ac, facilisis erat.

</div>
<div class="column3">
	<h2>column 3</h2>
	Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque ultrices vitae quam nec tempor. Aliquam et mattis tellus, vel aliquet ligula. In sem urna, tincidunt id molestie sit amet, viverra nec ligula. Orci varius natoque penatibus et magnis dis
	parturient montes, nascetur ridiculus mus. Phasellus pharetra ornare dolor non condimentum. Morbi pharetra ut felis sed gravida. Maecenas vitae dapibus lectus, et egestas erat. Vivamus at leo gravida odio scelerisque vestibulum ut at neque. Pellentesque
	dictum turpis sit amet leo blandit sagittis. Curabitur iaculis ex in dui vehicula rhoncus. Pellentesque vehicula libero mi, eu pharetra augue venenatis et. Maecenas ac erat sit amet purus interdum faucibus et quis nisl. Aenean in justo et nisl pharetra
	tempor. Suspendisse at bibendum urna, ut sagittis nibh. Aliquam lacinia quam porta, luctus enim ac, facilisis erat.

</div>

<div class="footer">
		<h2>footer</h2>
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque ultrices vitae quam nec tempor. Aliquam et mattis tellus, vel aliquet ligula. In sem urna, tincidunt id molestie sit amet, viverra nec ligula. Orci varius natoque penatibus et magnis dis
	parturient montes, nascetur ridiculus mus. Phasellus pharetra ornare dolor non condimentum. Morbi pharetra ut felis sed gravida. Maecenas vitae dapibus lectus, et egestas erat. Vivamus at leo gravida odio scelerisque vestibulum ut at neque. Pellentesque
	dictum turpis sit amet leo blandit sagittis. Curabitur iaculis ex in dui vehicula rhoncus. Pellentesque vehicula libero mi, eu pharetra augue venenatis et. Maecenas ac erat sit amet purus interdum faucibus et quis nisl. Aenean in justo et nisl pharetra
	tempor. Suspendisse at bibendum urna, ut sagittis nibh. Aliquam lacinia quam porta, luctus enim ac, facilisis erat.

</div>
```



## CSS
- Casecade Style Sheet
- html 페이지에 추가적으로 디자인 서식을 적용하고 싶은 경우에 사용
- 적용할 수 있는 방법 3가지
  1. inline style
    - html 태그에 `style` 속성을 이용하는 방법
    - 왠만하면 사용하지 않는 것이 좋습니다.
    - 우선순위가 제일 높습니다. 
  2. internal style
    - html 코드 내에 `<style>` 태그를 이용해서 표현
  3. external style
    - 대부분은 외부 스타일 시트를 이용해서 CSS를 적용



### 외부 스타일 시트
- 스타일 시트 파일을 html 페이지에서 가져와서 적용하는 방법

```
  <link rel='stylesheet' type='text/css' href='css 파일의 경로' />
```



### CSS의 구조

```
선택자(Selector) {
  속성이름1: 속성값1 속성값2 속성값3 ... ;
  속성이름2: 속성값1 ... ;
}
```

- 선택자: 스타일을 적용할 태그가 됩니다.
- 속성과 속성값은 `:(콜론)`으로 구분
- 속성값이 여러개인 경우는 `(공백)`으로 구분
- 속성과 속성은 `;`으로 구분



#### 글자와 관련된 속성들
- 폰트, 글자 크기, 글자 색, ... 
- 상속
  - CSS의 속성이 부모 태그에서 자식 태그로 상속되어서 하위 태그들도 동일한 속석이 적용
  - 무조건 상속이 되지는 않습니다. 
  - 글자와 관련된 속성들은 상속이 가능한 대표적인 속성 입니다. 

```
html {
    font-size: 20px;
    font-family: '나눔고딕코딩', '굴림체', 'serif', 'sans-serif';
    line-height: 0.8; /* 줄간격 */
}
```

- 글꼴은 `font-family`로 지정할 수 있습니다. 
  - 로컬(브라우저가 실행되는 환경)에 해당 글꼴이 설치되어 있어야만 사용이 가능합니다. 
  - 없는 글꼴을 사용하는 경우에 화면에 깨질 수 있습니다. 
    - 여러개의 글꼴을 지정
    - 글꼴들이 전부 없는 경우에는 기본글꼴이 사용될 수 있도록
    - serif, sand-serif, monospace, ... 



#### 색상과 관련된 속성들
- 글자색, 배경색, 배경이미지, ... 

```
    color: #006400;            /* 글자색 */
    background-color: black;   /* 배경색 */
```



### Selector
- CSS-Selector
  - 스타일을 원하는 태그에 정확하게 적용하기 위한 여러가지 방법
  - CSS에서만 사용하지 않고, 다른 곳에서도 동일한 셀렉터를 지원
- 가장 기본적으로는 `태그 셀렉터`, `id 셀렉터`, `class 셀렉터` 등이 많이 사용

- 우선순위
  - `Id 선택자 > class 선택자 > 태그 선택자`



#### 전체 선택자
- `*` (와일드 카드)
- html 문서내의 모든 태그를 선택
- 사용법

```
* { 
  ...
}
```



#### 태그 선택자
- 태그 이름으로 선택
  - 동일한 모든 태그에 동일하게 스타일이 적용

- 사용법

```
태그이름 { 
  ....
}
```



#### ID 선택자
- Id 속성에 따라서 선택

- 사용법

```
  #id속성값 {
    ...
  }
```

- id 속성은 html 페이지 전체에서 단 하나의 값을 가져야 합니다.
  - 예를 들면 예제에서의 `column1` 이라는 id 속성값은 하나만 존재



#### Class 선택자
- `Class` 속성에 따라서 선택
- 사용법

```
  .class속성값 {
    ...
  }
```

- id 속성은 유일한 값을 가져야 하며, class 속성은 중복 가능한 값을 가질 수 있습니다. 
  - class 속성과 id 속성을 같이 정의할 수 있습니다. 



#### 그룹 선택자
- 여러개의 선택자를 동시에 사용(콤마로 구분)
- 사용법

```
선택자, 선택자, 선택자, ... {
  ...
}

```



#### 하위 선택자
- 태그들의 계층 구조를 이용해서 선택
- 공백으로 표현
  - 선택자 SP 선택자

- 사용법

```
상위선택자 하위선택자 {
  ...
}
```

- 하위의 개념은 상위 선택자의 모든 하위 태그들을 전부 포함



#### 자식 선택자
- 하위 선택자와 마찬가지로 계층구조를 이용한 선택자
- `>` 표현
  - `직계 자손`: 바로 밑에 하위 태그만 자식으로 인정

- 사용법

```
상위선택자 > 하위선택자 {
  ...
}
```



### box-model
- html에서 태그는 영역에 대해서 상자로 표현할 수 있는데 이를 `박스모델`이라고 합니다. 
- 박스모델과 관련된 속성이
  - margin
    - margin-left
    - margin-right
    - margin-top
    - margin-bottom
  - border
  - padding
    - padding-left
    - padding-right
    - padding-top
    - padding-bottom
  - 내용

- border를 기준으로 바깥쪽 여백을 `margin`이라고 하고, 안쪽(내용과 border 사이) 여백을 `padding`이라고 합니다. 



## 레이아웃 구성 실습

### navigation bar 만들어보기
- `ul`을 이용해서 표현
  - `li` 태그들은 `블록기반`이 아닌, `인라인기반`으로 표현 해줘야 합니다. 

- `display` 속성을 이용해서 변경할 수 있습니다. 

```
.list-item {
  display: inline;
}
```



### position
- 태그의 위치를 지정
  - static(default)
    - 블록과 인라인에 따라서 자동으로 위치가 결정 됩니다. 
    - 즉, 기본흐름에 따른 배치
  - relative
    - top, bottom, left, right 속성을 이용해서 원래 위치를 변경
    - 원래 자기 자신의 위치에서 변경
  - absolute
    - top. bottom, left, right 속성을 이용해서 원래 위치를 변경
    - 자기 자신을 감싸는 태그에 대해 상대적으로 위치를 지정
    - 상위 태그의 position이 static이면 해당하지 않는다.
      - `body`를 기준으로 위치가 정해집니다. 
  - fixed
    - 고정 위치를 지정
    - 스크롤링이 되어도 항상 같은 영역에 표시
    - top, bottom, left, right 속성으로 위치를 지정



- 현재까지 작성된 CSS

```
.title {
    display: inline;
}

.list {
    display: inline;
    position: absolute;
    left: 500px;
    bottom: 15px;
}

.list-item {
    display: inline;
}

.container {
    border: 1px dashed blue;
    position:relative;
}

.span {
    position: absolute;
    top: 30px;
    left: 180px;
}
```
