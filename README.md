# Immune Module (Infection Risk Modeling)

## 1) 개요
본 분석 코드들은 프로젝트 중 요양원 거주 민감계층 대상 프로젝트의 면역/감염 리스크 분석 파트입니다.

MIMIC-IV 기반 코호트 EDA/전처리와 감염 위험 모델링, 환경 요인 통합, 한국 적용 검증 흐름으로 구성되어 있습니다.

## 2) 파일 구성
- `Infection_MIMIC-IV_EDA_Cohort_Preprocess.ipynb`
  - 데이터 EDA 및 코호트 전처리 노트북
- `Infection_MIMIC-IV_Modeling_1_Unsupervised_Supervised_Learning.ipynb`
  - 초기 모델링(비지도/지도 학습) 단계
- `Infection_DIVS_Modeling_2_MIMIC-IV_Environment_Integrated.ipynb`
  - 환경 변수 통합 모델링 및 점수화(DIVS 통합)
- `Infection_DIVS_Modeling_3_MIMIC-IV_Environment_Tunning.ipynb`
  - 하이퍼파라미터/앙상블 튜닝 단계
- `Infection_DIVS_Modeling_4_MIMIC-IV_Environment_Visualization.ipynb`
  - 모델 결과 시각화/해석 단계
- `Infection_DIVS_Modeling_5_Korea_Validation.ipynb`
  - 한국 적용 관점 검증(Validation) 단계

## 3) 분석/모델링 흐름
1. 코호트 정의 및 전처리(EDA 포함)
2. 비지도/지도 학습 기반 초기 위험 라벨링/예측
3. 환경 리스크 요인 통합(DIVS)
4. 튜닝(Optuna, 스태킹 포함)
5. 시각화 및 해석
6. 한국 적용 검증

## 4) 모델링 메모
- `Modeling_2`:
  - XGBoost 사용 로그 확인
  - Train AUC: `0.7325`
  - Test AUC: `0.7058`
- `Modeling_3`:
  - 필터링 비율 비교 후 상위 60% 선택
  - Optuna 최적 CV AUC: `0.7995`
  - LGBM 단독 Test AUC: `0.7988`
  - 스태킹 앙상블 Test AUC: `0.8002`
  - PR-AUC: `0.6029`
  - 최적 F1: `0.5918`

## 5) 수행 내용
- MIMIC-IV 기반 면역/감염 관리 모델링
- 성능 지표(AUROC, F1-score 등) 산출
- 요양원 대상 맞춤형 가이드라인 시스템의 면역 파트 근거 제공

## 6) 기술 스택(문서 기준)
- Python
- SQL
- Oracle DB
- MIMIC-IV

## 7) 참고
