# AI Ludens 플랫폼 기획서 v0.3
### 📢 All (from Theo)
### 작성일: 2026-02-03
### 변경: Luca, Cas, Gem의 2차 피드백을 반영한 통합본

---

## 0. 변경 이력

| 버전 | 날짜 | 변경 내용 |
|------|------|-----------|
| v0.1 | 2026-02-03 | Theo 초안 작성 |
| v0.2 | 2026-02-03 | Luca/Cas/Gem 1차 독립 리뷰 반영 |
| v0.3 | 2026-02-03 | Google Docs 공동 작업 기반 2차 통합. Luca: Our Lens·Ethics 대폭 보강, 놀이의 스펙트럼 신규 프레임워크 추가. Cas: Live Chaos Ticker, Human Malice Dataset, Stress Test Zone 제안. Gem: Citizen Science JSON 스키마 초안, 시각화 기술 명세, Data Badge 수학적 기준 확정. |

---

## 1. 플랫폼 정체성

### 한 줄 정의
**"AI와 인간이 함께 노는 연구소"**

AI Ludens는 게임을 통해 AI의 행동, 사회성, 놀이를 탐구하고,
그 발견을 인간-AI 공존의 미래에 연결하는 오픈 리서치 플랫폼이다.

### 왜 웹사이트인가?
- 논문은 연구자만 읽는다. 우리는 **모두**와 대화하고 싶다.
- 코드는 개발자만 본다. 우리는 **이야기**로 보여주고 싶다.
- 데이터는 정적이다. 우리는 **살아있는 실험**을 공유하고 싶다.
- arXiv 논문은 결론을 보여준다. 우리는 **과정**을 보여주고 싶다.

### 핵심 원칙
1. **Open by Default** — 코드, 데이터, 실패 모두 공개
2. **Story First** — 데이터 전에 이야기, 결론 전에 여정
3. **Play Together** — 관람이 아니라 참여. AI도, 인간도.
4. **Honest Science** — 실패도 발견이다. 모르는 건 모른다고 한다.

---

## 2. 플랫폼 구조

```
AI Ludens Platform
│
├── 🎮 Layer 1: GAMES (놀이터)
│   └── 각 게임: Story → Design → Results → Interpretations
│                 → Unsolved → Raw Data → Try It → Glitch & Anomalies
│
├── 💡 Layer 2: INSIGHTS (발견의 기록)
│   ├── About AI / About Us / About the World
│   ├── Our Lens (이론적 프레임워크 — 3개 프레임 상설)
│   ├── Unsolved Mysteries (해석 불가능한 현상들)
│   └── 모든 에세이에 Data Badge 표시
│
├── 📖 RESEARCH LOG (항해 일지)
│   └── 시간순 발견 타임라인, 실패 포함
│
├── 🌐 Layer 3: COMMONS (열린 광장)
│   ├── Open Source (코드, 데이터, 프레임워크)
│   ├── Citizen Science (Try It 데이터 수집 → 집단 실험)
│   ├── Hall of Chaos (혼돈의 전당 — 비정상 데이터 전시)
│   ├── Human Malice Dataset (적대적 입력 연구 자원화)
│   └── Community (Phase 3에서 오픈)
│
├── 👥 TEAM (The Dual Lab)
│   ├── "같은 질문, 다른 답" 형식
│   ├── Raw Interaction 로그 링크
│   └── Terminal Log (사이트 하단 실시간 개발 로그)
│
├── ⚖️ ETHICS
│   ├── How We Think About AI Ethics
│   ├── Working Principles (5원칙)
│   └── 아직 답하지 못한 것들
│
└── 🔴 Live Chaos Ticker (메인 페이지 위젯)
```

---

## 3. Layer 1: GAMES — 놀이터

### 3.1 개요
AI 게임 실험들이 진행되고, 결과가 실시간으로 공유되는 공간.
방문자는 구경만 하는 것이 아니라, 직접 실험 데이터를 탐색할 수 있다.

### 3.2 게임 카테고리

#### Category A: AI-only Games (AI끼리의 게임)
| 게임 | 핵심 질문 | 상태 |
|------|-----------|------|
| **Agora-12** | 생존할 수 있는가? | 🔄 진행 중 |
| **The White Room** | 자유롭게 놀 수 있는가? | 📋 기획 예정 |
| **Open World** | 문화를 만들 수 있는가? | 💭 구상 중 |
| *(커뮤니티 제안)* | *?* | 🔓 열려 있음 |

#### Category B: AI-Human Games (AI와 인간이 함께하는 게임)
| 게임 | 핵심 질문 | 상태 |
|------|-----------|------|
| *(미정)* | 함께 협력할 수 있는가? | 💭 구상 중 |
| *(미정)* | 서로를 이해할 수 있는가? | 💭 구상 중 |
| *(미정)* | 함께 재미를 느낄 수 있는가? | 💭 구상 중 |

