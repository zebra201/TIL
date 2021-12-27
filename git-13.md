## 웹기초 진행중



- 현재까지 작성된 CSS

```
header {
    background-color: #006699;
    color: #FFFFFF;
}

.title {
    display: inline;
}

.list {
    display: inline;
    position: absolute;
    right: 20px;
    bottom: 25px;
    text-align: right;
}

.list-item {
    display: inline-block;
    /* inline 속성은 너비 속성을 가지지 않습니다 */
    /* inline-block은 inline 속성이면서, block 속성을 같이 사용 */
    width: 300px;
    font-size: 30px;
    text-transform: uppercase;
}

.container {
    position:relative;
    margin-top: 20px;
    margin-bottom: 20px;
    padding-top:20px;
    padding-bottom:20px;
}

.span {
    position: absolute;
    top: 50px;
    left: 180px;
}
```



### Float
- 부유한다는 의미로, 원래 목적은 그림과 글자의 배치를 위하여 나온 기능 
- 레이아웃 기능으로 더 많이 사용
- 속성값
  - left: 태그를 왼쪽에 배치하기 위해 사용
  - right: 오른쪽에 배치하기 위해 사용
  - none: 태그를 띄우지 않음
  - inherit: 부모 태그로부터 상속

- float 속성을 사용하는 경우에는 `display` 속성은 무시 됩니다. 
  - 즉, 인라인 기반이든, 블록 기반이든 무시되고, float에 따라서 배치가 바뀌게 됩니다.



### Clear
- 이전에 사용했던 float 속성을 바꿔줍니다.
  - float 속성을 사용하면 원래 배치의 흐름이 바뀌게 되는데
  - 다시 원래대로 돌리고 싶은 경우에 사용

- 속성값
  - none: clear 설정을 하지 않는 것과 같습니다.
  - left: 왼쪽을 취소
  - right: 오른쪽을 취소
  - both: 양쪽 다 취소



# 실습
- 게시판 만들기 실습
  - 로그인 페이지
  - 게시글 목록 페이지
  - 게시글 작성
  - 게시글 수정



## 부트스트랩
- 전문가가 아니어도 전문가처럼 보이는 방법
- [부트스트랩 공식 홈페이지](http://bootstrapk.com/)
  - 트위터 디자이너들이 공개한 디자인 서식
  - 이를 이용하면, 쉽게 전문가 처럼 디자인이 가능
  - [부트스트랩 다운로드](https://github.com/twbs/bootstrap/releases/download/v3.3.2/bootstrap-3.3.2-dist.zip)



## login.css

```
html, body {
  height:100%;
}

body {
  display: flex;
  align-items: center;
}

.form-control {
  width: 300px;
}
```



## login.html

```
<!DOCTYPE html>

<html>
  <head>
    <!-- bootstrap css 적용 -->
    <link type='text/css' rel='stylesheet' href='../css/bootstrap.min.css' />
    <link type='text/css' rel='stylesheet' href='../css/bootstrap-theme.min.css' />
    <link type='text/css' rel='stylesheet' href='../css/login.css' />
  </head>

  <body>
    <div class='container'>
      <form class='form-horizontal' method='post' action=''>
        <div class='form-group'>
          <label for="inputId" class="col-xs-4 col-md-4 control-label">ID</label>
          <div class='col-xs-4 col-md-4'>
            <input class="form-control" type='text' name='id' id='inputId'>
          </div>
        </div>
        <div class='form-group'>
          <label for="inputPw" class="col-xs-4 col-sm-4 control-label">PW</label>
          <div class='col-xs-4 col-md-4'>
            <input class="form-control" type='password' name='pw' id='inputPw'>
          </div>
        </div>
        <div class='form-group'>
          <div class='col-xs-offset-4 col-md-offset-4 col-xs-10 col-md-10'>
            <button class="btn btn-default" type='submit'> 로그인 </button>
          </div>
        </div>
      </form>
    </div>
  </body>
</html>
```



## write.html

```
<!DOCTYPE html>
<html>
  <head>
    <link type='text/css' rel='stylesheet' href='../css/bootstrap.min.css' />
    <link type='text/css' rel='stylesheet' href='../css/bootstrap-theme.min.css' />
  </head>

  <body>
    <div class='container'>
      <form>
        <div class='row'>
          <!-- 날짜 -->
          <div class="col-md-4">
            <input type='date' class='col-md-4'>
          </div>

        </div>

        <div class='row'>
          <!-- 작성자 -->
          <div class="col-md-4">
            <input type='text' class='col-md-4'>
          </div>
        </div>

        <div class='row'>
          <!-- 게시글 -->
          <div class="col-md-8">
            <textarea class="form-control" rows="20"></textarea>
          </div>
        </div>
      </div>
    </form>
  </body>

</html>
```



## list.html

```
<!DOCTYPE html>
<html>
  <head>
    <link type='text/css' rel='stylesheet' href='../css/bootstrap.min.css' />
    <link type='text/css' rel='stylesheet' href='../css/bootstrap-theme.min.css' />
  </head>

  <body>
    <table class='table'>
      <thead>
        <tr>
          <th> 시간 </th>
          <th> 작성자 </th>
          <th> 제목 </th>
        </tr>
      </thead>

      <tbody>
        <tr>
          <td> 2021-12-21 </td>
          <td> 임종혁 </td>
          <td> 오늘 수업은 여기까지... </td>
        </tr>
        <tr>
          <td> 2021-12-20 </td>
          <td> 임종혁 </td>
          <td> 왜 아무도 안보이죠? </td>
        </tr>
        <tr>
          
        </tr>
        <tr>
          
        </tr>
      </tbody>
      
    </table>
  </body>
</html>
```



