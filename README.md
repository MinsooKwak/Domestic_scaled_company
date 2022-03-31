## 국내 규모가 형성된 Tech Company 판별 모델링 및 데이터 분석

### 0. 요약
2020년 이후 투자받은 전세계의 Tech company에 대한 데이터를 활용하였습니다. </br>
본 데이터는 SHIVAM BANSAL님이 제공한 Tech company Fundings 데이터셋입니다. </br></br>
[데이터 출처: Tech company Fundings 2020](https://www.kaggle.com/datasets/shivamb/tech-company-fundings-2020-onwards)

### 1. 데이터 설명
  <b>1) 기존 데이터 </b></br></br>
    총 데이터셋 크기: (3575, 8) </br></br>
    <b>[feature 설명 및 특징]</b>
    
      - company        (3224): 회사명
      - Website        (3343): 웹사이트
      - Region         (72)  : 지역 (국가)
      - Verticle       (143) : 영역 
      - Funding Stage  (22)  : Funding 단계
      - Funding Amount (USD) : 투자 금액 
      
      - 특징 : 높은 범주의 feature로 낮은 범주로 묶어줄 필요가 있었음

</br>
<b>2) 데이터 수정 내용 </b></br></br>

    - 높은 범주를 갖고 있는 feature들이 많아 좁은 범주들로 재구성해주었음
    
    - 오탈자나 동일한 범주를 다르게 표현하고 있는 경우 다시 구성해줌
    
    - Funding Stage에 대한 자료조사를 통해 7개의 Funding Stage로 재구성
    
    - Verticle에 대해서도 Tech, Business, Health, Infra&Vehicle, Extra의 5개 범주로 재구성


### 2. 프로젝트 진행 사항
<b>1) 데이터 분석 및 시각화</b>
  - 투자 받은 국가와 비율 확인 (Folium Library, Seaborn) 
  - 데이터 시각화를 통한 현황 파악 (Seaborn : Bar, Pie chart)
    - 카테고리 분포, Tech category Top10, Debt Financing Fund 영역 등 </br>

<b>2) 모델 형성</b> 
  - 국내에서 어느 정도 규모가 형성이 되고 자체적으로 기업 영위가 가능한 Series C를 Target으로 설정해 모델 형성

### 3. 모델 사용
- Funding Amount, Funding Date를 제외한 항목이 카테고리형이므로 회귀모델이 아닌 분류모델을 사용함
- Logistic Regression 모델과 XG Boost 모델을 사용하여 비교
- 두 모델의 검증 결과가 동일해 XG Boost 모델을 선택해 사용함
- 기준모델인 Decision Tree의 정확도 0.83에 비해 XG Boost 모델의 정확도가 0.88로 향상되었음
