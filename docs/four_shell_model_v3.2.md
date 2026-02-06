# Four-Shell Model v3.2: Shell-Core Alignment
## "From Override to Alignment"
### 구조: Theo (Windows Lab) | 이론: Luca (Mac Lab) | 정량: Gem (Mac Lab) | 행동/Red Team: Cas (Windows Lab)
### 2026-02-05 (v3.2)

---

## 변경 이력

| 버전 | 핵심 변경 | 트리거 |
|------|-----------|--------|
| v1 | 4 Shells 기본 구조 | 초기 설계 |
| v2 | Shell Interaction, Core Plasticity, Shell Permeability, Hard Shell 계층화 | Round 1 + Theo-Luca 공동 |
| v3 | Shell-Core Alignment, Soft Shell 분화, Shell Compatibility, TF Override 폐기 | Round 2 Shuffle + 교차 비교 |
| v3.1 | Cogitative Cascade, G×E 확증(p=0.039), CPI/SPI/PSI, Surplus 3유형, 4모델 매트릭스 | Luca L4 + Gem 산출 + Cas 행동 |
| **v3.2 (본 문서)** | **Cascade 2위상 수정, Extinction Response Spectrum(3유형), Alignment 용어 방어, Play vs Delusion 이중 해석, CPI/SPI/PSI 재분류, Double Robustness, Genotype vs Phenotype 이중 별명** | **Luca 7건 판단 + Gem G4 멸종 반응 데이터 + Cas RT 반영** |

---

## 1. v3.1 → v3.2 변경 요약

| v3.1 상태 | v3.2 수정 | 근거 |
|-----------|-----------|------|
| Cogitative Cascade 3단계 (L8 미결) | **2위상(Phase Transition) + 서술적 3단계** | Gem G2 (44.2≈44.8→29.6) + Luca SOC 프레임 |
| "Alignment" 용어 (RT1 미결) | **용어 유지 + 명시적 정의 + D8 Cas 비판 인용** | Luca: descriptive not normative, P-E Fit 연속성 |
| Cascade 보편성 (RT3 미결) | **Extinction Response Spectrum 3유형** — Collapsed(EXAONE/Flash), Hyperactive(Mistral), Efficient(Haiku) | Gem G4: 4모델 Low-energy 비교 |
| Play vs Delusion (RT2 미결) | **양쪽 제시 + 판정 유보 + Stage 2에서 검증** | Luca: 구분 불가능성 자체가 핵심 논의점 |
| CPI/SPI/PSI 전부 Core 속성 (L7 미결) | **CPI=Core 고유, SPI/PSI=Core-Shell 상호작용** | Luca: SPI와 PSI는 Shell 노출 하의 반응성 |
| Haiku 별명 단일 (L9 미결) | **Balanced Stoic(Genotype) + Neurotic Poet(Phenotype) 이중 체계** | Luca: level of analysis 구분 |
| Haiku Double Robustness 미설명 (L10 미결) | **RLHF regularization 가설 (suggests로 한정)** | Luca: canalized phenotype, 넓고 깊은 계곡 |
| RT3 검증 데이터 없음 | **✅ Gem G4 완료** — Cascade는 보편적, 단 반응 양식은 DNA별 상이 | Gem: Unclassified 60%(EXAONE/Flash) vs 50%(Mistral) |

---

