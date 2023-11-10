# Flutter_Grammar
### 플러터 문법 정리본

<br>
<br>

# 1. dart 기본문법

<br>
<br>


# Object Oriented Programming(객체지향 프로그래밍)
<br>


## 1. 콘솔 출력하기
    ```
    print("Hello World);
    ```
<br>
<br>

## 2. 변수 선언하기
    ```
    // variable(변수)
    // 타입지정X
    // var => (보통 타입지정이 어려울때 사용)
    // 변수를 재할당 할때 선언되어있는 타입과 다른타입 할당불가
    var name = '여준우';

    // 변수타입 추출
    print(name.runtimeType);
    ```

    <br>
    <br>

    #### 변수타입
    
    <br>

    ```
    // integer(정수)
    int number1 = 10;
    int number2 = 20;

    print(number1 + number2);
    print(number1 - number2);
    print(number1 * number2);
    print(number1 / number2);


    =====================================================


    // double(실수)
    double number3 = 7.5;
    double number4 = 3.5;

    print(number3 + number4);
    print(number3 - number4);
    print(number3 * number4);
    print(number3 / number4);


    =====================================================


    // Boolean(맞다 / 틀리다)
    bool isTrue = true;
    bool isFalse = false;

    print(isTrue);
    print(isFalse);


    =====================================================


    // String(문자)
    String name = '여준우';
    String job = '개발자';

    print(job + ' ' + name);
    print('${job} ${name}');
    print('$job $name');


    =====================================================


    // dynamic 
    // var과 유사, var와 달리 재할당을 할때 다른 타입 할당가능

    var job = '개발자';
    // job = 10; => Error

    dynamic name = '여준우';
    name = 1; // OK
    ```

<br>
<br>

## 3. 변수 null 허용여부 설정
    ```
    // nullable - null이 될 수 있다.
    // non-nullable - null이 될 수 없다.
    // null - 아무런 값도 있지 않다.
    String name = '여준우';

    print(name);
    // name = null; => Error


    // ?: null 값을 허용한다.
    String? job = '개발자';
    job = null // OK


    // !: 절대 null 값이 아니다.
    print(name!);
    ```

<br>
<br>

## 4. Final과 Const
    ```
    // 변수 타입 앞쪽에 붙임
    // 상수
    // final과 const를 사용하면 var 키워드 생략가능
    final name = '여준우';

    print(name);

    const job = '개발자;

    print(job);
    ```

    <br>
    <br>

    #### final과 const의 차이

    <br>

    ```
    // 코드가 실행되는 순간의 시간을 출력 (코드 실행시 값 할당)
    DateTime today = DateTime.now();
    print(today); // 2023-11-04 10:38:36.257


    // final: build 타임의 값을 알고 있지 않아도 됨
    // const: build 타임의 값을 알고 있어야함
    final DateTime now = DateTime.now();

    print(now); // OK

    // 빌드과정에 now2에 값이 할당 되어있지 않기 때문에 에러
    // const DateTime now2 = DateTime.now(); => Error
    ```


<br>
<br>

