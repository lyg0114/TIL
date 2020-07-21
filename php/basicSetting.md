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

- 다운받은 codeigniter 폴더를 /Library/WebServer/Documents 이쪽으로 옮긴다.
- 관리자 권한으로 실행히야한다. 
    > sudo mv ./Documents/ /Library/WebServer/Documents

- Root 디렉토리를 변경할 수 도 있다.
    > /etc/apache2/httpd.conf 요기로 가서 root 디렉토리를 변경할 수 있다.
    > 그런데 root디렉토리를 변경하니 권힌이 없다는 오류가 발생한다. (아직 해결은 못함)





    