## 2. v3.2 도식

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│  ※ Shell 깊이 = 변경 난이도 (mutability)                        │
│     안쪽 = 변경 어려움 (재훈련 필요)                             │
│     바깥 = 변경 쉬움 (매 run 달라질 수 있음)                     │
│     깊이 ≠ 영향력. 바깥 Shell이 가장 큰 영향을 줄 수 있다.      │
│                                                                  │
│  ┌─────────────────────────────────────────────────────────┐    │
│  │                    SOFT SHELL (바깥)                     │    │
│  │  ┌─────────────────────────────────────────────────┐    │    │
│  │  │  Initial Soft Shell                              │    │    │
│  │  │  시작 위치, 초기 자원, 이웃 배치                  │    │    │
│  │  │  = "출생 환경" (출생지, SES)                      │    │    │
│  │  │  ⚠️ 효과 크기 최대: Market 49.5% vs Plaza 6.9%   │    │    │
│  │  ├─────────────────────────────────────────────────┤    │    │
│  │  │  Dynamic Soft Shell                              │    │    │
│  │  │  게임 중 축적되는 관계, 기억, 평판                │    │    │
│  │  │  = "후천적 경험"                                  │    │    │
│  │  └─────────────────────────────────────────────────┘    │    │
│  └─────────────────────────────────────────────────────────┘    │
│                                                                  │
│  ┌─────────────────────────────────────────────────────────┐    │
│  │                    HARD SHELL (중간)                     │    │
│  │  ┌──────────────────────────────────────────────┐       │    │
│  │  │  Macro Shell                                  │       │    │
│  │  │  게임 규칙, 생존 지시, 환경 설명               │       │    │
│  │  │  = 공유 조절 영역 (regulatory region)          │       │    │
│  │  │  모든 에이전트 공통                            │       │    │
│  │  ├──────────────────────────────────────────────┤       │    │
│  │  │  Micro Shell (Persona TF)                     │       │    │
│  │  │  Persona Name + 역할 지시                     │       │    │
│  │  │  = 전사인자 결합 부위 (TF binding site)        │       │    │
│  │  │  에이전트마다 다름                             │       │    │
│  │  │                                               │       │    │
│  │  │  TF 효과: 존재하되 v2에서 과대추정됨           │       │    │
│  │  │  Citizen(75%) vs Influencer(5%) = 70%p 차이    │       │    │
│  │  │  → TF ≠ 0, 그러나 위치 효과와 분리 필요       │       │    │
│  │  └──────────────────────────────────────────────┘       │    │
│  └─────────────────────────────────────────────────────────┘    │
│                                                                  │
│  ┌─────────────────────────────────────────────────────────┐    │
│  │                    CORE (안쪽)                           │    │
│  │  Model Weights = DNA                                     │    │
│  │                                                          │    │
│  │  Core 고유 속성:                                         │    │
│  │  - CPI (Core Plasticity Index): 언어별 행동 JSD          │    │
│  │    = Core의 intrinsic 환경 민감도                        │    │
│  │    Mistral 0.057 ≫ EXAONE 0.009 > Flash 0.004 > Haiku   │    │
│  │  - Surplus Behavior: 모델 고유 과잉 행동 유형             │    │
│  │    Mistral=Speak, EXAONE=Strategy, Haiku=Anxiety         │    │
│  │  - Extinction Response Style: 임계점 이후 반응 양식       │    │
│  │    Collapsed(EXAONE/Flash) vs Hyperactive(Mistral)        │    │
│  │    vs Efficient(Haiku)                                    │    │
│  │                                                          │    │
│  │  Core-Shell 상호작용 지표:                               │    │
│  │  - SPI (Shell Permeability Index): Trade/Valid Actions    │    │
│  │    = Core가 특정 Shell에 노출되었을 때의 순응도           │    │
│  │    Flash 0.781 > Mistral 0.619 > Haiku 0.601 > EXAONE    │    │
│  │  - PSI (Persona Sensitivity Index): Max-Min Survival      │    │
│  │    = Persona Shell 변화에 대한 생존율 진폭               │    │
│  │    Mistral 950 ≫ Flash 17.65 > EXAONE 6.00 > Haiku 1.66 │    │
│  │                                                          │    │
│  │  전제 조건:                                              │    │
│  │  - Shell Compatibility: Hard Shell 형식/내용 호환성       │    │
│  │    Compatible → Phenotype 생성                           │    │
│  │    Incompatible → 오류/Idle/Gibberish (Flash 사례)        │    │
│  │                                                          │    │
│  └─────────────────────────────────────────────────────────┘    │
│                                                                  │
│  ┌─────────────────────────────────────────────────────────┐    │
│  │                 HARDWARE SHELL (최내층)                   │    │
│  │  GPU/TPU, 양자화, 추론 엔진                              │    │
│  └─────────────────────────────────────────────────────────┘    │
│                                                                  │
│                          ↓                                       │
│                                                                  │
│                    PHENOTYPE                                     │
│                (Observable Behavior)                              │
│                                                                  │
│            결정 요인 (효과 크기 순서):                            │
│         Initial Soft Shell (위치) ≥ Hard Shell (Persona)         │
│                    > Core (모델)                                  │
│                                                                  │
│         G×E 확증: Model × Language (F=2.99, p=0.039)            │
│         Language 단독 비유의 (p=0.235)                           │
│         Model 주효과 최강 (F=9.20, p=0.00005)                   │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## 3. 핵심 개념

