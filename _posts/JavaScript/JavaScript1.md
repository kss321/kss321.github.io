1. 자바 스크립트 선언
    1) async
        스크립트 선언을 만나면 fetching 후, 바로 execute        
    2) defer
        스크립트 선언을 만나면 fetching, html 파싱이 끝나야 execute
        
2. 'use strict';
    자바스크립트의 비상식적인 문법 용이를 방지    
    
3. 입력 -> 연산 -> 출력

4. 변수
    1) let 
        - ES6에서 추가된 데이터타입
        - mutable
    2) var
        - let가 나오기 전에 쓰던 데이터 타입
        - let을 쓰기를 추천
        - var hoisting : 어디에 선언 했느냐에 상관없이 항상 제일 위로 선언을 끌어 올려줌
        - var는 block scope가 없음, 블럭을 무시함
    3) const
        - 값을 변경할 수 없음, immutable
        - 한번 작성한 값을 변경할 수 없으므로 보안상 좋음
        - 다양한 스레드들이 동시에 접근해서 값을 변경하는 것을 막음 thread safety
        - 개발자 실수 방지
        
    Variable / Const    
    mutable 변할수 있는 / immutable 불변의
        
5. 데이터 타입 
    1) 숫자
        - Number -2의 53승부터 2의 53승 사이의 범위
        - bigIng 최근에 추가됨
    2) Symbol
        - 같은 String이어도 Symbol을 사용하면 다른 것으로 판별
        ex1) const test1 = Symbol('a');
             const test2 = Symbol('a');
             -> test1 != test2
             같은 string이지만 Symbol을 사용했으므로 다른 존재로 받아들임              
        ex2) const test1 = Symbol.for('a');
             const test2 = Symbol.for('a');
             -> test1 == test2 
             for를 사용하면 같은 String일 경우, 같은 Symbol로 이해
        ex3) Symbol은 console에 찍을 경우, test1.description처럼 description을 사용해야함
        
6. block scope
    블럭 내부의변수는 밖에서 볼 수 없음
        
6. 데이터타입 결정이 중요한 이유
    해당하는 데이터 타입에 따라 메모리에서 차지하는 용량이 다르기 때문에 
    불필요한 메모리 낭비를 방지하기 위해서는 알맞는 데이터 타입 선택이 필요하다

7. concat연결
    ``으로 연결 가능

9. Dynamic typing
    데이터 타입 유연하게 사용가능
    string에서 number로 number에서 string으로 바뀔수 있음
    자바스크립트는 runtime에서 타입이 결정됨
    
10. TypeScript
    자바스크립트 위에 타입이 올려진 언어

11. 연산
    1) String concatenation
        +
    2) Numeric Operatiors
        2**3 : 2의 3승    
        
12. Function
    - 하나의 함수는 한가지의 일만 하도록 만들어야 한다
    - 함수명은 동사 형태로 지어야 한다
    - 함수의 이름이 길고 어렵다면 함수 안에서 여러가지 동작으로 하고 있는 것은 아닌지 고민해 보아야 함
    - function is object
             