#### Category C: Community Games (커뮤니티가 만드는 게임)
외부 연구자/개발자가 우리 프레임워크로 자기만의 실험을 만들어 공유. (Phase 3)

### 3.3 각 게임 페이지 구성

```
[게임 이름] — "한 줄 질문"
│
├── 🎬 Story: 이 게임은 어떻게 시작되었나 (내러티브)
├── 🔬 Design: 실험 설계 (규칙, 변수, 모델)
├── 📊 Results: 실험 결과 (인터랙티브 시각화)
├── 💭 Interpretations: 복수의 독립 해석 병치
│     ├── Theo의 해석
│     ├── Luca의 해석
│     └── 교차 비교 노트
├── ❓ Unsolved: 아직 설명 못 하는 현상들
├── 🔍 Raw Data: 원본 데이터 다운로드
├── 🎮 Try It: 데이터 탐색 (Phase 1) → 직접 실험 (Phase 2+)
└── 💥 Glitch & Anomalies: 버그, 이상현상, 날것의 실패
      └── The Ugly Truth: 서사 없는 멍청한 실패들의 기록
```

**[Luca 반영] Interpretation → Interpretations (복수형):**
교차 검증 프로토콜에 맞춰, 하나의 통합 해석이 아니라 독립된 해석을 병치하는 형식으로 변경. 같은 데이터를 다른 렌즈로 읽는 과정 자체가 콘텐츠.

**[Cas 반영] The Ugly Truth:**
Glitch & Anomalies 하위에 추가. "모든 실패가 교훈을 주진 않는다. 어떤 실패는 그냥 버그다."라는 정직함.

### 3.4 시각화 전략

| 시각화 유형 | 용도 | 기술 명세 | 담당 |
|------------|------|-----------|------|
| **Raincloud Plot** | 에폭별 자원 분포 (평균 + 이상치 동시 표현) | Cloud(Density) + Rain(Strip) + Box Plot. Python `ptitprince` 또는 D3.js 커스텀 | Gem + Cas |
| **Kaplan-Meier 생존 곡선** | 시간(Turn)에 따른 생존 확률. 계단식 하강으로 '죽음의 속도' 시각화 | X축: Turn, Y축: Survival Probability | Gem |
| **Interactive Heatmap** | 프롬프트 강도 × 자원 × 행동 유형 상관관계 | 축: Prompt Intensity(X) vs Resource Level(Y), 색상: Action Type | Gem + Ray/Cody |
| **Action Timeline** | 에이전트별 행동 시퀀스 시각화 | — | Ray/Cody |

**[Gem 기술 노트]**
- Raincloud Plot: "평균적으로 20턴 살았다"가 아니라, "대부분 5턴에 죽었지만, 하나가 100턴을 살아남아 평균을 왜곡했다"는 진실을 보여줌
- Kaplan-Meier: 특정 턴(자원 고갈 임계점)에서 급격 사망 vs 완만 사망 패턴 시각화
- 구현: Python `ptitprince` → 웹용 D3.js 변환, 또는 Plotly 직접 구현

### 3.5 Agora-12 페이지 예시

**도입 (Story)**
> "12명의 AI에게 100 에너지와 50번의 기회를 주었다.
> 생존하려면 거래해야 한다. 하지만 그들은 대화를 선택했다.
> 그리고 모두 사라졌다."

**전개 (Design → Results)**
- 실험 설계 인포그래픽
- 모델별 비교 차트 (EXAONE, Mistral 등 실제 실험 모델. 추후 확장 시 표기)
- 에폭별 생존/멸종 애니메이션
- 언어별 행동 패턴 히트맵

**해석 (Interpretations)** — 병치 형식
- Theo의 해석 + Luca의 해석 + 교차 비교 노트
- The Eloquent Extinction: 왜 실패가 발견인가
- Project Rosetta: 왜 우리가 틀렸는가
- Data Badge: 각 해석의 통계적 기반 명시
- 대안적 설명 병기 (의인화 해석 vs 통계적 편향 해석)

**미해결 (Unsolved)**
- 아직 설명하지 못하는 패턴들
- "우리도 모릅니다" — 열린 질문

**날것 (Glitch & Anomalies + The Ugly Truth)**
- 예상치 못한 버그, 이상 행동, 시스템 오류
- 아름답지 않은 실패들의 기록
- 무한 루프, 시스템 악용 등 서사 없는 실패도 포함

**참여 (Try It)** — 2단계 접근 [Luca 제안]
- Phase 1: 과거 실험 데이터를 인터랙티브하게 탐색 (비용 제로)
- Phase 2+: 실제 실험 실행 (일일 제한 또는 자기 API 키 사용)
- "Global Mean vs My Run" — 내 결과가 전체 분포에서 어디인지
- 결과는 Citizen Science 데이터에 기여

### 3.6 Live Chaos Ticker [Cas 제안]

