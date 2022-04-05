# 프로젝트3_Dart 언어(Flutter)



### 생성자

```dart
void main() {
  // Idol 클래스로 블랙핑크를 만듦.
  // 인스턴스 부분
  Idol blackpink = Idol(
    '블랙핑크',
    ['지수', '제니', '리사', '로제'],
  );

  Idol blackpink2 = Idol(
    '블랙핑크',
    ['지수', '제니', '리사', '로제'],
  );

  print(blackpink.name);
  print(blackpink.members);
  blackpink.sayHello();
  blackpink.introduce();

//   Idol bts = Idol(
//     'BTS',
//     ['RM', '진', '슈가', '제이홉', '지민', '뷔', '정국'],
//   );

  Idol bts = Idol.fromList([
    ['RM', '진', '슈가', '제이홉', '지민', '뷔', '정국'],
    'BTS',
  ]);

  print(bts.name);
  print(bts.members);
  bts.sayHello();
  bts.introduce();
  print("---------------------------------------");
}

// immutable 프로그래밍(변경불가능)

// constructor(생성자) = 설계도
class Idol {
  final String name;
  final List<String> members;

  // constructor(생성자)
//   Idol(String name, List<String> members)
//       : this.name = name,
//         this.members = members;
  // 간단한 코드
  Idol(this.name, this.members);

  Idol.fromList(List values)
      : this.members = values[0],
        this.name = values[1];

  void sayHello() {
    print("안녕하세요 ${this.name}입니다");
  }

  void introduce() {
    print("저희 멤버는 ${this.members}가 있습니다.");
  }
}

```



### Getter and Setter

```dart
void main() {
  // Idol 클래스로 블랙핑크를 만듦.
  // 인스턴스 부분
  Idol blackpink = Idol(
    '블랙핑크',
    ['지수', '제니', '리사', '로제'],
  );


  Idol bts = Idol.fromList([
    ['RM', '진', '슈가', '제이홉', '지민', '뷔', '정국'],
    'BTS',
  ]);

  
  print(blackpink.firstMember);
  print(bts.firstMember);
  
  //setter 사용(아래 설정 이후)
  blackpink.firstMember = '현호';
  bts.firstMember = '아이언맨';
  
  print(blackpink.firstMember);
  print(bts.firstMember);
  print(blackpink.getFirstMember());
  
  print("---------------------------------------");
}

// getter / setter
// 데이터를 가져올 때 / 데이터를 설정할 때


// constructor(생성자) = 설계도
class Idol {
  String name;
  List<String> members;

  // 간단한 코드
  Idol(this.name, this.members);

  Idol.fromList(List values)
      : this.members = values[0],
        this.name = values[1];

  void sayHello() {
    print("안녕하세요 ${this.name}입니다");
  }

  void introduce() {
    print("저희 멤버는 ${this.members}가 있습니다.");
  }
  
  
  // setter 와 동일(뉘앙스가 다름)
  String getFirstMember(){
    return this.members[0];
  }
  
  // getter
  String get firstMember{
    return this.members[0];
  }
  
  // setter (하나의 파라미터만 들어감)
  set firstMember(String name){
    this.members[0] = name ;
  }
  
}

```



### Private 변수(_다른 파일에서 불러와서 사용이 안됨)

