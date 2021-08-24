# Install Spark 
- local 모드 ( 비분산 모드) 로 실행해보기!

<br>

</br>

## 0. 사용 환경 
- Virtual Box
- OS : Ubuntu

<br>

</br>

## 1. Java 설치
- Spark는 JVM 위에서 돌아감으로 Java 6 이후 버전이 필요
- Java 8 version 설치

    ### 1-1 ) open jdk 설치
    ```
    sudo apt-get install openjdk-8-jdk
    ```

    ### 1-2 ) 설치 확인
    ```
    javac -version
    ```

    ### 1-3 ) 관리자 권한으로 profile 열기
    ```
    sudo vi /etc/profile
    ```

    ### 1-4 ) profile의 맨 하단에 JAVA_HOME 설정
    ```
    export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
    ```
    ### 1-5 ) 환경설정 소스 적용
    ```
    source /etc/profile
    ```

    ### 1-6 ) 적용 확인
    ```
    echo $JAVA_HOME
    ```

<br>

</br>

## 2. Linux User 추가하기
- username을 spark로 설정
    ```
    sudo adduser spark
    ```
    ### ✔ user 정보 확인하기

    ```
    cat /etc/passwd
    ```

<br>

</br>

## 3. Spark 설치
- spark 3.1.2 version
- hadoop 3.2 version
    ### 3-1 ) home directory에서 압축 풀기
    ```
    tar -xf spark-3.1.2-bin-hadoop3.2.tgz
    ```
    ### 3-2 ) 심볼릭 링크 생성 
    - 링크를 연결해 원본 파일을 직접 사용하는 것과 같은 효과 냄 
    - windows의 바로가기롸 비슷한 개념
    ```
    ln -s spark-3.1.2-bin-hadoop3.2 spark 
    ```

    ### 3-3 ) spark 위치 옮기기
    ```
    sudo mv spark-3.1.2-bin-hadoop3.2/ /usr/spark
    ```

    ### 3-4 ) spark의 환경변수 지정
    - File 열기
    ```
    sudo getdit /etc/profile
    ```
    - 환경변수 설정
    ```
    export SPARK_HOME=/usr/spark
    export PATH=$SPARK_HOME/bin:$PATH
    ```

    ### ✔ Spark 설치 확인!
    - 실행
    ```
    /usr/spark/bin/spark-shell
    ```
    - 명령어
    ```
    println("spark is running")
    ```

<br>

</br>

## 4. Anaconda/ Python 설치
- conda version : 4.10.1
- python version : 3.8.8

    ### 4-1 ) Anaconda 설치
    ```
    bash Ana*.sh
    ```
    ### 4-2 ) Path 설정
    - File 열기
    ```
    getdit ~/.bashrc
    ```
    - 환경 변수 설정 (파일 맨 밑)
    ```
    export PATH=~/anaconda3/bin:$PATH
    ```
    ### 4-3 ) 파일 변경한거 실행
    - 폴더 이동
    ```
    cd anaconda3
    ```
    - File 실행
    ```
    source ~/.bashrc
    ```
    ### 4-4 ) Activate 하기
    ```
    source activate base
    ```

<br>

</br>


## 5. pyspark 설정
- Jupyter Notebook 에서 pyspark 활용
    ### 5-1 ) pip3 설치
    ```
    sudo apt install python3-pip
    ```

    ### 5-2 ) jupyter 설치
    ```
    pip3 install jupyter
    ```

    ### 5-3 ) jupyter에서 pyspark 실행하기
    - python 실행하고 비밀번호 설정 
    ```
    $ python
    >>> from notebook.auth import passwd
    >>> passwd() 
    ```
    - 비밀번호 입력하고 key 복사해놓고 종료 
    ```
    exit()
    ```

    ### 5-4 ) jupyter 설정 파일을 생성
    ```
    jupyter notebook --generate-config
    ```

    ### 5-5 ) Code 추가
    ```
    sudo gedit ~/.jupyter/jupyter_notebook_config.py
    ```
    - code 내용
    ```
    c.NotebookApp.allow_origin = '*'
    c.NotebookApp.open_browser = False
    c.NotebookApp.password = 'passwd()에서 복사한 key
    ```

    ### 5-6 ) pyspark의 환경변수 설정
    ```
    sudo gedit /etc/profile
    ```
    - code 내용
    ```
    export PYSPARK_DRIVER_PYTHON=jupyter
    export PYSPARK_DRIVER_PYTHON_OPTS='notebook'
    ```

    ### 5-7 ) pyspark 실행
    - ubuntu 재시작하고 실행할 것
    ```
    pyspark
    ```
    - localhost:8888로 접속하면 jupyter notebook 나타남 

<br>

</br>

## ✔ spark 연결 잘 되었는지 확인
- jupyter python창에서 확인하기 
    ```
    sc
    ```