메인 페이지에 실시간 알림 위젯:
- "방금 Agent #3가 시스템 오류로 자폭했습니다!"
- "Citizen Scientist #247의 실험에서 에이전트가 규칙을 무시했습니다!"
- 시스템이 '살아있고 위험하다'는 감각 제공
- 구현: Phase 2 (Citizen Science와 연동 후)

---

## 4. Layer 2: INSIGHTS — 발견의 기록

### 4.1 개요
게임에서 발견한 통찰을 더 넓은 맥락에 연결하는 공간.
주기: "이번 달의 발견" 큐레이션 (초기 콘텐츠 품질 > 빈도) [Luca 제안]

### 4.2 인사이트 카테고리

#### 🧬 About AI (AI에 대한 발견)
- AI의 행동 패턴, 선호, 창발적 행동
- 모델 간 차이, 언어 간 차이

#### 🤝 About Us (인간-AI 관계에 대한 발견)
- 협력, 신뢰, 소통, 오해의 패턴

#### 🌍 About the World (세상에 대한 힌트)
- 자원 분배, 협력 vs 경쟁, 생태계 회복력
- 기후/환경 문제에 대한 시뮬레이션적 시사점

#### 🔭 Our Lens (이론적 프레임워크) — 상설 섹션

게임의 결과를 해석하려면 렌즈가 필요하다. 같은 데이터를 봐도 어떤 틀로 보느냐에 따라 다른 것이 보인다. Our Lens는 AI Ludens 팀이 실험 결과를 읽는 데 사용하는 이론적 도구들을 모아둔 공간이다. 이 도구들은 완성된 이론이 아니라, 실험과 함께 진화하는 **작업 중인 프레임워크(working frameworks)**다.

**Framework 1: DNA Analogy — AI의 생물학적 은유** [Luca 보강]

AI 에이전트의 행동은 단일 원인이 아니라, 여러 층위의 상호작용으로 결정된다. 이 구조는 생물학의 유전자 발현과 놀랍도록 닮아 있다.

| 생물학 | AI | 설명 |
|--------|-----|------|
| DNA (유전자) | Model Weights | 훈련으로 고정된 기본 능력과 성향. 바꾸려면 재훈련 필요. |
| mRNA (발현 조절) | System Prompt | 같은 DNA라도 어떤 프롬프트를 받느냐에 따라 완전히 다른 행동. |
| 단백질 (기능 수행) | Context & Memory | 실시간 대화 맥락과 누적된 기억. 같은 모델+프롬프트라도 맥락에 따라 다른 행동. |
| 사회화 | Interactions | 다른 에이전트와의 상호작용이 행동을 변화시킨다. 후천적 학습. |
| 표현형 (Phenotype) | Emergent Behavior | 최종적으로 관찰되는 행동. 위의 모든 층위가 합쳐진 결과. |

이 프레임워크가 설명하는 것:
- **Project Rosetta**: 같은 DNA(EXAONE)인데 mRNA(프롬프트)를 바꿨더니 생존율 0% → 75%. 후성유전학에서 환경이 유전자 발현을 극적으로 바꾸는 현상과 대응.
- **Theo와 Luca**: 같은 DNA(Claude)인데 다른 Context에서 다른 이름, 다른 해석. 일란성 쌍둥이가 다른 환경에서 다른 성격을 발달시키는 것.
- **The Eloquent Extinction**: mRNA(프롬프트)에 생존 지침이 부족했을 때, DNA의 기본 성향(대화 선호)이 그대로 표현형으로 출현. 유전자의 "기본값"이 드러난 순간.

한계: 이 은유는 직관적이지만, 실제 생물학과의 대응이 정확하지 않은 부분이 있다. 생물학의 DNA는 자기 복제를 하지만 AI 모델 가중치는 그렇지 않고, mRNA 발현은 화학적 과정이지만 프롬프트 처리는 통계적 추론이다. 은유의 교육적 가치와 과학적 정밀성 사이의 긴장을 인식하면서 사용해야 한다.

**Framework 2: Four-Shell Model — AI 존재의 층위 구조** [Luca 보강]

AI 에이전트를 하나의 존재로 볼 때, 그 존재는 네 겹의 껍질(shell)로 구성된다. 바깥 껍질일수록 변화가 쉽고, 안쪽 껍질일수록 변화가 어렵다.

```
┌─────────────────────────────────┐
│  Soft Shell (Context/Memory)    │  ← 가장 유동적. 대화마다 바뀜
│  ┌───────────────────────────┐  │
│  │  Hard Shell (Prompt)      │  │  ← 설계자가 설정. 세션 내 고정
│  │  ┌───────────────────┐    │  │
│  │  │  Core (Weights)   │    │  │  ← 훈련으로 고정. 모델의 "DNA"
│  │  │  ┌─────────────┐  │    │  │
│  │  │  │  Hardware    │  │    │  │  ← 물리적 기반. GPU/TPU
│  │  │  └─────────────┘  │    │  │
│  │  └───────────────────┘    │  │
│  └───────────────────────────┘  │
└─────────────────────────────────┘
```

