# 🔬 ANSL Lab Research & Study Log
> **학부연구생 지원을 위한 논문 리뷰 및 인프라 학습 저장소**

---

## 📑 [Paper 01] OrthoRank: Token Selection via Sink Token Orthogonality
**International Conference on Machine Learning (ICML), 2025**

### 1. 연구 목적 
* LLM 추론 시 발생하는 막대한 연산량을 최적화.
* 불필요한 토큰 연산을 선별적으로 제거하여 **추론 속도 향상 및 효율성 극대화**.

### 2. 핵심 이론 및 가설
* **Sink Token의 발견:** 문장 초반 토큰들이 정보 가치 없이 어텐션을 독차지하는 현상에 주목.
* **핵심 가설:** 'Sink Token'과 방향이 다른(**직교하는, Orthogonal**) 토큰일수록 고유한 정보를 가진 중요한 데이터일 것이다.

### 3. 연구 방법 
* 각 레이어에서 토큰과 Sink Token 사이의 **코사인 유사도(Cosine Similarity)**를 측정.
* 유사도가 낮은(즉, 직교성이 높은) 토큰을 '중요 토큰'으로 판별하여 다음 연산에 우선적으로 참여시킴.

### 4. 핵심 결과 
* **높은 정확도 유지:** 동일한 연산량 절감(Sparsity) 조건에서 기존 레이어 푸닝(Layer Pruning) 방식보다 압도적인 정확도를 보임.
* **롱컨텍스트 강점:** 문장이 매우 긴 데이터셋(LongBench)에서도 성능 저하 없이 효율적인 추론 가능.

---
