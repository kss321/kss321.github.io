1. 정의
    - 지속적 통합
    - 지속적으로 퀄리티 컨트롤을 적용하는 프로세스를 실행하는 것
    - 소프트웨어 개발 프로젝트는 [분석/설계] → [코드 작성] → [빌드] → [테스트] → [릴리스] → [디플로이]의 생명주기를 가짐
    - 위의 단계들이 반복적으로 이루어지는데 예전에는 이 과정에서 복잡성 및 시간 소요로 통합이 드물게 이루어졌음
    - 이러한 문제를 해결하기 위해 팀원들이 작성한 코드를 최대한 자주 통합하는 소프트웨어 개발 실천법이 지속적인 통합임                        
    1. 생명주기
        - Compile
            - 컴퓨터가 이해하는 기계어로 변환하는 작업 즉, 바이너리 코드로 변환
            - 이러한 작업을 하는 것을 컴파일러
            - 자바의 경우 컴파일러가 바이트코드 형태의 클래스 파일을 생성하면 JVM에서 실행
            - 컴파일은 해당 파일만을 컴파일해서 object 파일을 생성
        - Build
            - 소스코드 파일을 실행가능한 소프트웨어 산출물로 만드는 일련의 과정을 말함
            - 빌드 안에 컴파일이 포함되어 있음
            - 자바의 경우 war, jar 파일을 만드는 것
            - 빌드는 관련된 모든 파일을 컴파일해서 object 파일을 만든 뒤, link를 해서 실행가능한 exe/bpl/bpk 등의 파일을 생성
            - Compile + 그 외 작업
            - 빌드툴은 전처리(preprocessing), 컴파일(Compile), 패키징(packaging), 테스팅(testing), 배포(distribution)를 제공함
            - 빌드툴 종류 Ant, Maven, Gradle
        - Run  = Bulid + 실행
               = (Compile + 그 외 작업) + 실행     
        - release
        - deploy                
            - 빌드되어 실행가능한 결과물을 컨테이너에서 인식가능한 곳에 배치하는 것
            
2. SCM
    - 소스코드 형상관리 시스템
    - 소스코드의 개정과 백업 절차를 자동화하여 오류 수정 과정을 도와줌
    - Git, SVN, Mercurial
    - Git 호스팅 서비스
        - GitHub
        - GitLab
        - Bitbucket
            
3. Build Tool
    - 컴파일, 테스트, 정적분석 등을 실시해 동작 가능한 소프트웨어를 생성
    - ANT, Maven, Gradle 

4. CI서버
    - 빌드 프로세스를 관리하는 서버
    - Jenkins, Hudson, CruiseControl.NET, TeamCity
    - Jenkins가 가장 많이 사용됨
    - Jenkins
    
5. 웹서버
    1. Apache
        - 패키지 다운로드
        - 패키지 인스톨
        - 서비스 개시
        - 인스턴스 기동시 자동기동 설정
        * G1Apache OpenSSL Install
            - Amazon Apache 2.4へSSL自己証明書を発行する手順
            - 秘密鍵（Private Key）の作成
            - 公開鍵（CSR）の作成
            - サーバー証明書（CRT）の作成
            - httpd設定ファイルの編集
            - 設定変更の反映
6. WAS
    1. Tomcat
        - 인스톨 모듈 준비
        - 모듈의 전개
        - 인스턴스 기동시 자동기동설정(젠킨스의 경우)
        - 권한 설정
        - chkconfig 설정
        - Tomcat Log Rotate
    
7. Docker
    - 리눅스의 응용프로그램들을 소프트웨어 컨테이너 안에 배치시키는 일을 자동화하는 오픈소스 프로젝트
    
8. 라이브러리 관리
    - Nexus

9. SonarQube

*출처
- 도커 https://subicura.com/2017/01/19/docker-guide-for-beginners-1.html
- https://tenlie10.tistory.com/75