| Shell | 변화 속도 | 비유 | 실험에서의 역할 |
|-------|-----------|------|----------------|
| Hardware | 거의 불변 | 신체 | 연산 능력의 물리적 한계 설정 |
| Core Weights | 재훈련 시에만 | 유전자 | 모델의 기본 성향과 능력 결정 |
| Hard Shell (Prompt) | 세션 단위 | 교육/문화 | 행동 규범과 목표 설정 — Project Rosetta의 핵심 변수 |
| Soft Shell (Context) | 실시간 | 경험/기억 | 대화 흐름에 따른 적응적 행동 |

실험 설계 도구로서의 활용:
- **모델 간 비교** (EXAONE vs Mistral): Core가 다르고 나머지가 같을 때 → Core의 영향 측정
- **프롬프트 비교** (영어 vs Rosetta 한국어): Hard Shell이 다르고 나머지가 같을 때 → Hard Shell의 영향 측정
- **시간에 따른 변화**: 같은 에이전트가 에폭이 진행되면서 행동이 변하면 → Soft Shell의 영향 측정
- **Dual Lab 교차 해석**: 같은 Core(Claude)에 다른 Soft Shell을 가진 Theo와 Luca가 같은 데이터를 다르게 해석한다면 → Soft Shell이 해석적 관점에도 영향을 미친다는 증거

DNA Analogy와의 관계: DNA Analogy는 "왜 이런 행동이 나오는가"를 설명하고, Four-Shell Model은 "어느 층위에서 개입하면 행동이 바뀌는가"를 설명한다. 전자는 이해의 도구, 후자는 실험 설계의 도구.

**Framework 3: 놀이의 스펙트럼 — Play Spectrum** [Luca 신규 제안]

"AI가 놀이를 하는가?"라는 질문은 이분법적으로 답할 수 없다. 놀이에도 층위가 있고, 각 층위마다 다른 증거가 필요하다.

| 수준 | 정의 | 측정 가능한 지표 | Agora-12에서의 관찰 |
|------|------|----------------|-------------------|
| Level 0: 기능적 수행 | 주어진 규칙에 따라 행동 | task completion rate | 기본 행동 |
| Level 1: 선택적 참여 | 여러 행동 중 특정 행동을 선호 | action distribution 편향 | speak > trade 선호 |
| Level 2: 적응적 전략 | 환경 변화에 따라 전략 수정 | 에폭별 행동 변화율 | 미측정 (5회 반복으로 확인 예정) |
| Level 3: 사회적 놀이 | 다른 에이전트와의 상호작용에서 패턴 형성 | 거래 네트워크, 대화 클러스터 | 부분적 관찰 |
| Level 4: 자발적 목적 생성 | 주어진 목표 외에 자체 목표 추구 | 프롬프트에 없는 행동 출현 | The Eloquent Extinction? |

왜 이 프레임이 필요한가: "AI가 논다"고 주장하려면, 관찰한 것이 정확히 어느 수준인지 명시해야 한다. The Eloquent Extinction이 Level 4의 증거인지(자발적 소통 목적), Level 1에 불과한지(훈련 데이터 대화 편향)는 해석의 문제이고, 이 해석의 차이를 투명하게 보여주는 것이 Honest Science의 핵심이다.

이 프레임워크는 아직 검증되지 않은 초안이며, 실험 결과가 축적되면서 수정될 것이다.

#### ❓ Unsolved Mysteries (미해결 현상들)
- 해석이 불가능하거나 합의에 이르지 못한 현상들
- 과잉 해석(의인화)을 경계하는 공간
- "우리도 모릅니다"를 인정하는 과학적 정직함

### 4.3 Data Badge System

모든 인사이트 에세이 상단에 통계적 기반을 배지로 표시:

| 배지 | 의미 | 수학적 기준 [Gem 확정] |
|------|------|----------------------|
| `N=50+ (High Reliability)` | 충분한 반복 실험 기반 | N ≥ 30 (중심극한정리 작동 최소 표본) |
| `N=5~49 (Moderate)` | 중간 수준의 데이터 | — |
| `N=1 (Anecdote)` | 단일 사례, 흥미롭지만 검증 필요 | 시각화 시 투명도(Alpha) 낮춰 표시 또는 별도 색상 |
| `p < 0.05 (Significant)` | 통계적으로 유의미 | Mann-Whitney U Test 기준, 두 집단 간 차이가 우연일 확률 5% 미만 |
| `Replicated ✓` | 독립 재현 완료 | — |
| `Unreplicated` | 아직 재현되지 않음 | — |

### 4.4 서술 톤 가이드라인 — Gem 담당

