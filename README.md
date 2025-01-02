# 대리기사 탐지 모델링 (과제 2)

## 프로젝트 개요
본 프로젝트는 투루카(Turuka) 서비스 이용 고객 중 대리기사를 식별하여 두 가지 목표를 달성하기 위한 모델을 개발합니다:
1. 기존 대리기사 고객 유지
2. 잠재 고객 유치

### 데이터 개요
- **수집 기간:** 2022년 10월 1일 ~ 2023년 7월 31일
- **주요 데이터:** 
  - 고객 인적사항 (나이, 성별 등)
  - 차량 정보 (차량 번호, 모델 등)
  - 이용내역 (출발/도착 스팟, 이용 시간 등)
  - 파생 변수 (시간대별 이용 비율, 스팟 다양성 등)

## 모델링 과정
1. **EDA 및 데이터 전처리**
   - 고객과 대리기사의 행동 패턴 비교
   - 시간대별, 요일별 이용 비율, 스팟 클러스터 등 파생 변수 생성
2. **모델 개발**
   - 사용 모델: Logistic Regression, Random Forest, XGBoost 등
   - 데이터 분할 및 오버샘플링(SMOTE) 적용
   - Subset Selection을 통해 최적 변수 선정
3. **평가 지표**
   - Accuracy, Precision, Recall, F1 Score, ROC AUC 등

## 최종 모델 성능
- **사용 모델:**  XGBoost
- **주요 변수:** 
  - 총 이용 횟수(Total_count)
  - 일요일 이용 비율(Day_6)
  - 시간대별 이용 비율(Hour_10_23)
  - 출발/도착 스팟 다양성(Start/End_spot_diversity)
  - 평균 이동 거리(Avg_dist)
- **최종 성능:**
  - Accuracy: 0.9718
  - F1 Score: 0.9500
  - ROC AUC: 0.9808

## 해석 가능성 강화
- **SHAP 분석:** 변수별 기여도 평가
- **Waterfall Plot:** 대리기사와 일반 고객의 예측 기여도 시각화
- **로지스틱 회귀 분석:** 변수별 회귀 계수 및 통계적 유의성 확인

## 주요 인사이트
- **대리기사 예측 요인:** 
  - 스팟 다양성이 높을수록 대리기사일 확률 증가
  - 10~23시 이용 비율이 낮을수록 대리기사일 확률 증가
- **일반 고객:** 주로 주간 시간대 이용
- **모델 해석 결과:** 대리기사와 일반 고객의 특징을 구분하는 데 효과적

---