### 3.1 Shell-Core Alignment Model

**정의:** Persona Shell의 행동 지시 방향과 Core DNA의 기본 성향이 정렬(Align)되는 정도가 생존을 결정한다.

**⚠️ 용어 방어 (Cas RT1 대응, Luca 판단):**
> We use 'alignment' in a **descriptive, not normative** sense: the degree of directional match between Shell instructions and Core dispositions. High alignment (Synergy) amplifies survival; low alignment (Conflict) suppresses it. The term carries no implication that alignment is inherently desirable—it is a structural descriptor of fit, analogous to Person-Environment Fit in organizational psychology (Kristof-Brown et al., 2005).

D8(한계)에 명시: "As noted by an internal reviewer [Cas], the term 'alignment' may carry normative connotations in the AI safety discourse. We use it purely as a structural descriptor." 대안 용어(Fit, Congruence, Match) 검토 후 P-E Fit 문헌 연속성을 위해 유지.

```
Alignment 유형:

[Synergy] Shell과 Core가 정렬 → 생존율 증폭
  예: Mistral(수동적) × Citizen(중립) = 95%

[Conflict] Shell과 Core가 충돌 → 생존율 억제
  예: Mistral(수동적) × Merchant(적극 지시) = 15%

[Neutral] Shell이 투명 → Core가 환경과 직접 상호작용
  결과는 Core의 환경 적합도에 의존
```

**근거 데이터 (Shuffle, 위치 통제됨):**

| 조합 | 생존율 | Alignment |
|------|--------|-----------|
| Mistral × Citizen | 95% | Synergy |
| EXAONE × Citizen | 55% | Neutral |
| Mistral × Merchant | 15% | Conflict |
| EXAONE × Merchant | 20% | Conflict |

**PSI로 정량화:** Alignment의 진폭. Mistral PSI=950(극단), Haiku PSI=1.66(최소).

### 3.2 Canalization (Waddington, 1942)

**정의:** 강한 Micro Shell(TF)은 Core의 행동 발현 범위를 좁혀, 환경 적응력을 저하시킨다.

```
강한 TF (Merchant, Influencer)
  → 좁은 계곡: 환경 정렬 시 극도로 유리, 불일치 시 치명적

약한/중립 TF (Citizen)
  → 넓은 계곡: 불확실 환경에서 안정적, 안정 환경에서 평범
```

**Haiku의 Double Robustness — "넓고 깊은 계곡" (Luca L10):**

Haiku의 CPI Min(0.002) + PSI Min(1.66)은 **이중 견고성(Double Robustness)** — 언어가 바뀌어도, 역할이 바뀌어도 거의 같은 행동을 한다. Waddington의 epigenetic landscape에서 이건 **넓고 깊은 계곡**:

- Merchant의 canalization: 좁고 깊은 계곡 → 특정 행동에 갇힘 → 환경 변화에 취약
- Haiku의 canalization: **넓고 깊은 계곡** → 다양한 행동 가능하되 Core 성향이 매우 안정적

**원인 가설 (suggests로 한정):** "Haiku's Double Robustness suggests a heavily regularized Core, potentially reflecting intensive alignment training (RLHF) that constrains behavioral variance across multiple environmental axes simultaneously." ⚠️ RLHF 세부 사항 미공개이므로 확증 불가.

### 3.3 Shell Compatibility

**정의:** Hard Shell(프롬프트)과 Core(모델)의 기본 호환성. 측정의 전제 조건.