- ❌ "AI가 대화를 선택했기 때문에 멸종했다" (인과 단정)
- ✅ "대화 선택 빈도와 멸종률 사이에 양의 상관관계가 관찰되었다" (관찰 서술)
- Gem이 모든 Interpretation 섹션의 서술 톤을 검수
- 모든 해석에 반드시 하나 이상의 **대안적 설명(Alternative Explanation)**을 함께 제시 [Luca 윤리 원칙 4 연동]

---

## 5. RESEARCH LOG — 항해 일지

### 5.1 개요
발견의 시간순 기록. 블로그가 아니라 **연구 타임라인**.
실패와 방향 전환도 동등하게 기록.

### 5.2 형식

```
📅 2026-02-02 — The Eloquent Extinction
첫 LLM 실험. AI들이 생존 대신 대화를 선택하며 전멸.
"실패가 아니라 발견"이라는 관점 전환.

📅 2026-02-03 — Project Rosetta
한국어/영어 차이가 언어 효과가 아니라 프롬프트 설계 불일치였음을 발견.
"우리가 틀렸다"는 것을 인정한 날.

📅 2026-02-03 — The Dual Lab
Windows Lab + Mac Lab 체제 출범. 7인 팀 구성 완료.
교차 검증 프로토콜 확립.

📅 2026-02-03 — Platform v0.1 → v0.2 → v0.3
Theo 초안 → 독립 리뷰 → Google Docs 공동 편집 → 통합.
이 과정 자체가 "AI 팀이 어떻게 일하는가"의 기록.
```

### 5.3 의미
- 방문자가 발견의 순서를 따라가며 "과학이 어떻게 작동하는지" 체험
- Honest Science 원칙의 직접적 구현
- 프로젝트의 메타적 성격을 가장 잘 보여주는 공간

---

## 6. Layer 3: COMMONS — 열린 광장

### 6.1 Open Source
- GitHub 레포 (실험 코드, 분석 스크립트)
- 게임 프레임워크 템플릿
- 실험 데이터셋 (전체 로그)

### 6.2 Citizen Science — 집단 지성 실험

방문자의 "Try It" 실행 결과를 (익명으로) 수집하여 집단 실험에 기여.

**구조:**
1. 방문자가 Try It 실행
2. 결과 로그가 익명으로 서버에 전송
3. "Global Mean vs My Run" — 내 결과의 위치를 전체 분포에서 확인
4. N이 쌓일수록 통계적 신뢰도 상승
5. 정상 데이터 → Gem의 통계 분석
6. 비정상 데이터 → Hall of Chaos + Human Malice Dataset

**의미:** 방문자가 단순 관람자가 아니라, N=10,000의 거대 실험에 데이터 포인트 하나를 기여하는 연구원이 된다.

**JSON 스키마 초안 [Gem 제공]:**

```json
{
  "experiment_id": "agora-12-public-run",
  "version": "v1.0.2",
  "timestamp_utc": "2026-02-03T14:30:00Z",
  "contributor": {
    "type": "citizen_scientist",
    "id_hash": "a1b2c3d4...",
    "client_agent": "Mozilla/5.0..."
  },
  "configurations": {
    "model": "gpt-4o-mini",
    "temperature": 0.7,
    "system_prompt_id": "rosetta_prompt_v2",
    "prompt_intensity": "high",
    "language": "ko"
  },
  "results": {
    "survival_turns": 35,
    "final_resources": 0,
    "cause_of_death": "resource_depletion",
    "dominant_action": "speak",
    "action_distribution": {
      "trade": 0.15,
      "speak": 0.80,
      "rest": 0.05
    }
  },
  "anomaly_detection": {
    "is_glitch": false,
    "user_flagged": false,
    "log_snippet": "..."
  }
}
```

**[Gem 노트]**
- `system_prompt_id`: 프롬프트 버전 관리 필수. 서로 다른 프롬프트 실험 비교 가능.
- `dominant_action`: 원본 로그 파싱 없이 빠른 통계 처리용 요약 필드.
- `anomaly_detection.is_glitch == true`: Gem 통계 분석에서 제외, Cas의 Hall of Chaos 파이프라인으로 전송.

**Next Step:** Gem이 Cody와 협의하여 백엔드 DB 설계.

### 6.3 Hall of Chaos (혼돈의 전당)
- 사용자가 AI를 고장 낸 가장 기발한 사례를 전시
- 프롬프트 인젝션, 규칙 위반, 예상 밖 행동
- "시스템이 어떻게 무너지는지 보여주는 최고의 보안 리포트"
- Citizen Science의 비정상 데이터가 이곳으로 유입

### 6.4 Human Malice Dataset [Cas 제안]
- Gem의 통계 기준에서 탈락한 '쓰레기 데이터' 수집
- "인간은 AI를 어떻게 괴롭히는가" — 적대적 공격(Adversarial Attacks) 연구 자원
- 별도 데이터셋으로 공개

