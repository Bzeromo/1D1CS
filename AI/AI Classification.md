# ✅ Daily CS : AI 분류(AI Classification)

>❓
> AI 분류란 무엇이며, 주요 유형과 특징은 무엇일까?

***

## 📌 정의
🔷 **AI(인공지능)를 그 목적, 기능, 학습 방식 등에 따라 여러 유형으로 나누는 것**

- AI는 매우 다양한 분야와 응용이 가능하기 때문에, 이를 체계적으로 이해하고 활용하기 위해 분류가 필요


- 분류 기준에 따라 AI의 특성과 적용 분야가 달라짐

***

## 🔍 주요 분류 기준과 기준에 따른 유형

🔷 **학습 모델 내 분류**


- **지도 학습 (Supervised Learning)**

    - **정의: 입력 데이터와 그에 대응하는 정답(Label)을 함께 학습하는 방식**

    - **주요 목적: `예측(Prediction)`**

    - **예시 알고리즘:**

        - `회귀(Regression)`: 선형 회귀(Linear Regression), 로지스틱 회귀(Logistic Regression)

        - `분류(Classification)`: 결정 트리(Decision Tree), SVM, 랜덤 포레스트(Random Forest)

        - `딥러닝(Deep Learning)`: CNN, RNN 등

    - **활용 사례:**

        - 이메일 스팸 분류

        - 주식 가격 예측

        - 이미지 분류(고양이 vs 개)


- **비지도 학습 (Unsupervised Learning)**

    - **정의: 정답(Label) 없이 입력 데이터의 패턴이나 구조를 찾는 방식**

    - **주요 목적: `군집화(Clustering)` / `차원 축소(Dimensionality Reduction)`**

    - **예시 알고리즘:**

        - `K-means`, `계층적 군집화(Hierarchical Clustering)`

        - `PCA(Principal Component Analysis)`

        - `Autoencoder`

    - **활용 사례:**

        - 고객 세분화(Customer Segmentation)

        - 데이터 시각화

        - 이상 탐지(Anomaly Detection)


- **강화 학습 (Reinforcement Learning)**

    - **정의:** **행위(Action)**를 취했을 때 환경(Environment)으로부터 받는 **보상(Reward)**을 통해 학습하는 방식

    - **주요 목적: `정책 최적화(Policy Optimization)`**

    - **예시 알고리즘:**

        - `Q-Learning`

        - `SARSA`

        - `Deep Q-Network (DQN)`

    - **활용 사례:**

        - 게임 AI (알파고)

        - 로봇 제어

        - 자율주행차

🔷 **인간의 기능에 따른 분류**


- **머신 비전 (Machine Vision)**

    - **정의: 인간의 시각 기능을 컴퓨터가 수행하는 기술**

    - **주요 기술: `이미지 처리(Image Processing)`, `객체 인식(Object Detection)`**

    - **활용 사례:**

        - 얼굴 인식 시스템

        - 의료 영상 분석(CT, MRI)

        - 공장 제품 불량 검출


- **머신러닝 (Machine Learning)**

    - **정의: 데이터에서 패턴을 학습하고 예측·결정을 수행하는 인공지능 기술 전반**

    - **범위: 지도/비지도/강화 학습을 모두 포함하는 개념**

    - **활용 사례: 추천 시스템, 금융 사기 탐지, 고객 이탈 예측**


- **자연어 처리 (Natural Language Processing, NLP)**

    - **정의: 인간의 언어 이해 기능을 컴퓨터에 구현**

    - **주요 기술: 형태소 분석, 개체명 인식(NER), 감성 분석(Sentiment Analysis)**

    - **활용 사례:**

        - 챗봇(Chatbot)

        - 기계 번역(Machine Translation)

        - 음성 비서(Voice Assistant)


- **자연어 생성 (Natural Language Generation, NLG)**

    - **정의: 컴퓨터가 인간이 이해할 수 있는 자연스러운 언어를 생성하는 기술**

    - **주요 기술: GPT, LLaMA, BERT 기반 생성 모델**

    - **활용 사례:**

        - 자동 기사 작성

        - 시·소설 창작

        - 코드 자동 생성
