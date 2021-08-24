# ✔ Spark Basic

## ✔ Spark의 셸
- 여러 머신의 메모리나 디스크에 분산되어 존재하는 데이터들과 통신 가능 
- Spark의 작업 node에서 데이터를 ㅁ모리에 올려 처리 가능해 테라바이트 단위의 데이터 처리도 빠르게 가능함

<br>

</br>

## ✔ 핵심 개념
- Spark Application은 cluster에서 병렬 연산을 수행하는 드라이버 프로그램으로 구성
    ### Driver Program
    - 만든 App의 main함수를 가짐
    - cluster의 분산 dataset을 정의
    - dataset에 연산 작업 수행

    ### 흐름 
    1. Driver Program은 SparkContext 객체를 통해 spark에 접속함 
        - SparkContext 객체 => 연산 cluster에 대한 연결 나타냄
        - SparkContext 객체는 자동으로 sc라는 변수에 만들어짐
    
    2. SparkContext 객체로 RDD 만들 수 있음 
        - sc.textFile()을 호출해 연산 수행 가능 
        - 연산을 수행하기 위해 Driver Program들은 excutor( cluster의 machine 1개) 를 관리

    3. Spark API들이 cluster에서 연산 작업들을 수행하기 위해 함수를 작성해 연산 함수에 인자를 보냄

<br>

</br>

## ✔ 단독 Application
- 대화형으로 사용하는 것 이외에도 독립적인 app과 연결해서 사용 가능 
    - SparkContext 객체를 초기화해줘야 함