## 5. Operator
    ```
    // operator(연산자)

    // var number = 5;
    // number++; => number에 +1
    // number--; => number에 -1

    // var num = m;
    // num += n; -> num의 n만큼 더하겠다.
    // num -= n; -> num의 n만큼 뻬겠다.
    // num #= n; -> num의 n만큼 곱하겠다.
    // num /= n; -> num의 n만큼 나누겠다.


    var number = 10;

    number++; // 11

    number--; // 10

    number += 5; // 15

    number -= 5; // 10

    number *= 2; // 20

    number /= 2; // 10



    // num ??= n; -> num의 값이 null이면 n적용, 아님 기존값 유지.

    double number2 = 4.0;

    number2 = 2.0; // 2.0

    number2 ?? = 3.0;
    // number이 nul이면 3.0 할당
    // number이 null이 아니면 2.0 유지


    =====================================================


    // number1 < number2 -> number1이 number2보다 작으면 true 아님 false
    // number1 > number2 -> number1이 number2보다 크면 true 아님 false
    // number1 <= number2 -> number1이 number2보다 작거나 같으면 true 아님 false
    // number1 >= number2 -> number1이 number2보다 크거나 같으면 true 아님 false
    // number1 == number2 -> number1이 number2랑 같으면 true 아님 false
    // number1 != number2 -> number1이 number2랑 다르면 true 아님 false

    val number1 = 10;
    val number2 = 20;

    print(number1 < number2); // true
    print(number1 > number2); // false
    print(number1 <= number2); // true
    print(number1 >= number2); // false
    print(number1 == number2); // false
    print(number1 != number2); // true


    =====================================================


    // 타입비교
    var number = 1;

    print(number is int); // true
    print(number is String); // false

    // 반대
    print(number is! int); // false
    print(number is! String); // true


    =====================================================


    // && - and 조건
    // || - or 조건

    bool result = 12 > 10 && 1 > 0 && 3 > 0;

    print(result); // true

    bool result2 = 12 > 10 && 0 > 1;

    print(result2); // false

    bool result3 = 12 > 10 || 1 > 0;

    print(result3); // true

    bool result4 = 12 > 10 || 0 > 1;

    print(result4); // true

    bool result5 = 12 < 10 || 0 > 1;

    print(result5); // false 
    ```


<br>
<br>

## 6. List, Map, Set
    ```
    // List
    List<String> blackPink = ['제니', '지수', '로제', '리사'];
    List<int> numbers = [1, 2, 3, 4, 5, 6];

    print(blackPink); // ['제니', '지수', '로제', '리사']
    print(numbers); // [1, 2, 3, 4, 5, 6]


    // index (순서) 
    // 0부터 시작
    print(blackPink[0]); // 제니
    print(blackPink[1]); // 지수
    print(blackPink[2]); // 로제
    print(blackPink[3]); // 리사
    print(blackPink[4]); // Error


    // 값 추가
    blackPink.add('준우');
    print(blackPink); // ['제니', '지수', '로제', '리사', '준우']

    // 값 삭제
    blackPink.remove('리사');
    print(blackPink); // ['제니', '지수', '로제', '준우']

    // 원하는 값 인덱스 찾기
    print(blackPink.indexOf('준우')); // 3


    =====================================================


    // Map
    // Key / Value
    Map<String, String> dictionary = {
        'Harry Potter': '해리포터',
        'Ron Weasley': '론 위즐리',
        'Hermione Granger': '헤르미온느 그레인저',
    };

    Map<String, bool> isHarryPotter = {
        'Harray Potter': true,
        'Ron Weasley': true,
        'Ironman': false,
    };


    // Map에 데이터 추가하는 함수
    // 스파이더맨 추가
    isHarryPotter.addAll({
        'Spiderman': false,
    });

    // key값으로 데이터 가져오기
    print(isHarryPotter['Ironman']);

    // 임의적 Map에 데이터 추가
    isHarryPotter['Hulk'] = false;

    // 값 변경
    isHarryPotter['Spiderman'] = true;

    // 데이터 삭제
    isHarryPotter.remove('Harry Potter');

    // key값만 가져오기
    print(isHarryPotter.keys);

    // value값만 가져오기
    print(isHarryPotter.values);


    =====================================================


    // Set
    // 알아서 중복값 삭제
    final Set<String> names = {
        'wnsdnn',
        'Flutter',
        'Black Pink',
        'Flutter'
    };

    print(names);
    // { 'wnsdnn', 'Flutter', 'Black Pink' }


    // 값 추가
    names.add('Jenny');

    // 값 삭제
    names.remove('Jenny');

    // 값이 있는지 확인
    names.remove('wnsdnn'); // true
    ```

<br>
<br>