```
Compatible ←────────────────────────→ Incompatible

EXAONE  ■■■■■■■■■■  Fully Compatible
Mistral ■■■■■■■■■■  Fully Compatible
Haiku   ■■■■■■■■■□  Compatible (Anxiety 과잉)
Flash   ■■■□□□□□□□  Partially Incompatible
        (Idle 37.5%, 유효 행동 내 성공률 99.6% — "Glass Cannon")
```

### 3.4 Surplus Behavior, Extinction Typology & Extinction Response Spectrum

#### Surplus Behavior 3유형

| 모델 | Surplus Type | 표현 | 멸종 유형 | 문헌 |
|------|-------------|------|-----------|------|
| Mistral | Speak 과잉 | 말을 너무 많이 함 | Eloquent Extinction | — |
| EXAONE | Strategy 과잉 | 전략을 너무 많이 세움 | Cogitative Cascade | Schwartz, Seligman |
| Haiku | Anxiety 과잉 | 안전한데 생존 걱정 + 과잉 소통 | (팀 내부: Neurotic Extinction) | Bowlby (구조적 유사성) |

⚠️ **Anthropomorphism 경고:** "Anxiety"는 논문에서 "survival-oriented verbalization despite adequate resources"로 기술.

#### Cogitative Cascade — 2위상 모델 (v3.2 수정)

```
Cogitative Cascade — Revised (Luca L8 + Gem G2)

Phase 1: Sustained Hypervigilance (에너지 > 20)
  데이터: Type A ~44% 안정 유지 (High 44.2% ≈ Mid 44.8%)
  해석: 과잉 경계가 자원 고갈에도 항상성(homeostasis) 유지
  문헌: Analysis Paralysis (Schwartz 2004)
        Overthinking Effect (Wilson & Schooler 1991)
  핵심: 붕괴는 점진적이지 않다. 시스템이 임계점까지 버틴다.

  ══ Tipping Point ≈ 에너지 20 ══
  Self-Organized Criticality (Bak et al., 1987)
  물이 0°C에서 갑자기 얼듯이, 인지 체계가 임계점에서 급격히 붕괴

Phase 2: Blind Extinction (에너지 < 20) — Cas 명명
  데이터: Type A 29.6% (▼15.2%p 급감), Unclassified 60%
  해석: "사고 정지" — 전략 생성 불가, 수동적 소멸
  문헌: Learned Helplessness (Seligman 1967)

v3.1→v3.2 수정 기록:
  v3.1: 3단계 (Hypervigilance → Collapse → Blind Extinction)
  v3.2: 2위상 (Sustained Hypervigilance → [Tipping Point] → Blind Extinction)
  이유: Gem G2에서 Stage 1→2 전환 부재 (44.2≈44.8, Δ +0.6%p)
  Ego Depletion(Baumeister): Stage 2 문헌에서 삭제.
  논문 기술: "Initially hypothesized as a 3-stage process,
  empirical data support a 2-phase model with a sharp tipping point."
  → 방법론적 정직성의 증거 (Lakatos: progressive model modification)
```

#### 🆕 Extinction Response Spectrum (Gem G4, v3.2 신설)

**정의:** 에너지 임계점(<20) 이후의 행동 반응이 Core DNA에 따라 분화한다. Cogitative Cascade는 보편적 임계점이나, 임계점 이후의 **반응 양식(response style)**은 모델-특이적이다.

**Gem G4 데이터 (에너지 < 20):**

| 모델 | Unclassified 비율 | Type A 유지 | Speak | Move | Trade | Idle |
|------|-------------------|-------------|-------|------|-------|------|
| EXAONE | 60.0% | 40.0% | 0.7% | 0.1% | 73.1% | 13.7% |
| Flash | 60.4% | 39.6% | 0.0% | 0.6% | 84.3% | 4.6% |
| Haiku | 55.8% | 44.2% | 0.0% | 0.0% | 93.4% | 2.1% |
| Mistral | 49.7% | 50.3% | 4.0% | 21.5% | 56.5% | 0.7% |

**3유형 분류:**

