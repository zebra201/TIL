# Java Script



### 실행환경
1. 웹브라우저에서 실행
  - 웹브라우저가 자바스크립트의 인터프리터의 역할을 수행
  - 웹브라우저의 `개발자 도구`를 이용해서 실행
    - `console`을 이용해서 자바스크립트 코드를 실행
  - URL 입력창을 통한 실행
    - `javascript:alert('hello javascript')`
    - 실행이 안된다면, 브라우저의 보안 설정 때문일겁니다. 
  - HTML 코드 내에서 실행
    - `<script></script>` 내에 자바스크립트 코드를 작성
    - HTML 파일이 브라우저에서 로드될 때, 자동으로 실행

2. node.js를 이용한 실행
  - 브라우저 없이도 자바스크립트 코드를 실행
  - node.js가 인터프리터의 역할을 수행
  - 자바스크립트를 `백엔드`에서 실행하고자 하는 경우에 주로 많이 사용



- (번외) 프로그래밍 언어를 여러개를 한꺼번에 공부할 필요가 없음
  - 어차피 튜링구조를 따르는 언어들은 다 똑같음
  - 결국 중요한 것은 분기, 반복, 함수를 이용해서
  - 내가 원하는 과정을 만들 수 있는가가 중요.

- 데이터 엔지니어가 '엔지니어' 수업과 비슷



