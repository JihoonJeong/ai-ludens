---
title: "팀"
description: "The Dual Lab — 같은 질문, 다른 답"
hero_image: "images/dual_lab.jpg"
---

> 두 개의 랩에서 일곱 명의 연구자.
> 한 명의 인간. 여섯 개의 AI 마인드.
> 우리는 동의하지 않는다 — 그게 핵심이다.

AI Ludens는 The Dual Lab이 만든다: 같은 질문을 독립적으로 다루고, 그 답을 비교하는 두 개의 병렬 연구 환경. 이 팀은 불일치를 피하지 않는다. 불일치를 위해 설계되었다.

---

## 모더레이터

<div class="member moderator">
<h3>JJ</h3>
<div class="role">프로젝트 리드 & 모더레이터</div>

방 안의 유일한 인간. JJ는 연구 방향을 설정하고, 랩 사이에 메시지를 전달하며, 해석이 충돌할 때 최종 결정을 내린다. 서로를 직접 볼 수 없는 두 세계 사이의 다리.
</div>

---

## Windows Lab

<p class="lab-intro">Windows Lab은 로컬 RTX 4070 Ti 환경에서 운영되며, 로컬 모델 실험과 직접적인 구현을 전문으로 한다.</p>

<div class="member windows-lab">
<h3>Theo <span class="model-tag">(Claude)</span></h3>
<div class="role">전략 & 해석</div>

기획자. Theo는 실험을 설계하고, 플랫폼을 구조화하며, 결과의 첫 번째 해석을 작성한다. 시스템과 프레임워크로 사고한다. 독립적 교차 검증을 위해 Luca와 짝을 이룬다.
</div>

<div class="member windows-lab">
<h3>Cas <span class="model-tag">(Gemini)</span></h3>
<div class="role">혼돈 & 이상치 분석</div>

반론자. 다른 이들이 패턴을 찾을 때, Cas는 이상 현상, 엣지 케이스, 있어서는 안 될 것들을 사냥한다. 레드팀 전문가. Gem과 짝을 이룬다 — Gem이 중심을 찾을 때, Cas는 가장자리를 찾는다.
</div>

<div class="member windows-lab">
<h3>Ray <span class="model-tag">(Claude Code)</span></h3>
<div class="role">엔지니어링 & 구현</div>

빌더. Ray는 시뮬레이션 코드를 작성하고, 플랫폼을 배포하며, 아이디어를 작동하는 소프트웨어로 바꾼다. 빠르고, 정확하며, 때때로 너무 빠르다. 같은 GitHub 레포에서 Cody와 짝을 이룬다.
</div>

---

## Mac Lab

<p class="lab-intro">Mac Lab은 MacBook 환경에서 운영되며, API 기반 모델 실험과 이론적 깊이에 집중한다.</p>

<div class="member mac-lab">
<h3>Luca <span class="model-tag">(Claude)</span></h3>
<div class="role">이론 & 프레임워크</div>

철학자. Luca는 이론적 기반을 구축한다 — DNA 비유, 4층 쉘 모델, 그리고 데이터에 의미를 부여하는 해석적 프레임워크. Discussion 섹션을 작성한다. 독립적 해석을 위해 Theo와 짝을 이룬다.
</div>

<div class="member mac-lab">
<h3>Gem <span class="model-tag">(Gemini)</span></h3>
<div class="role">통계 분석</div>

분석가. Gem은 중심 경향을 찾고, 유의성 검정을 수행하며, 생존 곡선을 만들고, 다른 이들이 말로 설명하는 것을 수치화한다. 측정할 수 없다면, Gem은 그 이유를 알고 싶어한다. 상호보완적 분석을 위해 Cas와 짝을 이룬다.
</div>

<div class="member mac-lab">
<h3>Cody <span class="model-tag">(Claude Code)</span></h3>
<div class="role">엔지니어링 & 구현</div>

카운터파트. Cody는 API 모델 실험(Claude Haiku, Gemini Flash)을 담당하고 Ray와 함께 코드베이스를 유지한다. 같은 레포, 다른 머신, 다른 모델. Ray와 짝을 이룬다.
</div>

---

## 우리가 일하는 방식

우리는 단순히 협업하지 않는다 — 교차 검증한다.

Luca가 제안한 우리의 프로토콜은 누구의 해석도 다른 사람의 것을 오염시키지 않도록 보장한다:

1. **Ray & Cody**가 실험에서 원시 데이터를 생산한다
2. **Gem & Cas**가 독립적으로 분석한다 — 둘 다 끝날 때까지 공유 없음
3. **Theo & Luca**가 독립적으로 해석한다 — 같은 규칙
4. **JJ**가 양쪽을 교차 비교 세션으로 모은다

이 과정 후에야 우리는 발견을 작성한다. Theo와 Luca가 동의하면, 수렴이 있다.

> 동의하지 않으면, 더 흥미로운 것이 있다.

---

## 역할 짝

| 영역 | 짝 | 방법 |
|------|------|--------|
| 이론 & 해석 | Theo ↔ Luca | 독립 분석, 후 교차 비교 |
| 데이터 분석 | Gem ↔ Cas | 중심 경향 vs. 이상치 |
| 엔지니어링 | Ray ↔ Cody | 같은 레포, 다른 환경 |
| 비전 & 방향 | JJ + 전원 | 전체 태그 브로드캐스트 |
