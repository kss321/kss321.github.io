1. 리눅스
    - 컴퓨터 운영 체제

2. 명령어
    - sudo
        - 슈퍼유저 권한 명령
        - 일반 사용자가 root 권한을 잠시 빌려 명령을 실행하게 하는 명령어
        - $ sudo 명령어
        - sudo 명령어를 사용할 수 있는 사용자, 혹은 그룹은 /etc/sudoers에 등록되어 있어야 함
    - chmod
        - change mode
        - 대상 파일과 디렉토리의 사용권한을 변경할 때 사용
    - log
        - tomcat
            - 해당하는 로그 위치로 이동 cd /var/log/tomcat/front-log/
            - 실시간 tomcat log 명령어 tail -f catalina.out
            - 검색1 tail -f catalina.out | grep INFO
            - 검색2 tail -f catalina.out | grep "INFO 18544"
    - vim
        - 텍스트 에디터
        -     
    - ライブラリーアップデート	
        - $ sudo yum update
    - Javaインストール	
        - $ sudo yum install java-1.8.0-openjdk-devel
    - ホスト名変更	
        - $ sudo hostname <HOSTNAME>
        - $ sudo hostnamectl set-hostname <HOSTNAME>
    - Apacheインストール	
        - $ sudo yum -y install httpd 
    - Nexus 
        - ダウンロード(3.20.1)	
            - https://download.sonatype.com/nexus/3/latest-unix.tar.gz
        - インストール	
    - polkitアップデート	
        - sudo yum install polkit
    - t2.microタイプはメモリ不足	
        - /app/nexus/nexus-3.20.1-01でログ確認
    - postfix(메일서버)
        - $ sudo yum install postfix
    
    ＊AWS EC2のタイムゾン変更方法
    
    １。clockファイルを開いて、下記のように変更
    $ sudo vim /etc/sysconfig/clock
    # ZONE="UTC"
    ZONE="Japan"
    UTC=true
    
    ２。時間帯ファイルにシンボリックリンク
    $ sudo ln -sf /usr/share/zoneinfo/Japan /etc/localtime
    
    ３。日本時間に表示されていることを確認
    $ date
    
    ４。インスタンス再起動
    $ sudo reboot
3. Install
    1. RPM/YUM
        - RPM
            - Redhat Package Manager
            - 프로그램 설치 후 바로 실행
            - 확장자명 *.rpm
            - 패키지 인스톨을 하기 위해선 그 패키지의 필요요소 전부를 따로 다운해야함(의존성)
            - 리눅스에서만 쓸 수 있는 패키지 인스톨
        - YUM
            - Yellodog Updater Modified
            - RPM기반 시스템 자동업데이터 
            - 소프트웨어의 설치,삭제 도구
            - rpm의 패키지 의존성 문제를 해결
            - 인터넷을 통해서 필요한 파일을 저장소에서 자동으로 모두 다운로드하여 설치하는 방식
            - 따라서, 외부 레포지토리 서버와 통신이 가능해야 함
                
                
    
* 출처
- 명령어 https://www.leafcats.com/168