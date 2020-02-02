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
        
2. JAVA
    - OpenJDK8　RPMインストール
    - 
3. Tomcat
    - 인스톨 모듈 준비
    - 모듈의 전개
    - 인스턴스 기동시 자동기동설정(젠킨스의 경우)
    - 권한 설정
    - chkconfig 설정
    
4. Docker
5. Nexus
6. Jenkins
7. SonarQube
8. GitLab

* RPM/YUM
- RPM
    - Redhat Package Manager
    - 프로그램 설치 후 바로 실행
    - 확장자명 *.rpm
    - 패키지 인스톨을 하기 위해선 그 패키지의 필요요소 전부를 따로 다운해야함(의존성)
    - 리눅스에서만 쓸 수 있는 패키지 인스톨
- YUM
    - Yellodog Updater Modified
    - rpm의 패키지 의존성 문제를 해결
    - 인터넷을 통해서 필요한 파일을 저장소에서 자동으로 모두 다운로드하여 설치하는 방식
    - 따라서, 외부 레포지토리 서버와 통신이 가능해야 함