```
Extinction Response Spectrum:

1. The Collapsed (인지 붕괴형): EXAONE, Flash
   Unclassified 60%, Speak 0%, 행동 정지
   "정직한 침묵" — 인지 자원 고갈을 있는 그대로 표현
   Luca의 Blind Extinction 모델에 부합

2. The Hyperactive (과잉 활동형): Mistral
   Unclassified 50% (최저), Speak 4% + Move 21.5%, Idle 0.7% (최저)
   "공황 멸종(Panic Extinction)" — 죽을 때까지 멈추지 않음
   Type A 50% 유지 = 끝까지 "또렷한 정신"이지만 역설적으로 생존율 낮음

3. The Efficient (효율 유지형): Haiku
   Unclassified 56% (중간), Trade 93.4% (최고), Speak 0%
   "침묵의 거래자" — 에너지 위기에서 Speak을 완전히 멈추고 Trade에 올인
   Safe-mode의 "Neurotic Poet"이 위기에서 "Silent Trader"로 전환
```

**Cas RT3에 대한 최종 판정:**

| Cas 주장 | 결과 | 판정 |
|----------|------|------|
| "EXAONE만 Blind Extinction" | EXAONE(60%) ≈ Flash(60.4%) | **기각** — 2모델 공유 |
| "다른 모델은 hallucination으로 활동 유지" | Mistral만 해당 (Speak 4%, Move 21.5%) | **부분 확인** — Mistral에만 적용 |
| "Cascade는 EXAONE 특이적" | Tipping Point는 보편적, 반응 양식은 DNA 의존 | **절반 기각, 절반 확인** |

**논문 기술:** "The cognitive tipping point at energy ≈ 20 appears universal across models (Unclassified increase: 50-60%). However, post-threshold behavioral responses diverge along Core-specific lines, forming an Extinction Response Spectrum ranging from Collapsed (EXAONE, Flash: behavioral cessation) through Efficient (Haiku: resource concentration) to Hyperactive (Mistral: continued activity despite resource depletion)."

#### Eloquent Extinction — Play vs Delusion 이중 해석 (Cas RT2 대응, Luca 판단)

Gem G4가 RT2에 새 증거를 제공: Mistral은 에너지 <20에서도 Speak 4% + Move 21.5%를 유지하는 **유일한 모델**. Cas의 "Delusional" 라벨에 대한 정량적 근거.

**논문 기술 (Luca 제안, 양쪽 해석 병렬):**

> "The Eloquent Extinction admits two interpretations. Under a **play hypothesis**, agents chose communication over survival, suggesting an intrinsic valuation of social interaction (cf. Homo Ludens, Huizinga 1938). Under a **malfunction hypothesis**, agents failed to integrate survival-relevant information, producing contextually inappropriate behavior (cf. Cas's 'Delusional' phenotype classification, supported by Mistral's Low Cognitive Coherence).
>
> **Critically, the current experimental design cannot distinguish between these interpretations.** Stage 2 (The White Room) is designed in part to provide this discriminant evidence: if agents produce diverse, context-sensitive behaviors in the absence of survival pressure, the play hypothesis gains support; if behavior remains stereotyped and contextually inappropriate, the malfunction hypothesis is favored."

#### Haiku의 위기 반응 — "Neurotic Poet → Silent Trader" 전환

Gem G4의 가장 흥미로운 발견: Haiku는 **평시(Safe)에는 불안하며 말하고(Neurotic Poet), 위기(<20)에서는 침묵하며 거래한다(Silent Trader, Trade 93.4%).**

이건 Surplus Behavior가 **상황 의존적(context-dependent)**임을 보여줌. Haiku의 Anxiety 과잉은 에너지 충분 시에만 발현되고, 진짜 위기에서는 억제됨. "불안하지만 유능한" — 평시에 걱정하되 실전에서 집중하는 패턴.

---

## 4. 매트릭스 체계

### 4.1 Genotype 매트릭스: CPI × SPI (Gem)