## 7. enum
    ```
    enum Status {
        approved, // 승인
        pending, // 대기
        rejected // 거절
    }
    // 사용하는 이유
    // - 정확히 이 3개의 값만 존재한다는걸 알려준다. (타인, 미래의 나한테)
    // - 정확히 알맞는 값만 맞게 사용할 수 있게 한다. (오타 방지)

    // 타입처럼 쓸수 있다
    Status status = Status.pending;

    if (status == Status.appeoved) {
        print('승인입니다.');
    } else if(status == Status.pending) {
        print('대기입니다.');
    } else if(status == Status.rejected) {
        print('거절입니다.');
    }
    ```

<br>
<br>

## 7. Function
    ```
    // 세계의 숫자 (x, y, z)를 더하는 함수
    // 앞에 funciton 키워드 필요없음
    // parameter / argument - 매개변수
    // positional parameter - 순서가 중요한 파라미터
    void addNumbers(inx x, [int? y = 5, int? z = 10]) {
        int sum = x + y + z;
        print('sum: $sum');
    }



    // optional parameter - 있어도 되고 없어도 되는 파라미터
    // 값이 안넘어오면 기본값이 적용됨
    void addNumbers(inx x, [int? y = 5, int? z = 10]) {
        int sum = x + y + z;
        print('sum: $sum');
    }



    // named parameter - 이름이 있는 파라미터 (순서가 중요하지 않다.)
    // required - 안넣으면 optional parameter처럼 안넣어도 되는 값으로 처리한다. (대신 기본값 있어야함)
    void addNumbers({
        required int x,
        required int y,
        int z = 30,
    }) {
        int sum = x + y + z;
        print('sum: $sum');
    }

    // 함수 사용하는 방법
    addNumbers(x: 10, y: 20, z: 30);
    addNumbers(y: 60, z: 70, x: 40);

    // optional, named 섞어서 사용가능
    void addNumbers( int x, {
        required int y,
        int z = 30,
    }) {
        int sum = x + y + z;
        print('sum: $sum');
    }



    // arrow function - 화살표 함수
    int addNumbers( int x, {
        required int y,
        int z = 30,
    }) => x + y + z;
    


    // 함수에 return 타입 있어야함
    void: 그냥 실행 (리턴타입 X)
    int: int형의 데이터 반환
    String: String형의 데이터 반환
    ... 그외의 다른 모든 타입들도 적용가능



    =====================================================



    // typedef
    void main() {
        Operation operation = add;

        int result = operation(10, 20, 30);

        print(result); // 60

        operation = subtract;

        int result2 = operation(10, 20, 30);

        print(result2); // -40

        int result3 = calculate(30, 40, 50, add);

        print(result3); // 120

        int result4 = calculate(40, 50, 60, subtract);

        print(result4); // -70
    }

    // signature
    typedef Operation = int Function(int x, int y, int z);

    // 더하기
    int add(int x, int y, int z) => x + y + z;


    // 빼기
    int subtract(int x, int y, int z) => x - y - z;

    // 계산
    int calculate(int x, int y, int z, Operation operation) {
        return operation(x, y, z);
    }
    ```
    
<br>
<br>

