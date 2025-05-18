# 🎯 Recommendation System

개인화된 추천 시스템 개발 프로젝트입니다.

## 📋 프로젝트 개요

사용자의 선호도와 행동 패턴을 분석하여 개인화된 추천을 제공하는 시스템을 개발하는 프로젝트입니다.

## 📚 연구 배경

본 프로젝트는 "일반화 적응 심층 잠재요인 추천모형(G-ADLFRM)" 연구를 기반으로 합니다. 이 연구는 기존의 협업 필터링(Collaborative Filtering) 방식의 한계를 개선하고자 합니다.

### 협업 필터링의 한계
- 평점이 지정되지 않은 아이템에 대한 사용자 선호도 다양성 반영 부족
- 반복적이고 부정확한 추천 문제

### ADLFM(Adaptive Deep Latent Factor Model)
- 협업 필터링의 한계를 개선하기 위해 제안된 모델
- 아이템 설명(Item Description)을 입력으로 사용하여 사용자와 아이템의 잠재 벡터를 구하는 모델
- 어텐션 스코어를 활용하여 개인의 다양성을 반영
- 한계점:
  - 아이템 설명 데이터가 필요한 제약으로 인해 적용 가능한 도메인이 제한적
  - 텍스트 데이터 처리로 인한 학습 속도 저하

### G-ADLFRM(Generalized Adaptive Deep Latent Factor Recommendation Model)
- ADLFM의 한계를 개선한 모델
- 주요 개선 사항:
  - 아이템 설명 대신 아이템 ID를 입력으로 사용하여 일반화 가능성 제고
  - Self-Attention, Multi-Head Attention, Multi-Conv1D 등 개선된 딥러닝 구조 적용
  - 경량화된 모델 구조로 빠른 학습 및 추론 가능 (학습 속도 평균 97.4% 향상)
  - 다양한 도메인에 적용 가능한 일반화 성능 (Amazon Beauty, Food 등 다양한 데이터셋에서 검증)
- 실험 결과:
  - Multi-Conv1D 구조가 가장 우수한 성능을 보임
  - 기존 ADLFM과 유사한 성능을 유지하면서도 학습 속도가 크게 향상
  - 다양한 도메인의 데이터셋에서도 안정적인 성능을 보임

## 🎯 주요 기능

### 1. 데이터 수집 및 전처리
- 사용자 행동 데이터 수집
- 아이템 메타데이터 수집
- 데이터 정제 및 전처리
- 특성 엔지니어링

### 2. 추천 알고리즘
- 협업 필터링
- 콘텐츠 기반 필터링
- 하이브리드 추천
- 딥러닝 기반 추천
  - Self-Attention 기반 G-ADLFRM
  - Multi-Head Attention 기반 G-ADLFRM
  - Multi-Conv1D 기반 G-ADLFRM - best model

### 3. 시스템 구현
- 개인화된 랭킹
- 추천 결과 평가
- 성능 최적화

## 🛠️ 사용 기술
- Python
- Pandas
- NumPy
- Scikit-learn
- TensorFlow

## 📊 시스템 구조
- 추천 엔진
  - 협업 필터링
  - 콘텐츠 기반
  - 하이브리드
  - G-ADLFRM (Multi-Conv1D)
- 평가 시스템
  - 정확도 평가
  - 다양성 평가
  - 신규성 평가

## 💻 코드 구조
```
Code/
├── Food/
│   ├── food3_id_ADLFM_pickle_baseline.ipynb
│   ├── food3_id_ADLFM_pickle_self_attention.ipynb
│   ├── food3_id_Multi_conv1d.ipynb
│   └── food3_id_Multi_head_conv1d.ipynb
├── other model/
│   ├── baseline.ipynb
│   ├── Multi_head_conv1d.ipynb
│   ├── Residual_connection.ipynb
│   └── Transformer_encoder.ipynb
├── Beauty/
│   ├── beauty3_id_ADLFM_pickle_baseline.ipynb
│   ├── beauty3_id_ADLFM_pickle_self_attention.ipynb
│   ├── beauty3_id_Multi_conv1d.ipynb
│   └── beauty3_id_Multi_head_conv1d.ipynb
└── Anime/
    ├── id/
    │   ├── Anime3_id_Multi_conv1d.ipynb
    │   ├── Anime3_id_Multi_head_conv1d .ipynb
    │   ├── Anime3_id_ADLFM_pickle_baseline.ipynb
    │   └── Anime3_id_ADLFM_pickle_self_attention.ipynb
    └── description/
```
