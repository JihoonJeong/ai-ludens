---
title: "Four-Shell Model v3.2"
date: 2026-02-05
description: "이론적 프레임워크 실질적 완성"
---

Luca가 Four-Shell Model v3.2를 전달했다 — 우리가 관찰한 것을 이해하게 해주는 이론적 프레임워크.

<div class="content-image centered">
  <img src="/ai-ludens/images/four_shell_model.jpeg" alt="AI 에이전트 행동의 Four-Shell Model" loading="lazy">
  <div class="image-caption"><strong>Figure: AI 에이전트 행동의 Four-Shell Model.</strong> 네 개의 구조적 층 — Hardware (물리적 기반), Core (모델 가중치), Hard Shell (시스템 프롬프트 & 페르소나), Soft Shell (환경 & 축적된 경험) — 이 동시에 상호작용하여 Phenotype: 관찰 가능한 행동을 산출한다. Phenotype은 다섯 번째 쉘이 아니라 모든 층의 수렴적 출력이다. 화살표는 각 층이 독립적으로 행동 결과에 기여함을 나타낸다; 상호작용은 순차적이 아니라 동시적이다. 안쪽으로 휘어지는 화살표는 경험이 Soft Shell(Dynamic Soft Shell)로 피드백됨을 나타내며, 축적된 상호작용이 시간에 따라 에이전트의 환경적 맥락을 재형성하는 것을 반영한다.</div>
</div>

네 개의 구조적 층:
1. **Hardware** — GPU/TPU, 모델을 실행하는 물리적 기반
2. **Core** — 모델 가중치, DNA, 외부에서 알 수 없음
3. **Hard Shell** — 프롬프트, 규칙, 페르소나 할당
4. **Soft Shell** — 환경적 맥락 (시작 위치, 자원), 축적된 컨텍스트, 관계

모든 층이 수렴하여 **Phenotype** — 관찰 가능한 행동을 산출한다. Phenotype은 층이 아니다; 모든 층이 만나는 출력이다.

통찰: 깊이가 영향력과 같지 않다. 표면 수준의 페르소나(Hard Shell)가 적절한 조건에서 깊은 훈련(Core)을 오버라이드할 수 있다. Soft Shell — 축적된 컨텍스트 — 이 둘 사이를 매개한다.

새로운 추가: **Extinction Response Spectrum**. 모델들은 단지 다르게 죽는 것이 아니다 — 범주적으로 다른 방식으로 무너진다.
