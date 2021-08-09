# 목차
## Basic
### NumpyModule
- list & ndarray
- astype()
- arange() , zeros(), ones()
- reshape()
- tolist()
- Indexing 
- Sort() & argsort()
- np.dot() & transpose()

### PandasModule_1
- read_csv()
- shape
- info(), describe()
- value_counts()
- ndarray, List, Dictionary => DataFrame
- DataFrame => ndarray, list, dictionary
- column 값 update
- Drop()
- Index
- reset_index()

### PandasModule_2
- column 추출 (인덱싱)
- iloc[]
- loc[]
- sort_values()
- Aggregation 함수
- groupby() / agg()
- 결손 데이터 처리 ( isna() & fillna() )
- apply() (lambda 식)

### Regression
- 간단한 회귀분석 예제 & 해석

<br></br>

## ML_Concept
### 1.ML_Basic_Concept
- ML 기본 개념
- iris 품종 Classification

### 2.CrossValidation
- 과적합
- 교차검증
    - K 폴드 교차 검증
    - Stratified K 폴드 교차 검증
    - Cross_val_score()
    - GridSearchCV

### 3.PreProcessing
- Data Encoding
    - Label Encoding
    - One Hot Encoding
- Feature Scaling
    - 표준화 (StandardScaler)
    - 정규화 (MinMaxScaler)

### 4.Evaluation
- 성능평가 지표
    - 정확도 (Accuracy)
    - 오차행렬 (Confusion Matrix)
    - 정밀도 (Precision)
    - 재현율 (Recall)
    - F1 스코어
    - ROC AUC

### 5.Classification
- classification 기본 개념

<br>

</br>

## ML_Technique
### Classification
- Decision Tree
- Ensemble 기법 적용한 Algorithm
    - Random Forest
    - GBM
    - XGBoost

<br>

</br>

## DoExcercises
### Reuters_News_Classification_Example
- Text Mining예제
- 로이터 뉴스를 category에 맞게 분류하는 예제
- LSTM Algorithm 이용

### Titanic_Example_Sklearn
- Sklearn 예제

### Pima_Indian_Diabetes
- Evaluation 확인하기 위한 예제

### TF_IDF_Basic_Example
- TF-IDF 이용한 간단한 추천 예제

### Movie_Recommendation
- Contents Based Filtering 예제