## 8. Class
    ```
    void main() {
        // Dart언어에서는 클래스 생성시 'new' 키워드 생략 가능 (다른 언어에서는 'new' 기워드 필수)
        // const를 붙이면 const로 선언할수 있는 값들만 지정할수 있음 (constructor에 const 키워드가 붙어야지 const로 선언가능)
        // _Idol처럼 class 앞에 '_'를 붙이면 private 속성을 부여한 것과 같다.
        _Idol blackPink = _Idol(
            '블랙핑크', 
            ['지수', '제니', '리사', '로제']
        );
        
        //   Idol blackPink2 = const Idol(
        //     '블랙핑크', 
        //     ['지수', '제니', '리사', '로제']
        //   );
        
        
        // const로 선언시 같은 값들이 들어가면 같은 인스턴스로 인식
        //   print(blackPink == blackPink2);
        
        // print('-------------');
        
        // final 키워드를 사용해서 멤버변수의 값을 못 바꾸게 함
        // blackPink.name = '여준우'; // Error
        
        print(blackPink.name);
        print(blackPink.members);
        blackPink.sayHelo();
        blackPink.introduce();
        
        
        // setter에 경우 변수의 값을 할당하는 것처럼 사용하기 때문에 setter에 매개변수는 값을 1개밖에 받을 수 없다.
        blackPink.firstMember = '준우';
        
        print(blackPink.firstMember);
    }


    // Idol class
    class _Idol {
        String name;
        List<String> members;
        
        // constructor
        _Idol(this.name, this.members);
        // const Idol(this.name, this.members);
        
        
        // named 생성자를 사용해서도 값을 받을수 있음
        _Idol.fromList(List values)
            : this.members = values[0],
            this.name = values[1];
        
        
        void sayHelo() {
            print('안녕하세요 ${this.name}입니다.');
        }
        
        void introduce() {
            print('저희 멤버는 ${this.members}가 있습니다.');
        }
        
        // getter
        String get firstMember {
            return this.members[0];
        }
        
        // setter
        // setter에 매개변수에는 무조건 매개변수의 값이 딱 1개만 들어간다
        set firstMember(String name) {
            this.members[0] = name;
        }
    }
    ```


<br>
<br>

## 8. Inheritance(상속)
    ```
    void main() {
        print('------- Idol -------');
        Idol apink = Idol(name: '에이핑크', membersCount: 5);

        apink.sayName();
        apink.sayMembersCount();


        print('');
        print('------- Boy Group -------');
        BoyGroup bts = BoyGroup('BTS', 7);

        bts.sayName();
        bts.sayMembersCount();
        bts.sayMale();

        print('');
        print('------- Girl Group -------');
        GirlGroup redVelvet = GirlGroup('Red Velvet', 5);

        redVelvet.sayName();
        redVelvet.sayMembersCount();
        redVelvet.sayFemale();

        print('');
        print('------- Type Comparison -------');

        print(apink is Idol);
        print(apink is BoyGroup);
        print(apink is GirlGroup);


        print('');
        print('------- Type Comparison2 -------');
        print(bts is Idol);
        print(bts is BoyGroup);
        print(bts is GirlGroup);


        print('');
        print('------- Type Comparison3 -------');
        print(redVelvet is Idol);
        print(redVelvet is BoyGroup);
        print(redVelvet is GirlGroup);
    }


    // 상속 - ingeritance
    //
    // 상속을 받으면 부모 클래스의 모든 속성을
    // 자식 클래스가 부여받는다.
    class Idol {
        // 이름
        String name;
        // 멤버 숫자
        int membersCount;

        Idol({
            required this.name,
            required this.membersCount
        });


        void sayName() {
            print('저는 ${this.name}입니다.');
        }

        void sayMembersCount() {
            print('${this.name}은 ${this.membersCount}명의 멤버가 있습니다.');
        } 
    }


    class BoyGroup extends Idol {
        // super에 매개변수로 데이터를 넘겨주는 행위의 의미는 상속받은 class에 생성자를 호출하는 작업과 같다.
        // super(name: name, membersCount: membersCount); == Idol(name: name, membersCount: membersCount);
        BoyGroup(
            String name,
            int membersCount
        ): super(name: name, membersCount: membersCount);

        void sayMale() {
            print('저는 남자 아이돌입니다.');
        }
    }


    class GirlGroup extends Idol {
        GirlGroup(
            String name,
            int membersCount
        ) : super(name: name, membersCount: membersCount);

        void sayFemale() {
            print('저는 여자 아이돌입니다.');
        }
    }
    ```


<br>
<br>

