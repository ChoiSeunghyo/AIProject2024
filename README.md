# 당뇨병 예측 모델 만들기
### Flask를 이용한 웹페이지 구축하기

##### 1. 프로젝트 개요:
당뇨병은 현대 사회에서 매우 흔한 만성 질환이며, 합병증을 유발할 수 있다. 이러한 상황에서 당뇨병의 조기 예측은 환자의 건강을 지속적으로 모니터링하고, 심각한 합병증을 예방하며, 치료 및 관리에 중요한 역할을 한다.

이 프로젝트는 사용자의 다양한 생리학적 특성과 건강 지표를 기반으로 당뇨병 발병 가능성을 예측하는 인공지능 모델을 구축하는 것을 목표로 한다. 예를 들어, 임신 횟수, 나이, 체질량지수, 혈압, 포도당 농도 등과 같은 다양한 요인을 고려하여 개별 환자의 당뇨병 발병 위험을 수치로 확인할 수 있다.

이 모델은 사용자의 개인 건강 데이터를 분석하여 당뇨병 발병 가능성을 예측하는 도구로 활용될 것을 목적으로, 더 나아가 예측 결과를 토대로 개별적인 건강 관리 계획 및 예방 전략을 제시함으로써, 개인의 건강을 개선하고, 의료 비용을 절감하며, 생활의 질을 향상시키는 데 도움이 될 것으로 기대된다.

이 프로젝트는 뿐만 아니라, Flask를 사용하여 웹 페이지를 구축해 사용자가 쉽게 당뇨병 발병률을 확인할 수 있도록 확장된다. 사용자가 간편하게 자신의 건강 지표를 입력하면, 백엔드에서는 구축한 인공지능 모델을 활용하여 사용자의 당뇨병 발병 가능성을 예측한다.  이를 통해 사용자는 당뇨병 발병 가능성에 대한 예측 결과를 시각적으로 확인할 수 있을 것이다.

##### 2. 사용 데이터세트: 
Predict Diabetes From Medical Records (kaggle.com) kaggle에서 가져온 데이터를 사용했다.
<https://www.kaggle.com/code/paultimothymooney/predict-diabetes-from-medical-records/input>

당뇨병 268명, 비당뇨병 500명의 데이터로 이루어졌다.
![통계](https://github.com/ChoiSeunghyo/AIProject2024/blob/main/%EB%8D%B0%EC%9D%B4%ED%84%B0%ED%86%B5%EA%B3%84.png)

outcome과 가장 상관관계가 높은 항목으로 1. Glucose, 2.BMI, 3. Age이었다.
![상관관계](https://github.com/ChoiSeunghyo/AIProject2024/blob/main/%EC%83%81%EA%B4%80%EA%B4%80%EA%B3%84.png)

#####3. 모델 설명:
![모델비교](https://github.com/ChoiSeunghyo/AIProject2024/blob/main/%EB%AA%A8%EB%8D%B8%EB%B9%84%EA%B5%90.png)

성능비교를 통해 최종적으로 로지스틱 회귀 모델을 선택했다.
새로운 환자의 데이터에 대한 예측을 수행하는 데에 로지스틱 회귀모델은 매우 유용하다. 로지스틱 회귀모델은 계산이 비교적 간단하고 효율적이기 때문에 대규모 데이터셋에도 빠르게 적용할 수 있다. 이러한 점에서 실시간 예측이 필요한 응용 프로그램에 적합하다고 판단하였다.

![model1](https://github.com/ChoiSeunghyo/AIProject2024/blob/main/model1.png)
![model2](https://github.com/ChoiSeunghyo/AIProject2024/blob/main/model2.png)

아래는 성능평가에 활용한 ROC-AUC curve와 Precision-Recall curve이다.
![curve1](https://github.com/ChoiSeunghyo/AIProject2024/blob/main/curve.png)
![curve2](https://github.com/ChoiSeunghyo/AIProject2024/blob/main/curve2.png)

