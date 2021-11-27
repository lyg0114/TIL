***
# 1. 도커 세팅 
## 1.1 도커 다운로드
1. 공식 홈페이지 [Docker](https://www.docker.com/) 로 이동 
2. Docker DeskTop 다운로드및 설치
## 1.2 도커 이미지 다운로드 
1. 도커 허브 [DockerHub](https://hub.docker.com/) 로 이동 
2. 현재 필요한 이미지를 다운로드 한다.
    * **엘라스틱서치**, **키바나**를 검색하여 다운 
    
## 1.3 도커 컨테이너 실행 
1. 엘라스틱서치 실행 
    ```
    docker run --name ElasticSearch --port 9200:9200 elasticsearch:6.4.3 
    ```
2. 키바나 실행 
    ```
   docker run --name Kibana7 -p 5601:5601 --link lsElasticSearch:ElasticSearch kibana:6.4.3 
    ```
    * 엘라스틱서치와 키바나의 버전은 동일한 버전으로 세팅
    * 두개의 컨테이너를 --link로 연결해 주어야 한다.
        * link설정을 하지 않으면 키바나가 엘라스틱 서치를 찾지 못해 구동하지 않음

## 1.4 엘라스틱서치 설정 
1. 실습을 위하여 스넵샷 세팅을 진행
    * 엘라스틱서치 컨테이너에 CLI로 접속 DockerDesktop 활용
    * 엘라스틱서치가 설치되어 있는 경로 에서 ./config 경로로 이동 
    * elasticsearch.yml 파일 오픈 아래의 엘라스틱서치 정보를 입력후 저장
        ```
            discovery.zen.minimum_master_nodes: 2
            cluster.name: "javacafe-cluster"
            node.name: "javacafe-node1"
            network.host: 0.0.0.0
            http.port: 9200
            transport.tcp.port: 9300
            node.master: true
            node.data: true
            path.repo: ["/es/book_backup/search_example", "/es/book_backup/agg_example"]
        ```
    * /es/book_backup/ 경로에서 아래의 명령어를 실행하여 스냅샷 정보를 가져옴 
        ```
            wget https://github.com/javacafe-project/elastic-book-snapshot/raw/master/book_backup.zip --no-check-certificate 
        ```
    * "/es/book_backup/search_example", "/es/book_backup/agg_example" 두 경로의 권한을 열어준다.   


***
# 참고
* [도커공식문서](https://docs.docker.com/engine/reference/run/) 
* [생활코딩 도커](https://www.youtube.com/watch?v=Ps8HDIAyPD0&list=PLuHgQVnccGMDeMJsGq2O-55Ymtx0IdKWf) 
* [[따배도] 9-2. 컨테이너간 통신(네트워크) - 실습편](https://www.youtube.com/watch?v=CXrrkl4Zamc) 