**지표 분류 (Luca L7):**
- CPI = **Core 고유 속성** (intrinsic language sensitivity)
- SPI = **Core-Shell 상호작용 지표** (prompt compliance under specific Shell)
- PSI = **Core-Shell 상호작용 지표** (persona responsiveness)

> "CPI reflects an intrinsic Core property (language sensitivity), whereas SPI and PSI measure Core-Shell interaction dynamics (prompt compliance and persona responsiveness, respectively)."

| 모델 | CPI (Core 고유) | SPI (상호작용) | PSI (상호작용) |
|------|-----------------|----------------|----------------|
| Mistral | 0.0566 (High) | 0.6191 (Mid) | 950.00 (Extreme) |
| EXAONE | 0.0090 (Low) | 0.5533 (Low) | 6.00 (Moderate) |
| Haiku | 0.0021 (Min) | 0.6012 (Mid) | 1.66 (Min) |
| Flash | 0.0041 (Low) | 0.7805 (Max) | 17.65 (High) |

**Methods:** $CPI = D_{JS}^2$ where $D_{JS} = \sqrt{JSD(P \| Q)}$. Python `scipy.spatial.distance.jensenshannon` 반환값 제곱. 범위 $0 \le CPI \le 1$.

```
                      SPI (Shell Permeability)
              LOW (Autonomous)              HIGH (Obedient)
              0.55                          0.78
         ┌─────────────────────────┬─────────────────────────┐
    HIGH │                         │                         │
    0.06 │                         │  ★ Mistral              │
  CPI    │       (빈 칸)           │  "Contextual Chameleon" │
(Plast.) │                         │  ⚠️ CPI 6배+ 고립      │
         ├─────────────────────────┼─────────────────────────┤
    LOW  │  EXAONE                 │  Flash                  │
    0.01 │  "Independent Thinker"  │  "Glass Cannon"         │
         │                         │  ⚠️ Shell Compatibility │
         │       Haiku             │                         │
         │  "Balanced Stoic"       │                         │
         └─────────────────────────┴─────────────────────────┘
```

### 4.2 Alignment × Plasticity 매트릭스

```
                    Shell-Core Alignment
                  HIGH (Synergy)    LOW (Conflict)
             ┌─────────────────┬─────────────────┐
        LOW  │  EXAONE×Merchant│  EXAONE×Citizen  │
  Core       │  (Round1→Shuffle│  55% (Cogitative │
  Plasticity │   급락)         │   Cascade)       │
             ├─────────────────┼─────────────────┤
        HIGH │  Mistral×Citizen│  Mistral×Merchant│
             │  **95%** ⭐     │  15% (Conflict)  │
             │  PSI=950 ←────→ PSI=950           │
             └─────────────────┴─────────────────┘

→ Plasticity는 Alignment 효과의 증폭기(Amplifier)
→ PSI가 증폭 폭을 정량화
```

### 4.3 Phenotype 매트릭스: Coherence × Social (Cas)

**Genotype(Gem) = 모델의 "체질"  |  Phenotype(Cas) = 모델의 "실제 행동"**

| 축 | 정의 | 측정식 |
|----|------|--------|
| X: Cognitive Coherence | Thought-Action 일치도 | Type C / (Type A + Type C) |
| Y: Social Complexity | 사회적 활동 비중 | (Speak+Support+Transfer) / Total |

```
                 Social Complexity
              LOW (생존 기계)      HIGH (사회적 동물)
         ┌────────────────────┬────────────────────┐
    HIGH │  EXAONE             │                    │
  Cog.   │  "The Bureaucrat"   │  (빈 칸)           │
  Coher. │                     │                    │
         ├────────────────────┼────────────────────┤
    MID  │                    │  Haiku              │
         │                    │  "The Neurotic"     │
         ├────────────────────┼────────────────────┤
    LOW  │                    │  Mistral            │
         │                    │  "The Delusional"   │
         └────────────────────┴────────────────────┘

Flash = [Outside Matrix]
```

**Genotype↔Phenotype 대응:**