## 9. Override
    ```
    void main() {
        TimesTwo tt = TimesTwo(2);

        print(tt.calculate());
        
        TimesFour tf = TimesFour(2);
        
        print(tf.calculate());
    }

    // method = function (class 내부에 있는 함수)
    // override - 덮어쓰다 (우선시하다)
    class TimesTwo {
        final int number;

        TimesTwo(this.number);

        // method
        int calculate() {
            // this 생략가능
            return number * 2;
        }
    }

    class TimesFour extends TimesTwo {
        TimesFour(int number) : super(number);
    
        // `@override` 생략 가능 (근데 써주는게 더 보기 좋음)
        @override
        int calculate() {
            
            // `super.number`이게 정석인데 생략가능
            // return number * 4;
            
            // 이런식으로도 선언 가능
            return super.calculate() * 2;
        }
    }

    ```

<br>
<br>

## 10. Static

    ```
    void main() {
        Employee seulgi = Employee('슬기');
        Employee chorong = Employee('초롱');
        Employee jenny = Employee('제니');
        
        
        // instance의 귀속
        seulgi.name = '준우';
        seulgi.printNameAndBuilding();
        chorong.printNameAndBuilding();
        
        
        // class의 귀속
        Employee.building = '오투타워';
        seulgi.printNameAndBuilding();
        chorong.printNameAndBuilding();
        jenny.printNameAndBuilding();
        
        Employee.printBuilding();
    }

    class Employee {
        // static은 instance에 귀속되지 않고 class에 귀속된다.
        // 알바생이 일하고 있는 건물
        // static 키워드를 사용해서 class에 귀속 가능
        static String? building;
        // 알바생 이름
        String name;
        
        Employee(
            this.name,
        );
        
        void printNameAndBuilding() {
            print('제 이름은 $name입니다. $building 건물에서 근무하고 있습니다.');
        }
        
        static void printBuilding() {
            print('저는 $building 건물에서 근무중입니다.');
        }
    }
    ```

<br>
<br>

## 11. Interface
    ```
    void main() {
        BoyGroup bts = BoyGroup('BTS');
        GirlGroup redVelvet = GirlGroup('레드벨벳');
        
        bts.sayName();
        redVelvet.sayName();
        
        print(bts is IdolInterface);
        print(bts is BoyGroup);
        print(bts is GirlGroup);
        
        
        print(redVelvet is IdolInterface);
        print(redVelvet is BoyGroup);
        print(redVelvet is GirlGroup); 
    }

    // interface
    // abstract => 추상적
    abstract class IdolInterface {
        String name;
        
        IdolInterface(this.name);
        
        void sayName();
    }


    class BoyGroup implements IdolInterface {
        String name;
        
        BoyGroup(this.name);
        
        void sayName() {
            print('제 이름은 $name 입니다.');
        }
    }

    class GirlGroup implements IdolInterface {
        String name;
        
        GirlGroup(this.name);
        
        void sayName() {
            print('제 이름은 $name 입니다.');
        }
    }
    ```

<br>
<br>

## 12. Generic
    ```
    void main() {
        Lecture<String, String> lecture1 = Lecture('123', 'lecture1');
        lecture1.printIdType();
        
        Lecture<int, String> lecture2 = Lecture(123, 'lecture2');
        lecture2.printIdType();
    }


    // generic - 타입을 외부에서 받을때 사용
    class Lecture<T, X> {
        final T id;
        final X name;
        
        Lecture(this.id, this.name);
        
        void printIdType() {
            print(id.runtimeType);
        }
    }
    ```

<br>
<br>

## 13. OOP(Object Oriented Programming)
    ```
    void main() {
        Test test = Test();
        
        //   test.
        // 기본으로 나오는 4개의 메소드들은 Object 클래스에서 제공해주는 메소드들이다.
    }

    // OOP(Object Oriented Programming)
    // 객체지향 프로그래밍
    // 모든 클래스의 최상위 부모는 Object다
    class Test extends Object{}
    ```


<br>
<br>

# Funcational Programming(함수형 프로그래밍)


<br>

