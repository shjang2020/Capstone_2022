# 📁 Code Structure

이 디렉토리는 추천 시스템 구현을 위한 코드들을 포함하고 있습니다. 각 하위 디렉토리는 서로 다른 데이터셋에 대한 실험 결과와 모델 구현을 담고 있습니다.

## 📂 디렉토리 구조

### Anime/
- Anime Recommendation Database(2016) 데이터셋을 사용한 실험 코드
- 사용자-아이템 평점 데이터를 기반으로 한 추천 모델 구현
- G-ADLFRM의 세 가지 변형 모델 (Self-Attention, Multi-Head, Multi-Conv1D) 구현

### Beauty/
- Amazon Beauty Products Ratings(2018) 데이터셋을 사용한 실험 코드
- 뷰티 제품 도메인에 대한 추천 모델 구현
- 다양한 도메인에서의 모델 성능 검증을 위한 코드

### Food/
- Amazon Fine Food Reviews(2017) 데이터셋을 사용한 실험 코드
- 식품 리뷰 데이터를 활용한 추천 모델 구현
- 텍스트 데이터와 평점 데이터를 결합한 실험 코드

### other model/
- 기존 추천 시스템 모델들의 구현 코드
- 협업 필터링, 콘텐츠 기반 필터링 등 전통적인 추천 알고리즘 구현
- 성능 비교를 위한 베이스라인 모델 구현

## 🛠️ 주요 기능

각 디렉토리에는 다음과 같은 공통적인 기능들이 구현되어 있습니다:

1. 데이터 전처리
   - 데이터 로딩 및 정제
   - 특성 엔지니어링
   - 학습/검증/테스트 데이터 분할

2. 모델 구현
   - G-ADLFRM의 세 가지 변형 모델
   - 모델 학습 및 추론
   - 하이퍼파라미터 튜닝

3. 평가 및 분석
   - MAE(Mean Absolute Error) 기반 성능 평가
   - 학습 속도 측정
   - 모델 간 성능 비교

## 📊 실험 결과

각 데이터셋별 실험 결과는 다음과 같습니다:

### Anime Recommendation Database
- Multi-Conv1D 구조가 가장 우수한 성능을 보임
- 학습 속도가 기존 ADLFM 대비 평균 97.4% 향상

### Amazon Beauty Products
- 다양한 모델 구조에서 안정적인 성능을 보임
- 도메인 특성에 따른 모델 성능 차이 분석

### Amazon Fine Food Reviews
- 텍스트 데이터와 평점 데이터의 결합 효과 분석
- 도메인 특화된 특성 추출 방법 연구

## 💻 실행 방법

각 디렉토리의 코드는 다음과 같이 실행할 수 있습니다:

1. 필요한 패키지 설치
```bash
pip install -r requirements.txt
```

2. 데이터 전처리
```bash
python preprocess.py
```

3. 모델 학습 및 평가
```bash
python train.py
```

4. 결과 분석
```bash
python evaluate.py
```

## 📝 참고사항

- 모든 실험은 Google Colab Pro 환경에서 수행되었습니다.
- 모델의 하이퍼파라미터는 각 데이터셋의 특성에 맞게 조정되었습니다.
- 실험 결과는 30 epoch 기준으로 측정되었습니다. 