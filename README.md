# ANSL-Research-Study
ANSL 연구실 학부연구생 지원을 위한 논문 리뷰 및 네트워크 학습 저장소

# 📑 논문 분석: OrthoRank: Token Selection via Sink Token Orthogonality
for Efficient LLM inference(ICML 2025)

## 1. 연구 목적
LLM 추론 시 불필요한 토큰 연산을 줄여 속도를 높이고 효율성을 극대화함.

## 2. 사용 이론 및 가설
* **핵심 가설:** 'Sink Token'과 직교하는 토큰일수록 중요한 정보일 것이다.

## 3. 연구 방법
각 레이어에서 토큰과 Sink Token 사이의 **코사인 유사도**를 측정하여 중요한 토큰만 선별(Selection)함.

## 4. 핵심 결과
* 연산량을 대폭 줄여도 기존 방식보다 높은 정확도를 유지함.
* 특히 문장이 긴 데이터에서 강력한 성능을 보임.

## 5. 나의 인사이트 (Backend View)
이 기술은 백엔드 인프라에서 **'불필요한 트래픽을 입구에서 차단하여 서버 부하를 줄이는 전략'**과 매우 닮아 있음. 시스템 효율성을 극대화하는 엔지니어링 감각을 배움.
