***
# 1. 도커 세팅 
## 1.1 도커 다운로드
1. 공식 홈페이지 [Docker](https://www.docker.com/) 로 이동 
2. Docker DeskTop 다운로드및 설치
## 1.2 도커 이미지 다운로드 
1. 도커 허브 [DockerHub](https://hub.docker.com/) 로 이동 
2. 현재 필요한 이미지를 다운로드 한다.
    * **젠킨스**를 검색하여 다운 
    
## 1.3 도커 컨테이너 실행 
1.3.1 젠킨스 실행 

   ```
   docker run -itd --name jenkins -p 8085:8080 jenkins/jenkins:lts
   ```

   * run : 이미지를 실행
   * -itd 옵션: interacitve terminal + detach(background)
   * --name : 이미지 이름 지정
   * -p: hostport : docker container port
   * jenkins/jenkins:lts: docker hub이미지 저장소:버전

1.3.2 패스워드 입력

   ```
   docker exec yglee-jenkins cat /var/jenkins_home/secrets/initialAdminPassword
   ```
   * 상단의 명열어를 통해 패스워드 정보를 획득 
     
1.3.3 화면에 나오는대로 젠킨스 설치 진행
   
## 1.4 gitHub 연동

1.4.1 gitHub webHook 기능을 활용하여 빌드 자동화

1.4.2 gitHub에 ngrok을 활용한 외부에서 접근 가능한 URL(http://생성도메인/github-webhook/) 생성 및 등록

***

# 참고
* [블로그](https://jktech.tistory.com/41) 
* [창천향로 블로그](https://jojoldu.tistory.com/139)
* [유튜브 채널](https://www.youtube.com/watch?v=m0tky1jyP-0&list=PLwery4qTjQdaFZI_a0DJak4gIQeg2LzOq&index=3)

