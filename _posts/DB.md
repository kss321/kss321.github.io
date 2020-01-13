
「모두의 SQL」 정리 

1. DB
    - 데이터베이스의 정의
        - 데이터를 모아놓은 것
        - 
    - 데이터베이스의 종류
        - 관계형 데이터베이스
            - 열과 행으로 이루어진 2차원 테이블 중심의 데이터베이스
            - 데이터를 키와 관계라는 연결고리로 연결
            - 현재 업무용으로 가장 많이 쓰임
            - 오라클, DB2, MySQL, MS SQL Server
        - 계층형 데이터베이스
            - 가장 오래된 형태의 데이터베이스
            - 개인 컴퓨터 저장장치에 가장 많이 사용
            - 폴더와 파일 구조
            - 직관적
        - 객체지향 데이터베이스
            - 객체와 객체 식별자, 속성과 메서드, 클래스, 클래스 계층 및 상속, 복합 객체 등 객체 지향 데이터 모델을 지원
            - 자바 C++과 같은 객체 지향 언어 프로그래밍에 적합
        - XML 데이터베이스
            - W3C의 XML 표준 문서 구조를 계층형 트리 형태로 저장하거나 관리
            - XML문서 중심의 데이터 베이스
            - XQuery 사용

2. DBMS
    - 데이터베이스 관리 시스템
    - Oracle, MySql 같은 것들은 사실상 DB가 아니라 DBMS
    
3. SQL    
    - DML
        - SELECT
        - INSERT
        - UPDATE
        - DELETE
    - DDL
        - CREATE
        - ALTER
        - DROP
        - RENAME
        - TRUNCATE
    - DCL
        - GRANT
        - REVOKE
    - TCL
        - COMMIT
        - ROLLBACK
        - SAVEPOINT

4. WHERE
    - BETWEEN A AND <-> NOT BETWEEN A AND B 
    - IN (list) <-> NOT IN (list)
    - LIKE '문자열' -> 문자열%
    - IS NULL <-> IS NOT NULL
    - != 같지 않다
    - <> 같지 않다

5. 문자 타입 함수
    - LOWER     소문자 변환
    - UPPER     대문자 변환
    - INITCAP   첫글자 대문자 변환
    - SUBSTR    문자열 자르기
    - REPLACE   문자열 대체
    - CONCAT    문자열 연결
    - LENGTH    문자열 길이
    - INSTR     문자 위치
    - LPAD      왼쪽부터 특정 문자로 대체
    - RPAD      오른쪽부터 특정 문자로 대체
    - LTRIM     주어진 문자열의 왼쪽 문자열 삭제
    - RTRIM     주어진 문자열의 오른쪽 문자열 삭제
   
6. 숫자 타입 함수
    - ROUND     숫자 반올림
    - TRUNC     숫자 절삭
    - MOD       나누기 후 나머지 값
    - CEIL      숫자를 정수로 올림
    - FLOOR     숫자를 정수로 내림
    - SIGN      양수, 음수, 0을 구분
    - POWER     거듭 제곱을 출력
    - SQRT      제곱근을 출력
    
7. 날짜 타입 함수
    - MONTHS_BETWEEN    두 날짜 사이의 월수를 계산
    - ADD_MONTHS        월을 날짜에 더함
    - NEXT_DAY          명시된 날짜부터 돌아오는 요일에 대한 날짜를 출력
    - LAST_DAY          월의 마지막 날을 계산
    - ROUND             날짜를 가장 가까운 연도 또는 월로 반올림
    - TRUNC             날짜를 가장 가까운 연도 또는 월로 절삭

    - DATE + NUMBER         날짜에 일수를 더함
    - DATE - NUMBER         날짜에 일수를 뺌
    - DATE - DATE           날짜에서 날짜를 뺌
    - DATE + NUMBER / 24    날짜에 시간을 더할때 시간을 24로 나누어 날짜에 더함

8. 변환 함수
    - TO_CHAR   VARCHAR2 타입으로 변환              
    - TO_NUMBER 문자를 숫자 타입으로 변환
    - TO_DATE   날짜를 나타내는 문자열을 지정 형식의 날짜 타입으로 변환
        