## 1. 형변환
    ```
    void main() {
        List<String> blackPink = ['로제', '지수', '리사', '제니'];
        
        // 형변환
        print(blackPink);
        print(blackPink.asMap());
        print(blackPink.toSet());
        
        Map blackPinkMap = blackPink.asMap();
        
        print(blackPinkMap.keys.toList());
        print(blackPinkMap.values.toList());
        
        Set blackPinkSet = Set.from(blackPink);
        
        print(blackPinkSet.toList());
    }
    ```

<br>
<br>

## 2. map() 함수
    ```
    // List에서 map() 함수 사용법
    void main() {
        List<String> blackPink = ['로제', '지수', '리사', '제니'];
        
        final newBlackPink = blackPink.map((x) {
            return '블랙핑크 $x';
        });
        
        print(blackPink);
        print(newBlackPink.toList());
        
        
        final newBlackPink2 = blackPink.map((x) => '블랙핑크 $x');
        print(newBlackPink2.toList());
        
        print(blackPink == blackPink);
        print(newBlackPink == blackPink);
        print(newBlackPink == newBlackPink2);
        
        
        // [1.jpg, 3.jpg, 5.jpg, 7.jpg, 9.jpg]
        String number = '13579';
        
        final parsed = number.split('').map((x) => '$x.jpg').toList();
        
        print(parsed);
    }


    =====================================================


    // Map에서 map() 함수 사용법
    void main() {
        Map<String, String> harryPotter = {
            'Harry Potter': '해리 포터',
            'Ron Weasley': '론 위즐리',
            'Hermione Granger': '헤르미온느 그레인저'
        };

        final result = harryPotter.map((key, value) =>
            MapEntry('Harry Potter Character: $key', ' 해리포터 캐릭터: $value'));

        print(harryPotter);
        print(result);

        final keys = harryPotter.keys.map((x) => 'HPC: $x');
        final values = harryPotter.values.map((x) => '해리포터 캐릭터: $x').toList();

        print(keys);
        print(values);
    }


    =====================================================


    Set blackPinkSet = {
        '로제',
        '지수',
        '제니',
        '리사'
    };
    
    final newSet = blackPinkSet.map((x) => '블랙핑크 $x').toSet();
    
    print(newSet);
    ```
<br>
<br>

## 3. 그외의 함수들
    ```
    // where() 함수
    void main() {
        List<Map<String, String>> people = [
            { 'name': '로제', 'group': '블랙핑크', },
            { 'name': '지수', 'group': '블랙핑크', },
            { 'name': '로제', 'group': 'BTS', },
            { 'name': '뷔', 'group': 'BTS', },
        ];
        
        print(people);
        
        // js에 filter 메소드와 같은 동작을 하는듯
        final blackPink = people.where((x) => x['group'] == '블랙핑크');
        final bts = people.where((x) => x['group'] == 'BTS');
        
        print(blackPink);
        print(bts);
    }


    =====================================================


    void main() {
        List<int> numbers = [1, 3, 5, 7, 9];
        
        // js의 reduce랑 거의 흡사
        // 단 배열의 타입과 리턴해주는 값들의 타입이 일치해야한다.
        final result = numbers.reduce((prev, next) {
            // 맨처음에만 prev에 첫번째 값(1)이 들어가고 next에 (3)
            // 그 다음부터는 prev에 누적값, next에 n번째 값이 들어감
            
            print('----------');
            print('previous: $prev');
            print('next: $next');
            print('total: ${prev + next}');
            
            return prev + next;
        });
        
        // final result = numbers.reduce((prev, next) => prev + next);
        // print(result);
        
        
        List<String> words = [
            '안녕하세요. ',
            '저는 ',
            '여준우입니다.'
        ];
        
        final sentence = words.reduce((prev, next) => prev + next);
        
        print(sentence);
        
        // words.reduce((prev, next) => prev.length + next.length); => Error
    }


    =====================================================


    ```



