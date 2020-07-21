# 맥에서 php를 셋팅해 보자
 
- 맥에는 기본적으로 아파치와, php가 설치되어있다.
- 첫번째로 root 권한으로 변경
    > sudo su - 

- 아파치 실행
    > apachectl start

- 아파치에서 php 사용처리
    > - cd /etc/apache2/ <br>
    > - cp httpd.conf hppd.conf.bak <br>
    > - LoadModule php7_module libexec/apache2/libphp7.so 이부분 주석해제

- 아파치 재시작

- 기본 root 디렉토리 경로
    > /Library/WebServer/Documents -> 요안에 index.php가 들어간다고 생각하면됨

    
    