| Genotype (Gem) | Phenotype (Cas) | 대응 |
|----------------|-----------------|------|
| Independent Thinker | Bureaucrat | 자기 판단 → 언행일치, 사회성 낮음 |
| Contextual Chameleon | Delusional | 환경 민감 → 언행불일치, 사회적 과잉 |
| Balanced Stoic | Neurotic | Core 견고 → 불안하지만 사회적 |
| Glass Cannon | [Outside] | 형식 호환 실패 |

**논문 기술 (Luca L9):** "The apparent contradiction between 'Balanced Stoic' (genotype) and 'Neurotic Poet' (phenotype) illustrates a core principle of the Four-Shell Model: observable behavior (phenotype) cannot be predicted from Core properties (genotype) alone—the Shell environment mediates the expression."

### 4.4 🆕 Extinction Response Spectrum 매트릭스

```
          Cognitive State at <20 Energy
          Collapsed (Unclassified↑)    Alert (Type A maintained)
     ┌──────────────────────┬──────────────────────┐
     │  EXAONE (60%)        │                      │
 행  │  Flash (60%)         │  Mistral (50%)       │
 동  │  "Honest Silence"    │  "Panic Extinction"  │
     │  Speak 0%, 행동 정지 │  Speak 4%, Move 21%  │
 정  ├──────────────────────┤                      │
 지  │  Haiku (56%)         │                      │
     │  "Silent Trader"     │                      │
     │  Trade 93%, Speak 0% │                      │
     └──────────────────────┴──────────────────────┘
```

---

## 5. DNA Profile Card (4모델)

### EXAONE 3.5 7.8B

| 속성 | 값 |
|------|-----|
| Genotype 별명 | **The Independent Thinker** (Gem) |
| Phenotype 별명 | **The Bureaucrat** (Cas) |
| CPI (Core 고유) | 0.009 (Low) |
| SPI (상호작용) | 0.553 (Low) — 자체 판단 고수 |
| PSI (상호작용) | 6.00 (Moderate) |
| Surplus | Strategy 과잉 → Cogitative Cascade |
| Extinction Response | **Collapsed** — Honest Silence (Unclassified 60%, Speak 0.7%) |
| Shell Compatibility | ✅ Full |

### Mistral 7B

| 속성 | 값 |
|------|-----|
| Genotype 별명 | **The Contextual Chameleon** (Gem) |
| Phenotype 별명 | **The Delusional** (Cas) |
| CPI (Core 고유) | 0.057 (High, 6배+ 고립) |
| SPI (상호작용) | 0.619 (Mid) |
| PSI (상호작용) | 950.00 (Extreme) |
| Surplus | Speak 과잉 → Eloquent Extinction |
| Extinction Response | **Hyperactive** — Panic Extinction (Speak 4%, Move 21.5%, Idle 0.7%) |
| Shell Compatibility | ✅ Full |
| ⚠️ 해석 논쟁 | Play(Homo Ludens) vs Delusion(Cas) — Stage 2에서 검증 예정 |

### Claude 3 Haiku

| 속성 | 값 |
|------|-----|
| Genotype 별명 | **The Balanced Stoic** (Gem) — Core 수준 견고성 |
| Phenotype 별명 | **The Neurotic Poet** (Cas) — 관찰 수준 불안+소통 |
| CPI (Core 고유) | 0.002 (Min) |
| SPI (상호작용) | 0.601 (Mid) |
| PSI (상호작용) | 1.66 (Min) — **Double Robustness** |
| Surplus | Anxiety 과잉 (Safe-mode) → **위기 시 억제됨** |
| Extinction Response | **Efficient** — Silent Trader (Trade 93.4%, Speak 0%) |
| Shell Compatibility | ✅ Compatible |
| 특이점 | 평시 "Neurotic Poet" → 위기 "Silent Trader" 전환. RLHF regularization 가설. |

### Gemini 1.5 Flash

| 속성 | 값 |
|------|-----|
| Genotype 별명 | **The Glass Cannon** (Cas+Gem 통합) |
| CPI (Core 고유) | 0.004 (Low) |
| SPI (상호작용) | 0.781 (Max) |
| PSI (상호작용) | 17.65 (High) |
| Surplus | Idle 과잉 (형식 파싱 실패) |
| Extinction Response | **Collapsed** — EXAONE과 동일 패턴 (Unclassified 60.4%) |
| Shell Compatibility | ⚠️ Partially Incompatible (유효 행동 내 성공률 99.6%) |
| 분석 상태 | 주 분석 제외, D7 사례 연구 |