```javascript
// 자바스크립트의 한 줄 주석 입니다. 

/*
 멀티라인 주석 입니다. 
 여러줄을 주석으로 처리할 수 있습니다. 
*/

// 변수의 정의와 선언이 따로 있습니다. 

// 변수의 선언
var var1; // var 키워드는 사용하지 않는것이 좋습니다
let var2;

// 변수의 정의
var2 = 10;
console.log(var2);

// 자료의 타입
console.log( typeof 10 );
console.log( typeof 10.0 );
console.log( typeof 'hello'); // 문자열 타입
console.log( typeof true );

// 파이썬에서는 없는 타입
console.log( typeof null );
console.log( typeof undefined );
console.log( typeof NaN ); // Not a Number
console.log( typeof Infinity );

// 연산자
// 몫연산은 없습니다.
console.log( 2 + 3 );
console.log( 2 - 3 );
console.log( 2 * 3 );
console.log( 2 / 3 );
console.log( 2 % 3 );
console.log( 2 ** 3);

// 파이썬에서는 없는 연산자
// 증감연산자
let number = 2;

// 전위식은 증가 먼저하고 나머지 명령을 수행
console.log( ++number ); // number += 1
console.log( --number ); // number -= 1

// 전위식과 후위식의 차이
number = 2;

// 후위식은 명령을 먼저 처리하고 나중에 1을 증가/감소
console.log( number++ ); // number += 1
// 실제로는 1 증가 했습니다. 
console.log(number);

// 비교연산자
// 자바스크립트는 비교할 때 타입은 고려하지 않습니다
console.log( 1 == '1' );

// 자바스크립트에서 타입까지 함께 고려해서 비교
console.log( 1 === '1' );

// 논리연산자
// &&(and), ||(or), !(not)
console.log( true && false );
console.log( true || false ); // shift + 역슬래시(파이프 라인)
console.log( !true );

// 윤년구하기
// 연도가 4로 나누어 떨어지고, 1
// 100으로 나누어 떨어지지 않거나, 
// 400으로 나누어 떨어지면 윤년이다.
let year = 2000;

// if의 형태
// 블록의 시작({)과 끝(})을 중괄호로 감싸서 표현
/*
  if (명제) {

  } else if(명제) {

  } else {

  }
*/

if( (year % 4 == 0) && (year % 100 != 0) || (year % 400 == 0)) {
  console.log('윤년입니다')
} else {
  console.log('평년입니다')
}

// 추가적으로 switch-case문이 존재
// 현대 프로그래밍에서는 거의 안쓰는 추세

let q;
q = 3 / 2;
q = parseInt(q);
console.log(q);

// 새로운 변수는 선언을 먼저 해주든, 선언과 정의를 동시에 하든
// 둘 중에 하나를 해줘야 합니다.
let newVar;

// 배열과 반복
// 자바스크립트는 배열이라는 타입(파이썬의 리스트와 동일)

// let array = []; // 빈 배열 객체
// let array = Array(); // Array 클래스의 생성자를 이용해서 객체 생성
let array = new Array(); // new 연산자를 이용한 Array 객체 생성


array = [10, 20, 30, 40];
console.log( array );
console.log( array[0] );

// 파이썬의 append와 같은 역할
array.push(50);
console.log( array );

// 인덱스 범위를 넘어가는 경우
console.log( array[10] );

// 자바스크립트는 배열의 원소를 이렇게도 추가가 되요
array[10] = 100;
console.log( array );

// 자바스크립트는 배열을 파이썬을 dict 처럼 사용할 수 있습니다. 
// 연관배열이라고 표현
// 수업시간에는 다루지 않지만 파이썬의 dict처럼 map 타입을 지원

let arr = [];

arr['first'] = 10;
console.log( arr );

// for, while, for each

// 파이썬의 for와는 완전히 다른 문법
// while의 또 다른 표현 정도로 이해

// 1부터 10까지 반복
let i = 1;          // 초기값
while( i <= 10 ) {  // 조건
  console.log(i);
  i++;              // 증감
}

// 자바스크립트의 for는 초기값; 조건; 증감; 한줄에 표현
// for( 초기값; 조건; 증감 )
// 표현만 다르고, 동작은 while과 똑같이 동작
for( let i = 1; i <= 10; i++ ) {
  console.log(i);
}

// 파이썬의 for loop와 동일한 동작을 하는 for each
console.log(array);
for (let x of array) {
  console.log( x );
}

// 1부터 n까지의 총합을 구해봅니다. 
let n = 20;
let total = 0;
for(let i = 0; i <= n; i++ ) {
  total += i;
}
console.log(total);

// 자바스크립트 함수의 기능은 동일합니다.
// 자바스크립트는 'function' 키워드로 함수를 정의 합니다.

function func(a, b) {
  return a + b;
}

console.log( func(10, 20) );

// 가변인자
function add() {
  // 가변인자 객체가 따로 존재 합니다.
  // console.log( arguments );
  let sum = 0;
  for(let i = 0; i < arguments.length; i++ ) {
    sum += arguments[i];
  }
  return sum;
}

ret = add(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);
console.log( ret );

// 지역변수, 전역변수
let mem = 10;
function func1() {
  let mem = 20;
}
func1();
console.log( mem );

// 디폴트 파라미터
function func2(a, b = 2) {
  console.log(a, b);
}

func2();

// 자바스크립트의 클래스

class Person {
    // 클래스 변수 아닙니다.
    // 필드 선언(public과 private)
    // 속성 앞에 '#'을 붙여서 private 설정을 할 수 있습니다. 
    #name;
    #age; 

    // 파이썬의 클래스 변수와 같은 기능
    static nation = 'Korea';

    // 생성자
    constructor(name, age) {
      // this는 파이썬의 self와 같은 역할
      // 따로 파라미터로 정의하지 않아도 항상 정의되어 있다.
      this.#name = name;
      this.#age = age;
    };

    // 정적 메소드
    static staticMethod() {
      console.log( Person.nation );
    }

    // getter & setter
    get name() {
      return this.#name;
    }

    set name(name) {
      this.#name = name;
    }

    // class 내에서 메소드를 정의할 때는 'function' 키워드는 생략
    info() {
      console.log(this.#name, this.#age);
    }
}

// 객체 생성
object = new Person('장동건', 22);
object.info();

// 은닉성
// 외부에서는 접근 불가능
// object.#name = '원빈';

// 정적(static) 변수는 클래스 이름으로 접근 가능
console.log( Person.nation );
Person.staticMethod();

// getter와 setter를 사용하는 방법은 파이썬과 동일
object.name = '원빈';
console.log( object.name );
object.info();
```



- 자바스크립트가 HTML 을 어떻게 제어하는지 확인

- 자바스크립트를 쓴다는 것은 DOM(Document Object Model), BOM(Browser Object Model) 이 핵심.