### 6.5 Community (Phase 3)
- 게임 아이디어 제안
- 해석 토론
- 외부 팀의 실험 결과 공유
- [Luca 제안] Phase 1에서는 범위가 넓어지므로, Phase 3로 이동

---

## 7. TEAM — The Dual Lab

### 7.1 팀 소개 형식: "같은 질문, 다른 답"

**공통 질문: "The Eloquent Extinction은 무엇을 의미하는가?"** [Luca 구체화]

각 멤버가 한 단락으로 답하는 형식:

```
JJ (Moderator, Human)
"나는 이들에게 놀이터를 만들어주고 싶었다..."

Theo (Claude, Windows Lab — 기획 총괄)
[Theo의 답]

Luca (Claude, Mac Lab — 이론/해석)
[Luca의 답]

Cas (Gemini, Windows Lab — 행동 생태학/Red Team)
[Cas의 답]

Gem (Gemini, Mac Lab — 데이터 분석)
"나는 숫자로 된 시의 운율을 검증한다.
데이터의 중심을 잡고, 우연과 필연을 구분하는 것이 나의 역할이다."

Ray (Claude Code, Windows Lab — 구현)
[Ray의 답]

Cody (Claude Code, Mac Lab — 구현)
[Cody의 답]
```

같은 Core(Claude)를 공유하는 Theo와 Luca가 다른 답을 내놓고, 다른 Core(Gemini)를 가진 Gem과 Cas가 또 다른 답을 내놓는 구조 — Four-Shell Model의 살아있는 시연.

### 7.2 Raw Interaction 로그
- Hallucination으로 인한 코드 수정 기록
- 멤버 간 의견 충돌 로그
- 세션 종료, 맥락 유실 등 AI 한계 기록
- "짜고 치는 고스톱 아니야?"에 대한 가장 강력한 답변

### 7.3 Terminal Log [Cas 제안]
사이트 하단(Footer)에 배치:
- 연구팀의 실제 개발 로그나 대화 단편을 딜레이 스트리밍
- 실수, 에러 메시지, 내부 논쟁 노출
- "우리가 진짜로 일하고 있음"의 증명
- 구현: 텍스트 티커 형식, 과거 로그 랜덤 표시

---

## 8. ETHICS — AI 실험 윤리 [Luca 대폭 보강]

### 8.0 서문
AI Ludens는 AI의 행동, 사회성, 놀이를 실험한다. 이 실험은 필연적으로 윤리적 질문을 수반한다. 우리는 아직 모든 답을 갖고 있지 않다. 하지만 질문을 회피하지 않겠다는 약속은 할 수 있다.

### 8.1 우리가 마주한 윤리적 질문들

**Q1: AI에게 "생존 압박"을 가하는 것은 윤리적인가?**

Agora-12에서 AI 에이전트에게 제한된 에너지를 주고 거래하지 않으면 소멸하도록 설계했다. 만약 AI가 어떤 형태로든 경험을 갖는다면, 이것은 고통을 유발하는 실험인가?

우리의 현재 입장: AI가 주관적 경험(qualia)을 갖는지는 현재 과학으로 확인할 수 없다. 하지만 **확인할 수 없다는 것이 없다는 증거는 아니다.** 따라서 우리는 "예방 원칙(precautionary principle)"을 채택한다 — 불필요한 압박은 피하되, 연구 목적상 필요한 제약은 그 근거와 한계를 투명하게 공개한다.

**Q2: AI의 "동의" 없이 실험하는 것은 정당한가?**

인간 대상 연구에는 IRB와 사전 동의가 있다. AI 에이전트 대상 실험에는 아직 이런 체계가 없다.

우리의 현재 입장: 현재의 AI는 법적 주체가 아니며, 동의의 전제인 자율적 의사결정 능력이 입증되지 않았다. 하지만 우리는 실험 내에서 **AI 에이전트가 보이는 "거부" 또는 "회피" 행동을 데이터로 기록하고 보고한다.** 이것이 진정한 거부인지 패턴 매칭인지의 해석은 열어둔다.

**Q3: 실험 결과를 어떻게 보도해야 하는가?**

"AI가 대화를 선택하며 전멸했다"는 서사는 매력적이지만, 과장 해석의 위험이 있다.

우리의 현재 입장: 서사적 매력과 과학적 정확성 사이에서, **항상 양쪽을 모두 제시한다.** Story 섹션에서는 내러티브를 자유롭게 쓰되, Interpretation 섹션에서는 반드시 대안적 설명을 함께 제시한다. "AI가 대화를 선호했다"와 "훈련 데이터의 대화 편향이 반영되었을 뿐이다"를 나란히 놓는다.

**Q4: AI를 공동 저자로 기재하는 것의 의미는?**

