# Apache Spark Introdution
## What's the Apache Spark?
- cluster용 연산 플랫폼 ( 범용적 & 빠른 속도로 작업 수행)
- MapReduce Model을 대화형 명령어 쿼리 & 스트리밍 처리 가능하도록 확장
- 서로 다른 형태의 작업을 쉽고 저비용으로 연계 가능 
- Hadoop cluster 에서 실행 가능 

## Spark의 구성 
- 스파크 프로젝트는 밀접하게 연동된 여러개의 컴포넌트로 구성되어 있음 
- 다수의 가상 머신 & cluster에서 돌아가는 연산 작업들을 스케줄링 & 분배하는 역할 

    ### 장점
    - 하위 Layer의 성능 향상에 의해 직접적으로 이익 얻음 
        - spark의 핵심엔진을 최적화 하면 SQL, ML library도 자동으로 속도 빨라짐
    - 서로 다른 데이터 처리 모델을 합쳐 1개의 Application을 만들 수 있음 
        - ex) 데이터를 실시간으로 분류하는 동시에 실시간으로 SQL 질의 날리기 가능 
    
    ### (1) Spark Core 
    - 작업 스케줄링, 메모리 관리, 장애 복구, 저장 장치와의 연동등 기본적인 기능들로 구성 
    - RDD (Resilient Distributed Dataset) 정의하는 API의 기반 
        
    ### (2) Spark SQL
    - 정형 데이터 처리 위한 package
    - Hive Table, Parquet, JSON등의 데이터 소스 지원
    - Hive의 SQL 변형을 써서 데이터에 질의 보낼 수 있음

    ### (3) Spark Streaming
    - 실시간 데이터 스트림 처리 가능하게 해주는 spark의 component 
        
    ### (4) MLlib
    - ML 기능을 갖고 있는 라이브러리
    - 분류, 회귀, 클러스터링, 협업 필터링등의 ML 알고리즘 지원

    ### (5) Graph X
    - 그래프를 다루기 위한 library
    - 그래프 병렬 연산 수행

    ### (6) Cluster Manager
    - Spark는 1개 node에서 수천 node까지 효과정으로 성능 확장 가능
    - 이를위해 Hadoop의 YARN, Apache Method, 단독 스케쥴러등 다양한 클러스터 매니저 위에서 동작 가능 




    #### ▶ RDD 
    - 여러개의 컴퓨터 노드에 흩어져서 병렬처리 될 수 있는 아이템들의 모음을 표현 

    #### ▶ 실시간 데이터 스트림
    - 전체 데이터를 기다릴 필요 없이 도착하는 순서대로 처리 
    - log file & 상태 업데이트 메세지가 저장되는 queue등이 해당함