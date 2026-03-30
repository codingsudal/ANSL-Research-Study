# 🔬 ANSL Lab Research & Study Log
> **학부연구생 지원을 위한 논문 리뷰 및 인프라 학습 저장소**

---

## 📑 [Paper 01] OrthoRank: Token Selection via Sink Token Orthogonality
**International Conference on Machine Learning (ICML), 2025**

### 1. 연구 목적 (Research Objective)
* LLM 추론 시 발생하는 막대한 연산량을 최적화.
* 불필요한 토큰 연산을 선별적으로 제거하여 **추론 속도 향상 및 효율성 극대화**.

### 2. 핵심 이론 및 가설 (Theory & Hypothesis)
* **Sink Token의 발견:** 문장 초반 토큰들이 정보 가치 없이 어텐션을 독차지하는 현상에 주목.
* **핵심 가설:** 'Sink Token'과 방향이 다른(**직교하는, Orthogonal**) 토큰일수록 고유한 정보를 가진 중요한 데이터일 것이다.

### 3. 연구 방법 (Methodology)
* 각 레이어에서 토큰과 Sink Token 사이의 **코사인 유사도(Cosine Similarity)**를 측정.
* 유사도가 낮은(즉, 직교성이 높은) 토큰을 '중요 토큰'으로 판별하여 다음 연산에 우선적으로 참여시킴.

### 4. 핵심 결과 (Key Results)
* **높은 정확도 유지:** 동일한 연산량 절감(Sparsity) 조건에서 기존 레이어 푸닝(Layer Pruning) 방식보다 압도적인 정확도를 보임.
* **롱컨텍스트 강점:** 문장이 매우 긴 데이터셋(LongBench)에서도 성능 저하 없이 효율적인 추론 가능.

---

### 💡 나의 인사이트 (Backend & Infra View)
> "OrthoRank의 메커니즘은 백엔드 인프라의 **'Early Drop' 전략**과 닮아 있습니다."

* **트래픽 최적화:** 대규모 트래픽이 몰릴 때 모든 요청을 처리하기보다, 입구에서 헤더(직교성)를 검사해 불필요한 요청을 차단함으로써 전체 시스템의 가용성을 사수하는 전략과 유사성을 느꼈습니다.
* **엔지니어링 마인드:** 단순히 모델을 돌리는 것을 넘어, 리소스 효율을 극대화하여 서비스 단가를 낮추고 성능을 높이는 교수님의 연구 철학에서 엔지니어로서 나아가야 할 방향을 배웠습니다.