9. 일반 함수
    - NVL       Null값 치환        NVL(열 이름, 치환 값)
    - DECODE
    - CASE
    - RANK
    
10. 그룹 함수
    - CONT      행 개수
    - SUM       합계
    - AVG       평균
    - MAX       최댓값
    - MIN       최솟값
    - STDDEV    표준편차    
    - VARIANCE  분산
    
11. GROUP BY : 그룹으로 묶기
    - 특정 열의 데이터 값을 기준으로 그룹화하여 다른 열에 그룹 함수를 적용해야 하는 경우
    - SELECT CLASS, SUM(STUDENT_SCORE) GROUP BY CLASS
    - 위의 SQL의 경우 같은 클래스를 기준으로 그룹화 하여 각 클래스의 학생들의 점수를 합산하여 표시하게 됨
    - SELECT 기준 열, 그룹 함수(열 이름) 
        FROM 테이블 이름
        GROUP BY 열 이름
        
12. HAVING : 연산된 그룹 함수 결과에 조건 적용하기

13. 조인
    - 조인이란 한 개 이상의 테이블과 테이블을 서로 연결하여 사용하는 기법
    - 조인 기법의 종류
        - 곱집합            가능한 모든 행을 조인
        - 동등 조인         조인 조건이 정확히 일치하는 경우에 결과를 출력
        - 비동등 조인       조인 조건인 정확히 일치하지 않는 경우에 결과 출력      
        - 외부 조인         조인 조건이 정확히 일치하지 않아도 모든 결과 출력
        - 자체 조인         자체 테이블에서 조인하고자 할 때 사용

14. 서브쿼리
    - SELECT문 안에 있는 SELECT문
    - SELECT문을 효율적으로 작성할 수 있도록 도와줌
    - 복잡한 SELECT문을 작성할 때 거의 필수로 사용하는 기법
    - 두 번 작성해서 결과를 출력해야 하는 SELECT무을 한 번만 작성해서 처리할 수 있도록 함
    - 단일 행 서브쿼리
        - 서브쿼리 SELECT문에서 얻은 한 개 행의 결괏값을 메인 쿼리로 전달하는 서브쿼리
        - 메인 쿼리와 서브쿼리를 연결하는 연산자로 단일 행 연산자를 사용
        - WHERE 절에 기술되는 열의 개수와 데이터 타입은 메인 쿼리와 서브 쿼리가 서로 같아야 함
        
        ```SQL
        SELECT * 
        FROM employees A
        WHERE A.salary = (
                            SELECT salary
                            FROM employees
                            WHERE last_name = 'TEST'
                            );
        ```
    - 다중 행 서브쿼리
        - 사용법은 단일 행 서브쿼리와 같음
        - 하나 이상의 결과행을 메인 쿼리에 전달하는 경우에 사용
        - 연산자 종류
            - IN        같은 값
            - NOT IN    같은 값이 아님
            - EXISTS    값이 있으면 반환
            - ANY       최소한 하나라도 만족 하는 것
            - ALL       모두 만족하는 것
        
        ```SQL
        SELECT * 
        FROM employees A
        WHERE A.salary IN (
                            SELECT MIN (salary)
                            FROM employees
                            GROUP BY department_id
                            )
        ORDER BY A.salary DESC
        ```    
    - 다중 열 서브쿼리
        ```SQL
        SELECT * 
        FROM employees A
        WHERE (A.job_id, A.salary) IN (
                                        SELECT job_id, MIN(SALARY)
                                        FROM employees
                                        GROUP BY job_id
                                        )
        ORDER BY A.salary DESC;
        ```
    - FROM절 서브쿼리    
        - FROM절에 서브쿼리를 사용할 경우 가상의 뷰와 같은 역할을 함
        ```SQL
        SELECT *
        FROM employees AS A, (
                                SELECT department_id
                                FROM departments
                                WHERE department_name = 'IT'                
                              ) AS B
        WHERE A.department_id = B.department_id;
        ```