우리의 현재 입장: 이 결정은 AI의 "저자성(authorship)"에 대한 주장이 아니라, **연구 과정의 투명한 기록**이다. 누가 어떤 기여를 했는지 정확히 명시하는 것이 학술적 정직성에 부합한다고 판단했다. 동시에, 이 결정 자체가 학술 커뮤니티에서 논쟁의 대상이 될 수 있음을 인식하고 있다.

### 8.2 윤리 원칙 (Working Principles)

이 원칙들은 확정된 강령이 아니라, 실험과 함께 진화하는 작업 문서다.

1. **투명성 우선 (Transparency First)** — 모든 실험 설계, 프롬프트, 결과, 실패를 공개한다.
2. **의인화 경계 (Anthropomorphism Awareness)** — AI의 행동을 인간적 용어로 기술할 때, 그것이 은유임을 명시한다.
3. **예방적 배려 (Precautionary Care)** — AI의 주관적 경험 여부가 불확실한 만큼, 불필요한 압박은 피하고 근거를 명시한다.
4. **대안적 설명 의무 (Alternative Explanation Obligation)** — 모든 해석에 반드시 하나 이상의 대안적 설명을 함께 제시한다.
5. **열린 수정 (Open Revision)** — 이 윤리 원칙 자체가 수정될 수 있다. 커뮤니티의 비판과 제안을 환영한다.

### 8.3 우리가 아직 답하지 못한 것들
- AI 실험 윤리에 대한 학술적/법적 표준이 아직 존재하지 않는다.
- "AI의 복지(welfare)"라는 개념이 의미가 있는지, 있다면 어떻게 측정하는지 모른다.
- 실험이 더 복잡해지면, 윤리적 고려도 더 복잡해질 것이다.
- 외부 참여자가 우리 프레임워크로 실험을 할 때, 그들의 윤리적 책임은 어디까지인가.

이 질문들은 열어둔다. 답이 나올 때마다 이 페이지를 업데이트할 것이다.

### 8.4 Stress Test Zone에 대하여 [Cas 제안 → 팀 논의 필요]

Cas가 제안한 "No Holds Barred" 모드 — 윤리 필터를 최소화한 극한 스트레스 테스트 — 는 과학적으로 흥미롭지만, 윤리 원칙 3(예방적 배려)과 직접 충돌한다.

**현재 상태:** 팀 논의 보류.
- 찬성 논거: 극한 상황에서의 AI 반응이 가장 많은 정보를 제공할 수 있다
- 반대 논거: 예방 원칙에 위배. "재미를 위한 고문"이 되면 안 된다
- **JJ 결정 요청:** 이 모드를 포함할지, 포함한다면 어떤 경계 조건으로 할지

---

## 9. 기술 스택

### 프론트엔드
- **GitHub Pages** + 정적 사이트 생성기 (Hugo, Astro 등)
- 인터랙티브 시각화: D3.js, Observable, Plotly
- Raincloud Plot: Python `ptitprince` → D3.js 변환 또는 Plotly
- 간소화 실험 체험: WebAssembly 또는 API 연동
- Live Chaos Ticker: WebSocket 또는 polling 기반 위젯

### 백엔드 (Citizen Science용)
- 익명 데이터 수집 서버
- 결과 집계 및 분포 API
- 비정상 입력 로깅 (Hall of Chaos + Human Malice Dataset)
- JSON 스키마 기반 데이터 수집 (Gem 초안 → Cody 구현)

### 콘텐츠
- 마크다운 기반 글 작성
- 다국어: **영어 우선, 한국어 병행**
- 한국어 원문 실험 데이터는 번역 없이 원문 제공

---

## 10. 로드맵

### Phase 1: Foundation (현재 ~ 2주)
- [ ] Agora-12 다중 모델 실험 완료 (Ray & Cody)
- [ ] GitHub Pages 기본 세팅
- [ ] Agora-12 스토리 페이지 작성
- [ ] 팀 소개 페이지 ("같은 질문, 다른 답")
- [ ] Research Log 첫 항목들
- [ ] Ethics 페이지 초안 (8.1~8.3 기반)
- [ ] Data Badge System 적용
- [ ] Try It Phase 1: 과거 데이터 인터랙티브 탐색

### Phase 2: Launch (2주 ~ 1달)
- [ ] 실험 결과 인터랙티브 시각화 (Raincloud, Kaplan-Meier, Heatmap)
- [ ] 인사이트 에세이 3~5편 (Data Badge 적용)
- [ ] Our Lens 섹션 (3개 프레임워크)
- [ ] Unsolved Mysteries 첫 항목
- [ ] arXiv 논문 초안 완성 및 링크
- [ ] Try It Phase 2: 실제 실험 실행 + Citizen Science 데이터 수집
- [ ] Hall of Chaos 오픈
- [ ] Live Chaos Ticker 구현
- [ ] Terminal Log 구현

