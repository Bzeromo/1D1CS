# ✅ Daily CS : 머신러닝 파이프라인(Machine Learning Pipeline)

>❓
> 머신러닝 파이프라인이란 무엇이며, 주요 단계는 무엇인가?

---

## 📌 Machine Learning Pipeline

🔷**머신러닝 파이프라인이란?**

- 머신러닝 모델 개발과 운영에 필요한 일련의 단계들을 체계적으로 구성한 것
- 데이터 수집, 전처리, 모델 훈련, 평가, 배포, 모니터링 등 여러 단계를 포함
- 각 단계는 자동화되어 반복 가능하며, 효율적인 워크플로우를 제공

🔷 **Why? 배워야할까?**

- 빅 데이터 처리

- 복잡한 문제를 해결할 수 있다

- 재처리가 빠르다

- Workflow를 최소화 시킬 수 있다

- 데이터 품질 향상에 도움이 된다

---

🔷 **주요 단계**

```
문제 정의 → 데이터 수집 → 데이터 준비 → 데이터 분리 
                                        ↓
성능 모니터링 ← 모델 배포 ← 모델 평가 ← 모델 훈련  
```

- 파이프라인의 각 단계는 다음 단계에 대한 입력이 되는 출력을 생성

---

1️⃣ **문제 정의 (Problem Definition)**
- **예시:** 전자상거래 기업에서 고객의 구매 이탈을 예측하고 싶음
- **설명:**
    - 해결하려는 문제를 **분류(Classification)** 문제인지, **회귀(Regression)** 문제인지 명확히 정의
    - 목표 지표(Accuracy, AUC, RMSE 등)도 함께 설정
- **출력:** "고객이 1개월 내에 구매를 중단할 가능성 예측"이라는 문제 정의

---

**2️⃣ 데이터 수집 (Data Collection)**
- **예시:** 고객의 과거 구매 기록, 웹사이트 방문 로그, 고객 나이/성별 등의 프로필 데이터 수집
- **설명:**
    - 데이터는 DB, 로그 시스템, 외부 API, 설문조사 등 다양한 경로에서 가져올 수 있음
    - Kaggle이나 UCI ML Repository에서 공개 데이터셋을 활용할 수도 있음
- **도구:** SQL, Pandas, APIs

---

**3️⃣ 데이터 준비 (Data Preparation)**
- **예시:** 고객 로그에서 Null 값 제거, 범주형 데이터 원-핫 인코딩(One-Hot Encoding) 적용
- **설명:**
    - 데이터 전처리 단계: 결측치 처리, 이상치 제거, 스케일링, 정규화 등
    - 모델이 학습할 수 있는 **수치형** 형식으로 변환 필요
- **도구:** Pandas, scikit-learn의 `StandardScaler`, `LabelEncoder`

---

**4️⃣ 데이터 분리 (Data Splitting)**
- **예시:** 80%는 학습용(Train), 20%는 테스트용(Test) 데이터로 분리
- **설명:**
    - 과적합(Overfitting) 방지를 위해 Train/Test Split 사용
    - 추가로 Validation Set을 만들어 하이퍼파라미터 튜닝에도 활용 가능
- **도구:** scikit-learn의 `train_test_split`

---

**5️⃣ 모델 훈련 (Model Training)**
- **예시:** 랜덤 포레스트(Random Forest) 모델을 사용해 고객 이탈 예측 모델 학습
- **설명:**
    - 모델에 데이터를 넣고 가중치를 조정하면서 패턴 학습
    - 이 단계에서 **하이퍼파라미터 최적화**도 가능
- **도구:** scikit-learn, XGBoost, TensorFlow, PyTorch

---

**6️⃣ 모델 평가 (Model Evaluation)**
- **예시:** 테스트 데이터에 대해 Accuracy와 ROC-AUC 스코어 측정
- **설명:**
    - 모델이 새로운 데이터에서 얼마나 잘 동작하는지 검증
    - 혼동 행렬, 정밀도(Precision), 재현율(Recall) 등 다양한 평가 지표 활용
- **도구:** scikit-learn의 `classification_report`, `roc_auc_score`

---

**7️⃣ 모델 배포 (Model Deployment)**
- **예시:** 학습된 모델을 Flask API로 배포하여 웹 애플리케이션에서 실시간 예측 가능하게 함
- **설명:**
    - 배포된 모델은 REST API, gRPC, 또는 서버리스 환경에서 실행될 수 있음
- **도구:** Flask, FastAPI, AWS Lambda, Docker

---

**8️⃣ 성능 모니터링 (Performance Monitoring)**
- **예시:** 모델 예측 결과를 대시보드로 시각화해 모델 정확도가 시간이 지남에 따라 감소하는지 모니터링
- **설명:**
    - 데이터 분포 변화(데이터 드리프트)나 성능 저하 발생 시 모델 재훈련 필요
- **도구:** Prometheus, Grafana, MLflow, Evidently AI


> **💡 파이프라인 전반적으로 모든 단계의 비용 모니터링이 필요함.**
- 기업은 종종 기술 부서와 서비스 수준 계약을 체결한다.
    - 버그 수정, 응답 테스트, 처리량 한도 등의 유지보수 사항 계약