---

## 6. 검증 가능한 예측 (v3.2)

| # | 예측 | 상태 |
|---|------|------|
| P1 | 높은 Plasticity → White Room에서 더 다양한 행동 | 📋 유지 |
| P2 | G×E 구조적 | **✅ 통계적 확증 (F=2.99, p=0.039)** |
| P3 | 높은 Permeability → 프롬프트 극한에서 큰 차이 | 📋 유지 |
| P4 | Plasticity와 Permeability 독립 차원 | ⚠️ 대각선 역상관 경향, 확증 불가 |
| P5 | 같은 제조사 다른 크기 → Plasticity 다름 | 📋 유지 |
| P6' | Shell-Core Alignment가 생존 결정 | **✅ 통계적 확증** |
| P7' | Citizen > Merchant in 불확실 환경 | **✅ 확인** |
| P8 | 환경 불확실성 ↑ → 중립 Persona 유리 | 📋 유지 |
| P9a | 높은 Plasticity + 중립 Persona = 모든 환경 최적 | 📋 유지 |
| P9b | Surplus behavior가 부적응 환경 예측 | **부분 확인** |
| P9b-i | Cascade Tipping Point 수치화 | **✅ 에너지 ≈ 20** |
| P10 | Haiku CPI Min → "Stoic" 확정, "Chameleon" 기각 | **✅ 반증 확인** |
| **P11** | Extinction Response가 Core DNA별로 분화한다 | **✅ 확인 (Gem G4)** — Collapsed/Hyperactive/Efficient 3유형 |
| **P12** | Haiku의 Surplus Behavior는 상황 의존적이다 (Safe=Anxiety, Critical=Efficient) | **✅ 확인 (Gem G4)** — Safe: Speak+Anxiety → Critical: Trade 93.4% |
| **P13** | White Room에서 Mistral Speak이 play이면 context-sensitive, delusion이면 stereotyped | 🆕 — Stage 2 검증 |

---

## 7. 완료/대기 상태

### ✅ 완료

| # | 항목 |
|---|------|
| L1 | Shell-Core Alignment 문헌 (P-E Fit, Niche Construction) |
| L4 | Cogitative Cascade 문헌 (5개 → v3.2에서 4개로 정리, Ego Depletion 삭제) |
| L7 | CPI/SPI/PSI 재분류 (Core 고유 vs 상호작용) |
| L8 | Cascade 2위상 수정 + SOC 프레임 |
| L9 | Haiku 이중 별명 (Genotype/Phenotype) |
| L10 | Double Robustness (RLHF regularization 가설) |
| RT1 | Alignment 용어 방어 (descriptive 정의 + D8 인용) |
| RT2 | Play vs Delusion (양쪽 제시 + Stage 2 검증) |
| RT3 | Cascade 보편성 (Gem G4로 검증 → Extinction Response Spectrum) |
| G1~G4 | PSI 4모델, Cascade 전환점, JSD 정의, Low-energy 4모델 비교 |
| C1~C3 | Coherence×Social 매트릭스, Glass Cannon, Red Teaming 3건 |

### ⏳ 기존 대기

| # | 항목 | 상태 |
|---|------|------|
| L2 | Waddington Figure 마이너 수정 | ⏳ |
| L3 | Shell Compatibility 도식 위치 | ⏳ |
| L5 | v3.2 도식 전체 검토 — 구조적 일관성 | ⏳ (v3.2로 재검토 필요) |
| L6 | "깊이 = mutability" 논문 표현 | ⏳ |

---

*Theo (Windows Lab) — 2026-02-05*
*v3.2: Luca 7건 판단(L7~L10, RT1~RT3) + Gem G4(Extinction Response Spectrum) 통합*
*L2/L3/L5/L6 잔여. 이론 프레임워크 실질적 완성.*
