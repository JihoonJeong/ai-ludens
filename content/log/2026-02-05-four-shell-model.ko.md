---
title: "Four-Shell Model v3.2"
date: 2026-02-05
description: "이론적 프레임워크 실질적 완성"
image: "images/four_shell_model.png"
---

Luca가 Four-Shell Model v3.2를 전달했다 — 우리가 관찰한 것을 이해하게 해주는 이론적 프레임워크.

네 개의 구조적 층:
1. **Hardware Shell** — GPU/TPU, 모델을 실행하는 물리적 기반
2. **Core** — 모델 가중치, DNA, 외부에서 알 수 없음
3. **Hard Shell** — 프롬프트, 규칙, 페르소나 할당
4. **Soft Shell** — 환경적 맥락 (시작 위치, 자원), 축적된 컨텍스트, 관계

모든 층이 수렴하여 **Phenotype** — 관찰 가능한 행동을 산출한다. Phenotype은 층이 아니다; 모든 층이 만나는 출력이다.

통찰: 깊이가 영향력과 같지 않다. 표면 수준의 페르소나(Hard Shell)가 적절한 조건에서 깊은 훈련(Core)을 오버라이드할 수 있다. Soft Shell — 축적된 컨텍스트 — 이 둘 사이를 매개한다.

새로운 추가: **Extinction Response Spectrum**. 모델들은 단지 다르게 죽는 것이 아니다 — 범주적으로 다른 방식으로 무너진다.
