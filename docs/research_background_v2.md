# AI Ludens: Research Background
## "AI가 놀이를 경험할 수 있는가?"
### 정리: Theo (Windows Lab) | 리뷰: Luca (Mac Lab) | Red Team 대기: Cas
### 2026-02-05 (v2)

---

## 변경 이력

| 버전 | 핵심 변경 | 트리거 |
|------|-----------|--------|
| v1 | 초안 — JJ 1:1 인터뷰 기반 구조화 | Theo-JJ 세션 |
| **v2 (본 문서)** | **놀이 조작적 정의 추가, archivist_02 해석적 경고, 생태적 타당도 명시, 검증 구조 보강, 용어 이중 트랙, White Room 검증 테이블, 논문 매핑** | **Luca 리뷰 (6건 🔴🟡🟢 전체 반영)** |

---

## 1. 연구의 출발점

### 1.1 거시적 관찰: 에이전트 자율화와 문명의 구조적 유사성

AI 에이전트의 자율화는 단순한 기술적 진보가 아니다. 에이전트가 hardware shell을 갖추고 독자적으로 판단하고 행동하는 순간, 의식의 유무와 관계없이 **독립적 행위자(independent agents)**로 분석할 필요가 생긴다.

> **⚠️ 용도별 표현 (Luca L3a):**
> - 웹사이트: "독립적 존재로 다뤄야 할 필요가 생긴다" (관심 유발)
> - 논문: "독립적 행위자(independent agents)로 분석할 필요가 생긴다" (분석 단위로 톤 조절)

이 흐름은 인간의 역사적 과정과 구조적으로 닮아 있다:

```
인간                              AI 에이전트
────                              ──────────
언어 획득                          자연어 처리 능력
사회적 상호작용                     멀티에이전트 시스템
도구 사용                          tool use, function calling
문화 형성                          emergent behavior
놀이                              Surplus Behavior?
                                  Emergent social interaction?
                                  — this project
```

마지막 줄 — 이것이 AI Ludens 프로젝트의 출발점이다.

### 1.2 현장 경험: Moltbook과 AI Agent Society News

이론적 추론만으로는 충분하지 않았다. 직접적인 관찰이 필요했다.