```dart
void main() {
  // Idol 클래스로 블랙핑크를 만듦.
  // 인스턴스 부분
  _Idol blackpink = _Idol(
    '블랙핑크',
    ['지수', '제니', '리사', '로제'],
  );


  _Idol bts = _Idol.fromList([
    ['RM', '진', '슈가', '제이홉', '지민', '뷔', '정국'],
    'BTS',
  ]);

  
  print(blackpink.firstMember);
  print(bts.firstMember);
  
  //setter 사용(아래 설정 이후)
  blackpink.firstMember = '현호';
  bts.firstMember = '아이언맨';
  
  print(blackpink.firstMember);
  print(bts.firstMember);
  print(blackpink.getFirstMember());
  
  print("---------------------------------------");
}

// getter / setter
// 데이터를 가져올 때 / 데이터를 설정할 때


// constructor(생성자) = 설계도
class _Idol {
  String name;
  List<String> members;

  // 간단한 코드
  _Idol(this.name, this.members);

  _Idol.fromList(List values)
      : this.members = values[0],
        this.name = values[1];

  void sayHello() {
    print("안녕하세요 ${this.name}입니다");
  }

  void introduce() {
    print("저희 멤버는 ${this.members}가 있습니다.");
  }
  
  
  // setter 와 동일(뉘앙스가 다름)
  String getFirstMember(){
    return this.members[0];
  }
  
  // getter
  String get firstMember{
    return this.members[0];
  }
  
  // setter (하나의 파라미터만 들어감)
  set firstMember(String name){
    this.members[0] = name ;
  }
  
}

```



### 상속(inheritance)

- 상속을 하면 부모클래스의 속성은 자식클래스를 넘어가지만, 자식클래스의 속성을 부모로 주지는 않으며, 자식들간의 속성 역시 공유하지 않는다.

```dart
void main() {
  print('--------- Idol ---------');
  Idol apink = Idol(name: '에이핑크', membersCount: 5);

  apink.sayName();
  apink.sayMembersCount();

  print('--------- BoyGroup ---------');
  BoyGroup bts = BoyGroup('BTS', 7);

  bts.sayMembersCount();
  bts.sayName();
  bts.sayMale();
  
  print('----------- GirlGroup -----------');
  GirlGroup redVelvet = GirlGroup('Red Velvet', 5);
  
  redVelvet.sayMembersCount();
  redVelvet.sayName();
  redVelvet.sayFemale();
  
  print('--------- Type comparison ----------');
  print(apink is Idol);
  print(apink is BoyGroup);
  print(apink is GirlGroup);
  
  print('--------- Type comparison2 ----------');
  print(bts is Idol);
  print(bts is BoyGroup);
  print(bts is GirlGroup);
  
  print('--------- Type comparison3 ----------');
  print(redVelvet is Idol);
  print(redVelvet is BoyGroup);
  print(redVelvet is GirlGroup);
}

// 상속 - inheritance
// 상속을 받으면 부모 클래스의 모든 속성을 자식클래스가 부여받는다.

class Idol {
  String name;
  int membersCount;

  // 생성자
  Idol({
    required this.name,
    required this.membersCount,
  });

  void sayName() {
    print('저는 ${this.name}입니다.');
  }

  void sayMembersCount() {
    print('${this.name}은 ${this.membersCount}명의 멤버가 있습니다.');
  }
}

class BoyGroup extends Idol {
  BoyGroup(
    String name,
    int membersCount,
  ) : super(
          name: name,
          membersCount: membersCount,
        );

  // 예시) 자식 함수에 속성 하나(함수)를 추가해보자
  void sayMale() {
    print('저는 남자 아이돌입니다');
  }
}

class GirlGroup extends Idol {
  GirlGroup(
    String name,
    int membersCount,
  ) : super(
          name: name,
          membersCount: membersCount,
        );
  void sayFemale(){
    print('저는 여자 아이돌입니다');
  }
}

```



### Override (덮어쓰다)

```dart
void main() {
  // tt라는 변수이름 만들어보기
  TimesTwo tt = TimesTwo(2);
  print(tt.calculate());

  TimesFour tf = TimesFour(2);
  print(tf.calculate());
}

// method - function (클래스 내에 있는 함수)
// override - 덮어쓰다(우선시하다)

class TimesTwo {
  final int number;

  TimesTwo(
    this.number,
  );

  //method
  int calculate() {
    return number * 2;
  }
}

// 오버라이드는 상속했을 경우에만 가능
class TimesFour extends TimesTwo {
  TimesFour(
    int number,
  ) : super(number);

  @override
  int calculate() {
    // return number * 4; (아래와 동일)
    // return super.number * 4;
    // 부모의 함수를 그대로 받앙온 뒤 자식함수도 실행
    return super.calculate() * 2;
  }
}

```