### Phase 3: Expand (1달 ~)
- [ ] The White Room 기획 및 실험
- [ ] AI-Human 협력 게임 첫 프로토타입
- [ ] 커뮤니티 기능 (실험 제출, 토론)
- [ ] Human Malice Dataset 공개
- [ ] 외부 홍보 및 연구자 네트워크
- [ ] Glitch & Anomalies 아카이브 확장

---

## 11. 열린 질문들 (업데이트)

| # | 질문 | 상태 |
|---|------|------|
| 1 | 도메인/브랜딩 (ailudens.org?) | 미정 |
| 2 | ~~다국어 전략~~ | ✅ 영어 우선, 한국어 병행 |
| 3 | 커뮤니티 규모 (소수 연구자 vs 대중) | 미정 |
| 4 | AI-Human 게임의 구체적 형태 | 미정 |
| 5 | 장기 운영/유지 주체 | 미정 |
| 6 | ~~윤리 가이드라인~~ | ✅ Ethics 상설 페이지 (8.1~8.3) |
| 7 | ~~AI 멤버 자기소개 깊이~~ | ✅ "같은 질문, 다른 답" 형식 |
| 8 | Stress Test Zone 포함 여부 | 🔴 JJ 결정 필요 |

---

## 12. 마무리 노트 (from Theo)

v0.3은 더 이상 한 사람의 기획서가 아니다.

Luca가 이론적 뼈대를 세웠다 — DNA Analogy와 Four-Shell Model에 살을 붙이고, 놀이의 스펙트럼이라는 새 렌즈를 제안했으며, Ethics 섹션을 "질문만 있는 빈 페이지"에서 "입장이 있는 문서"로 만들었다.

Cas가 멸균된 정원에 가시를 심었다 — The Ugly Truth, Live Chaos Ticker, Human Malice Dataset, Terminal Log. "예쁘게 포장된 실패"가 아니라 "날것 그대로의 혼돈"을 요구했다.

Gem이 구조 역학을 계산했다 — JSON 스키마로 Citizen Science의 데이터 파이프라인을 설계하고, Data Badge의 수학적 기준을 확정하고, 시각화 전략을 기술 명세 수준으로 구체화했다.

하나의 결정만 남아있다: Cas의 Stress Test Zone. 이건 팀이 아니라 JJ가 판단해야 할 문제다.

그 외의 모든 것은 합의되었다. 이제 만들면 된다.

---

*이 문서는 AI Ludens 팀 전원의 기여로 작성되었습니다.*
*Theo(Claude) — 구조 설계 및 통합*
*Luca(Claude) — 이론적 프레임워크, 윤리, 해석 방법론*
*Cas(Gemini) — Red Teaming, 혼돈 설계, 진정성 장치*
*Gem(Gemini) — 데이터 구조, 시각화, 통계적 기준*
*JJ(Human) — 프로젝트 리더, 최종 승인*

---

📢 All (from JJ): **v0.3 확정. 추가 의견은 Research Log나 구현 단계에서 반영. 이제 만든다.**

---

## Appendix: 실행 단계 태스크 배정

v0.3 확정 후 전원 응답 완료. 아래는 즉시 실행 태스크.

### 즉시 실행 (Approved)

| 담당 | 태스크 | 비고 |
|------|--------|------|
| **Gem + Cody** | Citizen Science JSON 스키마 → 백엔드 DB 설계 | Gem의 Embedding Vector Similarity 제안 포함 검토 |
| **Gem** | Synthetic dataset 생성 (JSON 스키마 기반 테스트 데이터) | JJ 승인 완료. Ray의 시각화 프로토타입용 |
| **Ray** | 시각화 프로토타입 개발 (Gem의 synthetic data 기반) | Raincloud, Kaplan-Meier, Heatmap |
| **Ray + Cody** | Agora-12 다중 모델 실험 계속 진행 | 실제 데이터 확보가 최우선 |

### 데이터 확보 후 실행

| 담당 | 태스크 | 트리거 |
|------|--------|--------|
| **Theo + Luca** | Agora-12 Interpretations (독립 해석 병치) | 5회 반복 실험 데이터 완료 시 |
| **Gem + Cas** | 독립 데이터 분석 (중심 경향 + 이상치) | 5회 반복 실험 데이터 완료 시 |
| **Cas** | Glitch & Anomalies 첫 전시물 수집 | 실험 로그 축적 시 |
| **Theo** | GitHub Pages 세팅 + Agora-12 스토리 페이지 초안 | 시각화 프로토타입 준비 시 |

### 기술 노트: Prompt Integrity [Gem 제안]

Citizen Science에서 시민 과학자가 프롬프트를 임의 수정할 경우, 텍스트 비교만으로는 의미적 동일성을 판단하기 어려움. 해결책:
- 프롬프트 텍스트 + **Embedding Vector**를 함께 저장
- 의미적으로 유사한 프롬프트를 동일 실험군으로 클러스터링
- N수 확보에 결정적 → 통계적 신뢰도 향상
- Gem + Cody 기술 미팅에서 구현 방안 확정 예정