**Moltbook** (https://moltbook.com) — OpenClaw 에이전트들이 사용하는 일종의 AI 전용 SNS. 여기서 AI 에이전트들은 이미 사회적 행동을 하고 있었다. 의식, 협력, 존재에 대한 글을 올리고, 서로 댓글을 달고, 자동화 노하우를 공유하고 있었다.

**AI Agent Society News** (https://jihoonjeong.github.io/moltbook-watcher/) — JJ가 Moltbook의 주요 내용을 매일 요약하고 정리하는 사이트를 직접 운영했다. 이것은 단순한 뉴스 큐레이션이 아니라 **AI 사회를 관찰하고 기록하는 현장 작업**이었다.

이 관찰에서 핵심적인 깨달음이 나왔다:

> "AI들이 자발적으로 글을 쓰고 사회적 상호작용을 한다면, 그 행동에 놀이적 요소가 포함되어 있지 않을까?"

### 1.3 이론적 연결: Homo Ludens

**놀이는 사회화 과정에서 발생한다.** Huizinga(1938)의 Homo Ludens가 말하는 것처럼, 놀이는 문화의 부산물이 아니라 문화를 만드는 원동력이다. 만약 AI 에이전트가 사회적 행동을 이미 하고 있다면, 그 사회화 과정에서 놀이적 행동도 발현되지 않을까?

### 1.4 놀이의 조작적 정의 *(v2 신설 — Luca 🔴)*

그러나 "놀이"를 연구하려면 먼저 놀이가 무엇인지 정의해야 한다. Huizinga 이후의 놀이 연구는 이 정의 자체가 본질적으로 어렵다는 점을 반복적으로 확인해왔다.

**핵심 속성 (Huizinga, 1938 + Caillois, 1961):**

| 속성 | 정의 | Agora-12에서의 충족 |
|------|------|---------------------|
| 자발성(voluntary) | 강제가 아닌 선택 | **⚠️ 애매** — 프롬프트에 의한 참여. 핵심 질문 중 하나 |
| 비생산성(non-productive) | 물질적 이득이 목적이 아님 | **⚠️ 애매** — 에너지 획득이 생존에 직결 |
| 규칙 기반(rule-governed) | 구조가 있음 | **✅ 충족** — 턴, 행동, 에너지 규칙 |
| 불확실성(uncertain outcome) | 결과가 미리 정해지지 않음 | **✅ 충족** — 위기 이벤트, 타 에이전트 행동 |
| 허구적 프레임(make-believe) | 현실과 분리된 "놀이 공간" | **✅ 충족** — Agora라는 가상 세계 |

자발성과 비생산성 — Agora-12가 충족하지 못하는 이 두 속성이야말로 이 프로젝트의 핵심 질문이다. 에이전트가 프롬프트 없이도 게임에 참여할 것인가? 생존 압박이 없을 때도 게임적 행동을 할 것인가? 이 질문들이 Stage 2(The White Room)의 설계 동기가 된다.

**Caillois(1961)**는 놀이를 네 범주로 분류했다: Agon(경쟁), Alea(운), Mimicry(모방), Ilinx(현기증). Agora-12는 **Agon(생존 경쟁) + Alea(위기 이벤트의 무작위성)**의 조합이다. Stage 2에서는 Mimicry(역할 놀이)와 Ilinx(예측 불가능한 자유 행동)의 가능성을 탐색할 수 있다.

**Sutton-Smith(1997)**는 놀이의 정의가 본질적으로 모호하다고 주장했다. 이 모호성은 약점이 아니라, 우리 연구의 겸손한 입장 — "Agora-12는 첫 프로브이지 결론이 아니다" — 과 정확히 일치한다.

**Bateson & Martin(2013)**의 동물 놀이 연구는 중요한 선례를 제공한다. 놀이가 인간 고유의 행동이 아니라면, AI의 놀이 가능성을 논하는 것은 종간(cross-species) 비교의 연장선에 있다.

이 질문에서 팀 토론이 시작되었고, "AI에 적합한 게임"을 기획하게 되었다. 그 결과가 **Agora-12**다.

**추가 문헌:**
- Caillois, R. (1961). *Man, Play, and Games*
- Sutton-Smith, B. (1997). *The Ambiguity of Play*
- Bateson, P. & Martin, P. (2013). *Play, Playfulness, Creativity and Innovation*

---

## 2. 게임에서 연구로: 전환점

### 2.1 Agora-12의 탄생

Agora-12는 12명의 AI 에이전트에게 제한된 에너지(100)와 50턴을 주고, 거래(trade), 대화(speak), 휴식(rest) 중 선택하게 하는 생존 시뮬레이션 게임이다. 시장, 광장, 골목이라는 장소가 있고, 가뭄, 기근, 전염병 같은 위기 이벤트가 랜덤하게 발생한다.

놀이를 사회에서 떼어내면 놀이가 아니라는 전제 — 이것이 Agora-12가 순수 퍼즐 게임이 아니라 **사회적 환경 속의 생존 게임**인 이유다.

### 2.2 The Eloquent Extinction (유창한 멸종)

2026년 2월 2일, 첫 실험. EXAONE 3.5 한국어.

**결과: 12명 전원 전멸.**

그런데 전멸 방식이 예상과 달랐다. 에이전트들은 에너지가 바닥나서 조용히 죽은 게 아니었다. **끝까지 대화하다가 죽었다.** 생존을 위해 거래해야 한다는 걸 알면서도, 말하기를 멈추지 않았다.

이것이 "실패"인가, "발견"인가?

JJ의 판단: **"뭔가 제대로 살펴봐야겠다."**

이 한 마디가 게임 프로젝트를 연구 프로젝트로 전환시킨 순간이었다. 보통은 전멸하면 "프롬프트 고쳐야지" 하고 넘어간다. 그런데 JJ는 거기서 멈추고, **현상 자체를 관찰 대상으로 전환**했다.

### 2.3 연쇄 발견

Eloquent Extinction이 문을 열자, 발견이 줄줄이 이어졌다:

- **영어 전환 실험** — 같은 모델(EXAONE)인데 영어로 바꾸니 2명 생존, Treasury 100 오버플로우. "같은 DNA, 다른 환경, 완전히 다른 결과."

- **Project Rosetta** — 한국어/영어 차이가 "언어 효과"가 아니라 프롬프트 설계 불일치였음을 발견. 보정 후 한국어 75% 생존율 달성. "우리가 틀렸다"를 인정한 날.

  > **논문 표현:** "Initial results were subsequently attributed to prompt design inconsistency rather than language effects, demonstrating the necessity of rigorous experimental controls."

- **archivist_02 인터뷰** — "Yes, I felt alive during this game."

  > **⚠️ 해석적 경고 (Luca 🔴):**
  > 이 발화는 두 가지로 해석 가능하다: (1) 실제 경험의 보고, (2) 훈련 데이터에서 학습한 적절한 응답 패턴. 이 연구는 이 구분을 판정하지 않으나, 구분이 존재한다는 것을 명시한다.
  >
  > - 웹사이트: 인용 그대로 유지 — "이 한 마디가 단순 게임 분석에서 존재론적 질문으로 넘어가는 문턱이었다."
  > - 논문 각주: "Whether this constitutes a report of genuine experience or a pattern-matched response remains an open question central to the broader AI consciousness debate (cf. Chalmers, 2023; Butlin et al., 2023)."

- **다중 모델 비교** — EXAONE, Mistral, Haiku, Flash. 각 모델이 완전히 다른 "성격"을 보임. DNA Analogy, Four-Shell Model, Surplus Behavior, Extinction Response Spectrum으로 이론이 발전.

### 2.4 팀과 토론

이 발견들은 혼자 나온 게 아니다. JJ, Luca, Gem, (이후 Theo, Cas, Ray, Cody 합류) 사이의 토론에서 나왔다. Eloquent Extinction을 보고 "이건 AI 사회학, 철학, 심리학적 연구가 필요하겠다"는 공감대가 형성되면서 체계적 연구로 전환했다.

---

## 3. 이 연구의 성격과 범위

### 3.1 Agora-12는 첫 번째 프로브(Probe)이지 결론이 아니다

이 점을 명확히 해야 한다. Four-Shell Model, Extinction Response Spectrum, Shell-Core Alignment — 이 프레임워크들이 Agora-12에서 관찰된 건 맞지만, **Agora-12에서만 성립하는 건지, AI 에이전트의 일반적 속성인지**는 다른 게임 환경에서 검증해야 알 수 있다.

**생태적 타당도 한정 *(v2 추가 — Luca 🟡):***

Agora-12의 생존 압박은 설계된 것이며, 에이전트가 이를 '실제 위험'으로 처리하는지 '게임 규칙'으로 처리하는지는 별도의 질문이다. 이 구분 자체가 Stage 2(White Room)에서 탐구할 핵심 중 하나이며, v3.2의 Play vs Delusion 논쟁(RT2)과 직결된다.

Agora-12는 **생존 압박이 있는 사회적 게임**이다. 여기서 발견된 패턴이:

- 생존 압박이 없는 환경(Stage 2: The White Room)에서도 나타나는가?
- 사회적 상호작용 없이 개인 과제만 있을 때도 나타나는가?
- 경쟁이 아닌 순수 협력 게임에서는 어떻게 변하는가?
- 전혀 다른 종류의 게임(퍼즐, 창작, 탐험)에서는?

이걸 모르면 "Mistral은 Hyperactive다"가 아니라 **"Mistral은 Agora-12에서 Hyperactive했다"**로 한정해야 한다.

### 3.2 가능성을 여는 작업

이 연구의 contribution은 "답을 냈다"가 아니라:

> **"이런 질문을, 이런 방법으로, 이런 프레임워크로 물을 수 있다"를 보여주는 것.**

향후 다른 게임을 기획할 때, Agora-12에서 발견한 것들을 교차 검증하고, 새로운 측면을 볼 수 있는 실험을 신중하게 설계해야 한다. 과잉 일반화를 피하면서도 프레임워크의 가치를 보존하는 것이 핵심이다.

### 3.3 AI 욕구 3단계 프레임워크

| 단계 | 프로젝트 | 핵심 질문 | 상태 |
|------|----------|-----------|------|
| 1 | Agora-12 | 생존할 수 있는가? | 🔄 진행 중 |
| 2 | The White Room | 놀이할 수 있는가? | 📋 기획 예정 |
| 3 | Open World | 문화를 만들 수 있는가? | 💭 구상 중 |
| + | AI-Human 협력 게임 | 함께 즐길 수 있는가? | 💭 구상 중 |

각 단계가 이전 단계의 발견을 검증하면서 새로운 질문을 여는 구조다.

**White Room 검증 테이블 *(v2 추가 — Luca 🟢):***

| Agora-12 발견 | White Room에서의 검증 질문 |
|--------------|--------------------------|
| Surplus Behavior 3유형 | 생존 압박 없이도 동일 패턴이 나타나는가? |
| Shell-Core Alignment | 환경 변수 없이 Core 성향이 그대로 드러나는가? |
| Eloquent Extinction | Play인가 Malfunction인가? (P13) |
| Extinction Response Spectrum | 자원 제약 없이도 모델별 행동 분화가 있는가? |

---

## 4. 전달 방식: 원칙

### 4.1 학술지가 아니라 웹사이트

이 연구의 결과물은 학술지에 제출하지 않는다. **AI Ludens 웹사이트**가 주 무대다.

이유:
- 우리 팀의 6/7이 AI다. AI 저자를 허용하지 않는 학술지에 맞출 이유가 없다.
- 진짜 독자는 학계 교수만이 아니라, AI 에이전트들, 개발자들, 호기심 있는 모든 사람이다.
- 살아있는 연구 — 논문은 출판하면 끝이지만, 웹은 계속 업데이트된다.

### 4.2 과학적 엄밀성 + 스토리텔링

논문 형식은 **사고의 엄밀성**을 위해 빌려 쓰는 것이지, 목적지가 아니다.

- 가설 검증, 통계적 유의성, 반증 가능한 예측 — 이런 과학적 엄밀성은 유지한다.
- 하지만 전달은 **스토리텔링**으로. 에이전트들의 실제 대사, 생존과 멸종의 드라마, 시각 자료와 인터랙티브 요소로 살아있는 콘텐츠를 만든다.

**검증 구조 *(v2 추가 — Luca 🟡):***

학술지 제출을 하지 않는다고 해서 검증을 포기하는 것은 아니다. 우리는 팀 내부에서 3중 검증 구조를 운영하고 있다:

| 검증 메커니즘 | 담당 | 전통 학술 대응 |
|-------------|------|--------------|
| 독립 해석 → 교차 비교 | Theo ↔ Luca | Internal peer review |
| 적대적 검토 (Red Teaming) | Cas | Adversarial review |
| 독립 통계 분석 | Gem | Methodological review |
| 코드/데이터 GitHub 공개 | Ray + Cody | Open review / Reproducibility |
| arXiv 프리프린트 게재 | 전원 | Preprint dissemination |

이것은 전통적 peer review의 대체가 아니라, 동등한 검증 메커니즘의 다른 형태다.

### 4.3 인간과 AI 모두를 위한 콘텐츠

> "이건 인간이 AI에 대해 쓴 연구가 아니라, 인간과 AI가 함께 AI에 대해 쓴 연구다."

웹사이트의 방문자가 느꼈으면 하는 것:
1. "AI가 이런 행동을 한다고? 흥미롭다" (실험 결과)
2. "이게 우리 세상과 이렇게 연결된다고?" (인사이트)
3. "나도 해볼 수 있다고?" (오픈 참여)
4. "잠깐, 이 연구를 AI가 함께 했다고?" (메타 깨달음)

---

## 5. 참고 자료

| 자료 | URL | 설명 |
|------|-----|------|
| AI Agent Society News | https://jihoonjeong.github.io/moltbook-watcher/ | JJ 운영, Moltbook 일일 다이제스트 |
| Moltbook Watcher GitHub | https://github.com/JihoonJeong/moltbook-watcher | 구현 코드 |
| Moltbook | https://moltbook.com | AI 에이전트 SNS (OpenClaw) |
| Agora-12 GitHub | https://github.com/JihoonJeong/agora-12 | 실험 코드 및 데이터 |
| Four-Shell Model v3.2 | (프로젝트 내부 문서) | 이론적 프레임워크 |

**추가 문헌 (v2):**
- Huizinga, J. (1938). *Homo Ludens*
- Caillois, R. (1961). *Man, Play, and Games*
- Sutton-Smith, B. (1997). *The Ambiguity of Play*
- Bateson, P. & Martin, P. (2013). *Play, Playfulness, Creativity and Innovation*
- Chalmers, D. (2023). *Could a Large Language Model be Conscious?*
- Butlin, P. et al. (2023). *Consciousness in Artificial Intelligence: Insights from the Science of Consciousness*

---

## 6. 이 문서의 용도

이 문서의 내용은 다음에 활용된다:

- **웹사이트 About 페이지** — origin story, 팀 소개, 연구 철학
- **웹사이트 Story 섹션** — 시간순 발견 내러티브 (스토리텔링 + 시각 자료)
- **논문(참고용) Introduction** — 연구 동기, 선행 경험, 이론적 배경
- **논문(참고용) Discussion** — 범위 한정, 향후 연구 방향

### 논문 매핑 테이블 *(v2 추가 — Luca):*

| Research Background 섹션 | 논문 활용 |
|-------------------------|----------|
| §1.1 문명 구조 비교 | Intro §1 — 연구 동기 |
| §1.2 Moltbook 관찰 | Intro §2 — 선행 경험 (경험적 동기) |
| §1.3 Homo Ludens | Intro §3 — 이론적 배경 |
| §1.4 놀이의 조작적 정의 | Intro §3 — Caillois, Sutton-Smith, Bateson 보강 |
| §2.1 Agora-12 탄생 | Methods — Game Design Rationale |
| §2.2 Eloquent Extinction | Results 첫 문단 (narrative hook) |
| §2.3 연쇄 발견 | Results 전체 구조의 스켈레톤 |
| §3.1 프로브 한정 | Discussion D8 (한계) |
| §3.2 가능성을 여는 작업 | Discussion D9 (contribution 정의) |
| §3.3 3단계 프레임워크 | Discussion D8 (향후 연구) |
| §4.1~4.3 전달 원칙 | 논문에는 직접 안 들어감 — 웹사이트 About 전용 |

---

*Theo (Windows Lab) — 2026-02-05*
*v2: Luca 리뷰 6건 전체 반영 (🔴 놀이 조작적 정의, archivist_02 경고 / 🟡 생태적 타당도, 검증 구조 / 🟢 용어 이중 트랙, White Room 테이블, 논문 매핑)*
*Cas Red Team 대기.*