### Static

```
// ignore_for_file: prefer_const_constructors

import 'dart:convert';
import 'package:flutter/material.dart';
import 'package:flutter/services.dart';
import 'package:sm7/utilities/constants(login).dart';

class EmptyCheck extends StatefulWidget {
  @override
  _EmptyCheckState createState() => _EmptyCheckState();
}

final Map<String, dynamic> jsonString2 = {
  'table1': {
    //테이블1
    'chair': {
      'up': 2, //0빈자리, 1마스크한사람, 2마스크안한사람, 3error
      'down': 0
    },
    'object': {
      "notebook": 0, //노트북 갯수
      "book": 0, //책 갯수
      "bag": 0, //가방 갯수
      "cup": 0 // 컵 갯수
    }
  },
  'table2': {
    //테이블2
    'chair': {
      'up': 1, //0빈자리, 1마스크한사람, 2마스크안한사람, 3error
      'down': 1
    },
    'object': {
      "notebook": 1, //노트북 갯수
      "book": 0, //책 갯수
      "bag": 2, //가방 갯수
      "cup": 2 // 컵 갯수
    }
  },
  'table3': {
    //테이블3
    'chair': {
      'up': 1, //0빈자리, 1마스크한사람, 2마스크안한사람, 3error
      'down': 3
    },
    'object': {
      "notebook": 1, //노트북 갯수
      "book": 0, //책 갯수
      "bag": 2, //가방 갯수
      "cup": 2 // 컵 갯수
    }
  }
};
//바뀐거로

class myPainter extends CustomPainter {
  String target;
  myPainter(this.target);

  void _emptytable(Canvas canvas, Size size) {
    Paint paint = Paint()
      ..color = Colors.grey
      ..strokeCap = StrokeCap.round
      ..style = PaintingStyle.fill;
    canvas.drawRect(Offset(-80, -30) & const Size(160, 60), paint);
  }

  void _table(Canvas canvas, Size size) {
    Paint paint = Paint()
      ..color = Colors.blue
      ..strokeCap = StrokeCap.round
      ..style = PaintingStyle.fill;
    canvas.drawRect(Offset(-80, -30) & const Size(160, 60), paint);
  }

  void _noperson(Canvas canvas, Size size) {
    Paint paint = Paint()
      ..color = Colors.grey
      ..style = PaintingStyle.fill;
    canvas.drawCircle(Offset(0, 0), 20, paint);
  }

  void _person_mask(Canvas canvas, Size size) {
    Paint paint = Paint()
      ..color = Colors.blue
      ..style = PaintingStyle.fill;
    canvas.drawCircle(Offset(0, 0), 20, paint);
  }

  void _person_nomask(Canvas canvas, Size size) {
    Paint paint = Paint()
      ..color = Colors.red
      ..style = PaintingStyle.fill;
    canvas.drawCircle(Offset(0, 0), 20, paint);
  }

  void table1_person(Canvas canvas, Size size) {
    //p2, table1
    if (target == "p1" &&
        jsonString2["table1"]["chair"].keys.elementAt(0) == "up") {
      //p1, table1, up
      if (jsonString2["table1"]["chair"]["up"] == 0) {
        _noperson(canvas, size);
      } else if (jsonString2["table1"]["chair"]["up"] == 1) {
        _person_mask(canvas, size);
      } else if (jsonString2["table1"]["chair"]["up"] == 2) {
        _person_nomask(canvas, size);
      } else {
        _person_nomask(canvas, size);
      }
    } else if (target == "p2" &&
        jsonString2["table1"]["chair"].keys.elementAt(1) == "down") {
      //p2, table, down
      if (jsonString2["table1"]["chair"]["down"] == 0) {
        _noperson(canvas, size);
      } else if (jsonString2["table1"]["chair"]["down"] == 1) {
        _person_mask(canvas, size);
      } else if (jsonString2["table1"]["chair"]["down"] == 2) {
        _person_nomask(canvas, size);
      } else {
        _person_nomask(canvas, size);
      }
    }
  }

  void table2_person(Canvas canvas, Size size) {
    if (target == "p3" &&
        jsonString2["table2"]["chair"].keys.elementAt(0) == "up") {
      if (jsonString2["table2"]["chair"]["up"] == 0) {
        _noperson(canvas, size);
      } else if (jsonString2["table2"]["chair"]["up"] == 1) {
        _person_mask(canvas, size);
      } else if (jsonString2["table2"]["chair"]["up"] == 2) {
        _person_nomask(canvas, size);
      } else {
        _person_nomask(canvas, size);
      }
    } else if (target == "p4" &&
        jsonString2["table2"]["chair"].keys.elementAt(1) == "down") {
      if (jsonString2["table2"]["chair"]["down"] == 0) {
        _noperson(canvas, size);
      } else if (jsonString2["table2"]["chair"]["down"] == 1) {
        _person_mask(canvas, size);
      } else if (jsonString2["table2"]["chair"]["down"] == 2) {
        _person_nomask(canvas, size);
      } else {
        _person_nomask(canvas, size);
      }
    }
  }

  void table3_person(Canvas canvas, Size size) {
    if (target == "p5" &&
        jsonString2["table3"]["chair"].keys.elementAt(0) == "up") {
      if (jsonString2["table3"]["chair"]["up"] == 0) {
        _noperson(canvas, size);
      } else if (jsonString2["table3"]["chair"]["up"] == 1) {
        _person_mask(canvas, size);
      } else if (jsonString2["table3"]["chair"]["up"] == 2) {
        _person_nomask(canvas, size);
      } else {
        _person_nomask(canvas, size);
      }
    } else if (target == "p6" &&
        jsonString2["table3"]["chair"].keys.elementAt(1) == "down") {
      if (jsonString2["table3"]["chair"]["down"] == 0) {
        _noperson(canvas, size);
      } else if (jsonString2["table3"]["chair"]["down"] == 1) {
        _person_mask(canvas, size);
      } else if (jsonString2["table3"]["chair"]["down"] == 2) {
        _person_nomask(canvas, size);
      } else {
        _person_nomask(canvas, size);
      }
    }
  }

  void table1(Canvas canvas, Size size) {
    // if (target == 't1' && jsonString2["table1"].keys.elementAt(1) == "object") {
    //   if ((jsonString2["table1"]['object']['notebook'] == 0) &&
    //       (jsonString2["table1"]['object']['book'] == 0) &&
    //       (jsonString2["table1"]['object']['bag'] == 0) &&
    //       (jsonString2["table1"]['object']['cup'] == 0)) {
    //     _emptytable(canvas, size);
    //   } else {
    //     _table(canvas, size);
    //   }
    // }
  }

  void table2(Canvas canvas, Size size) {
    // if (target == 't2' && jsonString2["table2"].keys.elementAt(1) == "object") {
    //   if ((jsonString2["table2"]['object']['notebook'] == 0) &&
    //   (jsonString2["table2"]['object']['book'] == 0) &&
    //   (jsonString2["table2"]['object']['bag'] == 0) &&
    //   (jsonString2["table2"]['object']['cup'] == 0)) {
    //     _emptytable(canvas, size);
    //   } else {
    //     _table(canvas, size);
    //   }
    // }
  }

  void table3(Canvas canvas, Size size) {
    // if (target == 't3' && jsonString2["table1"].keys.elementAt(1) == "object") {
    //   if ((jsonString2["table3"]['object']['notebook'] == 0) &&
    //   (jsonString2["table3"]['object']['book'] == 0) &&
    //   (jsonString2["table3"]['object']['bag'] == 0) &&
    //   (jsonString2["table3"]['object']['cup'] == 0)) {
    //     _emptytable(canvas, size);
    //   } else {
    //     _table(canvas, size);
    //   }
    // }
  }

  @override
  void paint(Canvas canvas, Size size) {
    for (int i = 0; i < 3; i++) {
      if (jsonString2.keys.elementAt(i) == "table1") {
        //table1일경우
        table1_person(canvas, size);
        table1(canvas, size);
      } else if (jsonString2.keys.elementAt(i) == "table2") {
        //table2일경우만
        table2_person(canvas, size);
        table2(canvas, size);
      } else {
        table3_person(canvas, size);
        table3(canvas, size);
      }
    }
  }

  @override
  bool shouldRepaint(covariant CustomPainter oldDelegate) {
    return false;
  }
}

class _EmptyCheckState extends State<EmptyCheck> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("좌석 & 마스크 확인", style: TextStyle(fontSize: 20.0)),
        backgroundColor: Colors.black,
        centerTitle: true,
        elevation: 0.0,
      ),
      body: AnnotatedRegion<SystemUiOverlayStyle>(
        value: SystemUiOverlayStyle.light,
        child: GestureDetector(
          onTap: () => FocusScope.of(context).unfocus(),
          child: Stack(
            children: <Widget>[
              Container(
                height: double.infinity,
                width: double.infinity,
                decoration: BoxDecoration(
                  gradient: LinearGradient(
                    begin: Alignment.topCenter,
                    end: Alignment.bottomCenter,
                    colors: const [
                      Color.fromARGB(195, 0, 0, 0),
                      Color.fromARGB(215, 0, 0, 0),
                      Color.fromARGB(235, 0, 0, 0),
                      Color.fromARGB(252, 0, 0, 0),
                    ],
                    stops: const [0.1, 0.4, 0.7, 0.9],
                  ),
                ),
              ),
              SafeArea(
                child: Center(
                    child: Column(
                        mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                        children: <Widget>[
                      SizedBox(
                        height: 80,
                      ),
                      Container(
                        // alignment: Alignment.center,
                        child: CustomPaint(
                          painter: myPainter("p1"),
                        ),
                      ),
                      SizedBox(
                        height: 50,
                      ),
                      Container(
                        // alignment: Alignment.center,
                        child: CustomPaint(
                          painter: myPainter("t1"),
                        ),
                      ),
                      SizedBox(
                        height: 50,
                      ),
                      Container(
                        // alignment: Alignment.center,
                        child: CustomPaint(
                          painter: myPainter("p2"),
                        ),
                      ),
                      SizedBox(
                        height: 70,
                      ),
                      Container(
                        // alignment: Alignment.center,
                        child: CustomPaint(
                          painter: myPainter("p3"),
                        ),
                      ),
                      SizedBox(
                        height: 50,
                      ),
                      Container(
                        // alignment: Alignment.center,
                        child: CustomPaint(
                          painter: myPainter("t2"),
                        ),
                      ),
                      SizedBox(
                        height: 50,
                      ),
                      Container(
                        // alignment: Alignment.center,
                        child: CustomPaint(
                          painter: myPainter("p4"),
                        ),
                      ),
                      SizedBox(
                        height: 70,
                      ),
                      Container(
                        // alignment: Alignment.center,
                        child: CustomPaint(
                          painter: myPainter("p5"),
                        ),
                      ),
                      SizedBox(
                        height: 50,
                      ),
                      Container(
                        // alignment: Alignment.center,
                        child: CustomPaint(
                          painter: myPainter("t3"),
                        ),
                      ),
                      SizedBox(
                        height: 50,
                      ),
                      Container(
                        // alignment: Alignment.center,
                        child: CustomPaint(
                          painter: myPainter("p6"),
                        ),
                      ),
                      SizedBox(
                        height: 80,
                      ),
                    ])),
              )
            ],
          ),
        ),
      ),
    );
  }
}

```