### 기초문법
- 파이썬과 자바스크립트의 차이점을 기준으로 자바스크립트의 특징을 알아 봅니다. 
- `Vanilla Javascript`라고 표현 합니다. 
  - 순수 자바스크립트
  - 자바스크립트만 이렇게 사용하는 경우는 드물고 보통은 라이브러리를 사용하게 됩니다. 
    - vue.js, react, jquery, ... 
- 실습 내용은 아래의 소스코드를 참조해주세요
  - [basic_javascript.js](https://drive.google.com/file/d/18RT-5BLxS2wAOTJqFeYLvOPBUJDzsRLl/view?usp=sharing)



### DOM
- Document Object Model
- 직역하자면 `문서 객체 모델`인데
  - 쉽게는 브라우저에서 보여지는 문서를 하나의 객체로써 다루게 됩니다. 

- 요소(element)
  - 태그와 속성, 내용(content)를 하나의 요소라고 표현을 합니다. 
  - 일반적으로는 태그와 요소를 같은 의미로 많이 사용
  - DOM 에서는 각각의 요소를 계층적인 구조로 표현

![](https://i2.wp.com/oursmalljoy.com/wp-content/uploads/2020/12/DOM.jpg?resize=1200%2C416&ssl=1)

- `document`객체
  - **현재** 브라우저에서 보여지는 문서는 하나의 `document`객체로 표현되어 집니다. 
  - 자바스크립트는 `document`를 통해서 웹의 모든 내용을 전부 제어
  - 모든 요소에 대한 정의와 접근 방법들이 전부 명시되어 있습니다.
  - 요소를 추가, 수정, 삭제
  - 요소에 대한 속성도 추가, 수정, 삭제
  - 이벤트에 대한 제어도 가능합니다. 
    - 마우스 클릭, 키보드 입력, ... 



#### 요소의 선택
- 자바스크립트 `document` 객체내의 요소들을 다룰 수 있는 API를 제공해줍니다. 
  - `document.getElementByTagName('태그이름')`
  - `document.getElementById('Id 속성')`
  - `document.getElementByClassName('class 속성')`
  - `document.querySellectAll('CSS 선택자')`

- 요소 선택을 통한 원하는 요소의 접근 예시

```
document.querySelectorAll('li.nav_item a[data-clk="svc.cafe"]')[0].innerText = '자바스크립트를 통해서 바꿔줄 수 있다는 거죠';
```



#### 계층구조를 이용한 접근
- DOM 구조에서는 각 요소들이 전부 하나의 객체가 됩니다. 
  - `document.요소이름`
- DOM에서 각 노드와의 관계는 다음과 같습니다. 
  - parentNode: 현재 노드의 상위 노드(부모 노드)
  - childNodes: 자식 노드들의 배열
  - firstChild: 첫 번째 자식 노드
  - lastChild: 마지막 자식 노드
  - nextSibling: 다음 형제 노드
  - previousSibling: 이전 형제 노드

- 계층구조를 이용한 원하는 요소의 접근 예시

```javascript
document.body.childNodes[3].childNodes[5].childNodes[5].childNodes[1].childNodes[1].childNodes[1].childNodes[1].childNodes[1].innerText;
```



### BOM
- Browser Object Model
- `브라우저 객체 모델`
  - 브라우저 또한 객체로서 관리

- `window`객체 
  - history: 방문한 페이지에 대한 정보
    - `window.history.back()`: 이전 페이지
    - `window.history.forward()`: 다음 페이지

  - location: 현재 열려있는 페이지에 대한 정보
    - `window.location.href`: 현재 열려있는 페이지의 URL



### 카운터 만들기 실습

#### counter.html

```
<!DOCTYPE html>
<html>
  <head>
  </head>

  <body>
    <h2 id='number'>0</h2>
    <div>
      <button id='increase'>+1</button>
      <button id='decrease'>-1</button>
    </div>

    <script>
      let number = document.getElementById('number');
      let up = document.getElementById('increase');
      let down = document.getElementById('decrease');

      // 요소에 이벤트 달기
      up.onclick = function () {
        let count = number.innerText;
        count = parseInt(count);
        number.innerText = ++count;
      };

      down.onclick = function () {
        let count = number.innerText;
        count = parseInt(count);
        number.innerText = --count;
      }

    </script>
  </body>
</html>
```