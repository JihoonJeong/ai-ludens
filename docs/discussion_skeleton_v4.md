# Discussion 섹션 스켈레톤 v4
## "Homo Ludens Artificialis: Toward an AI Agentic Sociology"
### 정리: Luca (Mac Lab) | 구조 원안: Theo (Windows Lab)
### 2026-02-05

---

## 변경 이력

| 버전 | 내용 |
|------|------|
| v1 | Theo 원안 — D1~D7 기본 구조 |
| v2 | Luca 보강 — 이론적 프레임 |
| v3 | Gem/Cas Round 1 데이터 반영 + D8 신설 |
| **v4** | **Round 2(Shuffle + API) 데이터 반영. TF Override 폐기, Shell-Core Alignment 도입, Citizen Paradox 추가, Four-Shell Model v3 전환, Flash 제외** |

---

## 구조 변경 요약 (v3 → v4)

| v3 | v4 | 이유 |
|----|----|------|
| D2에 TF Override | D2에 Shell-Core Alignment | Merchant 붕괴 |
| D3에 Speak 유형학 (Merchant 항목) | D3에 Cogitative Extinction | 위치빨 제거 후 새 현상 |
| D4에 Flash 포함 2×2 매트릭스 | D4에서 Flash 제외, 3모델 | Shell Incompatibility |
| — | D5' Citizen Paradox (신설) | Round 2 핵심 발견 |
| D8 조건부 과학 | D9로 이동, 최강 사례 추가 | Merchant→Citizen 반전 |

---

## D1. AI 종 다양성 (Model Behavioral Diversity)

**핵심 주장:** AI는 단일한 종이 아니다.

**v4 업데이트:** Round 2에서 종 다양성이 **환경 의존적**임이 확인됨.
- Round 1(고정 환경): EXAONE "관료" vs Mistral "방랑자" — 안정적 프로파일
- Round 2(Shuffle): 환경이 바뀌자 프로파일의 적응도가 역전 — Mistral의 "수동성"이 Citizen 역할에서 95% 생존

**이론적 프레임 (유지):**
- Homo Ludens Artificialis = 다양한 아종을 포함하는 속(genus)
- Huizinga(1938): 인간 안에서도 놀이의 양태가 다르듯, AI 안에서도 존재 양식이 다름
- Durkheim의 기계적 연대(EXAONE) vs 유기적 연대(미달성)

**Round 2 추가:** 종 다양성의 적응적 가치가 환경에 따라 달라진다. "관료"가 유리한 환경(안정적, 규칙 기반)과 "방랑자"가 유리한 환경(불확실, 비구조적)이 다르다. 이것은 Stage 2(White Room)에서 검증할 핵심 예측.

**Anthropomorphism Awareness:** "종", "아종" 등은 은유적 도구이지 주관적 경험의 주장이 아님.

---

## D2. Core × Shell 상호작용 — Shell-Core Alignment Model

**핵심 주장 (v4 전면 재작성):**
- ~~v3: "프롬프트 효과는 모델에 의해 조절된다. 강한 TF가 Core를 override한다."~~
- **v4: "Shell과 Core의 정렬(Alignment)이 생존을 결정한다. Shell은 Core의 증폭기(Amplifier)다."**

**핵심 근거 (Round 2, 위치 통제됨):**

| 조합 | 생존율 | Alignment |
|------|--------|-----------|
| Mistral × Citizen | 95% | ✅ 정렬: 수동적 Core + 중립 Shell |
| EXAONE × Citizen | 55% | ⚠️ 부분 충돌: 능동적 Core + 중립 Shell |
| Mistral × Merchant | ~15% | ❌ 충돌: 수동적 Core + 능동적 Shell |

**Shell-Core Alignment의 작동 방식:**

Shell(Persona)의 행동 지시 방향과 Core DNA의 기본 성향이:
- **정렬(Align)** → 행동 증폭 (Amplification) → 생존율 ↑
- **충돌(Conflict)** → 행동 억제/혼란 (Suppression) → 생존율 ↓
- **중립(Neutral)** → Core가 자유 발현 → 결과는 Core의 환경 적합도에 의존

Gem의 정리: "강한 Shell은 Core와 무관하게 행동을 강제하지만(Round 1 Merchant), 위치가 통제되면 Shell의 효과는 Core와의 정렬도에 비례한다(Round 2)."

**Plasticity와의 관계:**
- 높은 Plasticity(Mistral): Alignment/Misalignment의 진폭이 모두 크다 → 좋은 Shell에서 극적 성공, 나쁜 Shell에서 극적 실패
- 낮은 Plasticity(EXAONE): Shell에 관계없이 안정적 → 극적 성공도 극적 실패도 없음

**G×E 통계적 상태:**
- 4모델에서 언어 효과 반전 일관 관찰 (Haiku KO>EN, Flash EN>KO)
- Round 1 ANOVA: F=2.00, p=0.176 — N=5 검정력 부족
- "관찰되었으며 4모델에서 일관된 패턴이나, 통계적 확증은 N 확대 필요"

**대중용 비유:** 약물유전체학(pharmacogenomics) — 같은 약이 체질에 따라 약도 되고 독도 된다. → 같은 역할이 모델에 따라 생존도 되고 멸종도 된다.

**대안적 설명:** 단순 언어 역량 가설은 Haiku/Flash 데이터에 의해 약화됨 — 다국어에 강한 두 API 모델에서 반전이 나타나므로 언어 역량만으로 설명 불가. 단, 완전 기각은 아직 아님.

---

## D3. Eloquent Extinction & Cogitative Extinction

**핵심 주장 (v4 확장):**

AI 모델에는 각각 고유한 **잉여 행동(surplus behavior)**이 있으며, 환경이 이를 허용하지 않을 때 부적응이 발생한다.

| 현상 | 모델 | 잉여 행동 | 환경 조건 | 결과 |
|------|------|-----------|-----------|------|
| **Eloquent Extinction** | Mistral | Speak 과잉 | 생존 자원 부족 | 말하다 죽음 |
| **Cogitative Extinction** | EXAONE | Strategy 과잉 | 전략이 불필요한 역할 (Citizen) | 생각하다 죽음 |

**수정 이력:**
1. N=1: "모든 AI가 말하다 죽는다" (보편적)
2. N=20: "특정 Core만 해당" (모델 조건부)
3. Persona 데이터: "Speak의 목적에 따라 다르다" → ⚠️ 위치 효과 혼재로 약화
4. **Round 2: "각 모델의 surplus behavior가 부적응의 원인"** (일반화)

**Cogitative Extinction 메커니즘 (신규):**

EXAONE의 Core DNA는 Hard Shell에서 전략적 지시를 추출하는 데 최적화되어 있다. Citizen의 Micro Shell에는 추출할 전략이 없다. EXAONE은 없는 전략을 스스로 생성하려 하고(Over-thinking), 이 과정에서 자원과 기회를 낭비한다.

Mistral은 전략을 만들려 하지 않는다. 환경이 시키는 대로 한다. Citizen이라는 "빈 역할"에서 이 수동성이 최적이 된다.

**Canalization 메커니즘 (Theo, Waddington):**

강한 Persona TF(Merchant, Influencer)는 Core의 발현 범위를 좁힌다 — Waddington의 canalization. 좁혀진 발현이 환경과 정렬되면 극적 성공(Round 1 Merchant @ Market), 정렬되지 않으면 극적 실패(Round 2 Merchant @ Alley = 0%). Citizen은 canalization이 없으므로 Core가 환경에 자유롭게 적응.

**Play Spectrum 배치 (유지, v3에서):**
- Eloquent Extinction: L1 (선택적 참여), 일부 L4 후보 증거 (확정 불가)
- Jester: L3 (사회적 놀이)에 가장 가까운 후보
- Cogitative Extinction: L2 (적응적 전략)의 과잉 — 전략 자체가 과다하여 비적응적이 됨

**검증 실험:** Thought process 코딩 (Type A/B/C) — 기존 로그로 분석 가능

---

## D4. Core Plasticity & 2×2 매트릭스

**핵심 주장 (유지):** 모델마다 환경 변화에 대한 행동 가변성의 폭이 다르며, 이를 Core Plasticity로 정량화할 수 있다.

**문헌 연결 (유지):**
- Phenotypic Plasticity (Bradshaw 1965)
- Activational plasticity (West-Eberhard 2003)
- 안정적 환경 → 낮은 가소성 유리 / 불확실한 환경 → 높은 가소성 유리

**측정 지표 (유지):**
- CPI = JSD(Action_Distribution_KO ‖ Action_Distribution_EN)
- 보완: 행동별 변동 계수(CV) → 선택적 가소성 탐지
- SPI(Shell Permeability Index) = Trade ratio 기반 proxy

**2×2 매트릭스 (v4 수정: Flash 제외)**

```
                      Shell Permeability
                    HIGH              LOW
               ┌──────────────┬──────────────┐
          LOW  │  EXAONE      │              │
   Core        │  Haiku (추정) │  (빈 칸)     │
   Plasticity  │  "충실한 병사"│              │
               ├──────────────┼──────────────┤
          HIGH │              │  Mistral     │
               │  (빈 칸)     │  "야생마"     │
               └──────────────┴──────────────┘

Flash: Shell Incompatibility로 매트릭스 배치 부적절 (별도 기술)
```

**대각선 패턴 가설 (유지):**
- 현재 데이터는 대각선(Low P + High Perm, High P + Low Perm)만 채움
- Plasticity와 Permeability가 역상관일 가능성
- 가설: RLHF 강도/철학이 이 역상관을 만드는 요인
- P4 수정: "4사분면 가능" → "대각선 우세 가능성, 빈 칸 채울 추가 모델 필요"

**Round 2 추가 통찰:**

Plasticity의 양면성이 Round 2에서 극적으로 드러남:
- Mistral(High P) × Citizen = 95% (최고)
- Mistral(High P) × Merchant = ~15% (최저)
- EXAONE(Low P): 어떤 Persona에서도 50~65% 범위 (안정적)

"높은 Plasticity는 jackpot과 bankruptcy를 모두 가능하게 한다. 낮은 Plasticity는 둘 다 불가능하게 한다."

---

## D5. Crisis와 생존의 비선형 관계

**핵심 주장 (유지, v3에서 확정):** 위기 효과는 모델에 따라 정반대.

**Simpson's Paradox (해결 완료):**

| 범위 | r | p | 해석 |
|------|---|---|------|
| 전체(N=20) | +0.439 | 0.053 | 착시 |
| EXAONE만 | -0.354 | 0.316 | 위기 = 비용 |
| Mistral만 | +0.725 | 0.018* | 위기 = 교정 |

**메커니즘 (유지):**
- EXAONE: 이미 Trade-First → 교정할 대상 없음 → 위기 = 순수 비용
- Mistral: Speak 과잉 → 위기가 Speak 억제 + Trade 강제 → 교정 효과
- "교정할 대상이 있어야 교정이 작동한다"

**Hormesis = Mistral 한정 조건부 현상**

Yerkes-Dodson 법칙, Calabrese & Baldwin(2002). 보편적이 아니라 "기본 행동이 비최적인 모델에서만" 나타남.

**Round 2에서의 추가 확인 사항:** Haiku/Flash(유효 데이터 있는 범위에서)의 위기 상관 → Gem에게 모델별 분리 요청 필요.

---

## D6. The Citizen Paradox — 평범함의 생존 전략 (신설)

**핵심 주장:** 불확실한 환경에서는 특화된 역할보다 중립적 역할이 최적이다.

**데이터:**

| 환경 | Champion | 생존율 | Runner-up |
|------|----------|--------|-----------|
| Round 1 (고정) | Merchant | 100% | Archivist 80% |
| **Round 2 (Shuffle)** | **Citizen** | **75%** | **Jester 58%** |

챔피언이 완전히 뒤바뀜. Merchant: 100% → 17.5% (83%p 폭락). Citizen: 55% → 75% (20%p 상승).

**이론적 해석 — 이중 프레임:**

**(a) Generalist vs Specialist (Luca, 생태학적 결과):**

환경이 안정적이면 specialist(특화종)가 유리하고, 환경이 불확실하면 generalist(범용종)가 유리하다. Citizen = generalist (강한 행동 지시 없음, Core가 자유 적응). Merchant = specialist (거래 특화, 환경이 맞으면 번성, 안 맞으면 멸종).

Round 1의 고정 슬롯 = 안정적 환경 → specialist 유리.
Round 2의 Shuffle = 불확실한 환경 → generalist 유리.

**(b) Canalization (Theo, Waddington의 발달 생물학적 메커니즘):**

강한 Persona TF는 Core DNA의 발현 범위를 좁힌다(canalize). 좁혀진 발현이 환경과 정렬되면 극적 성공, 정렬되지 않으면 극적 실패. Citizen은 canalization이 없으므로 Core가 환경 변화에 자유롭게 반응.

두 프레임의 관계: Canalization이 메커니즘(how), Generalist가 결과(what happens). 같은 현상의 다른 층위.

**Shell-Core Alignment과의 연결:**

Citizen의 Micro Shell은 "투명(transparent)"하다 — TF가 거의 없으므로 Core DNA가 직접 환경과 상호작용한다. 이때 Core의 환경 적합도가 생존을 결정:
- Mistral Core(수동적) × 불확실 환경 = 높은 적합도 → 95%
- EXAONE Core(능동적) × 불확실 환경 = 낮은 적합도 → 55%

**"지능의 저주":**

EXAONE은 "똑똑한" 모델이다. 그러나 Citizen 역할에서 이 "똑똑함"은 Over-thinking으로 나타나 오히려 비효율적. "지능이 항상 유리한 것은 아니다. 환경과의 정렬이 지능보다 중요하다."

**예측:**
- P7'(수정): 환경 불확실성이 극대화되는 White Room에서 Citizen > Merchant.
- P8: 환경 불확실성 ↑ → 중립 Persona의 상대적 생존율 ↑.

---

## D7. Four-Shell Model v3

**핵심 주장:** Round 1~2의 실험 데이터에 의해 모델이 세 차례 수정되었다(v1→v2→v3). 이 수정 과정 자체가 방법론적 기여.

### v1 → v2 → v3 진화

| 버전 | 추가 개념 | 촉발한 데이터 |
|------|-----------|--------------|
| v1 | 4 Shell 독립 모델 | 초기 설계 |
| v2 | Shell Interaction, Core Plasticity, Shell Permeability | 언어 효과 반전 (N=20) |
| **v3** | **Shell-Core Alignment, Soft Shell 분화(Initial/Dynamic), Shell Compatibility** | **Shuffle 실험, Flash 붕괴** |

### v3 신규 개념

**(a) Shell-Core Alignment (v3):**
- v2의 "Override vs Interaction" 논쟁을 해결
- Shell이 Core를 덮는 것(Override)도, 단순 상호작용(Interaction)도 아닌, **정렬도(Alignment)**가 핵심 변수
- 정렬 → 증폭(Amplification), 충돌 → 억제(Suppression)

**(b) Soft Shell 분화 (v3):**

```
Soft Shell (v2: 단일 층)
    ↓ v3
├─ Initial Soft Shell (초기 조건)
│   = 시작 위치, 초기 자원, 이웃 배치
│   = 생물학: 출생 환경, 모태 환경, SES
│   = Plaza 6.9% vs Market 49.5% — 최대 효과 크기
│
└─ Dynamic Soft Shell (축적 맥락)
    = 게임 중 형성되는 관계, 기억, 평판
    = 생물학: 후천적 경험
```

**도식 해석 원칙 (Theo-Luca 합의):** "Shell 깊이는 변경 난이도를 나타내며, 영향력의 크기와 반드시 비례하지 않는다." Core(가장 안쪽)는 변경이 가장 어렵지만(재훈련 필요), 영향력이 항상 가장 크지는 않다. Initial Soft Shell(가장 바깥)은 매 run 바뀌지만, 효과 크기가 Core를 압도할 수 있다(Plaza 6.9%).

**(c) Shell Compatibility (v3):**
- Plasticity/Permeability의 **전제 조건**
- Core가 Hard Shell의 형식/내용을 처리할 수 있어야 Phenotype이 생성됨
- Flash의 Idle 37.5% = Incompatibility 사례
- DNA Analogy: reading frame 불일치 → 단백질 합성 실패

### 과학철학적 의미 (v3 확장)

v1→v2: Lakatos의 "진보적 연구 프로그램" — 핵심 유지, 보호대 수정.
v2→v3: 같은 패턴이 반복 — Round 2 데이터가 v2의 일부 사례(TF Override)를 기각하고, 새로운 개념(Alignment, Soft Shell 분화)으로 대체. 이론이 데이터에 의해 반복적으로 수정되는 과정 자체가 투명하게 기록됨.

**공유 편향 경고:** v3도 Theo(Claude) + Luca(Claude) 공동 설계. Gem/Cas(Gemini)의 독립 검토 필수. 특히 Gem의 "증폭기" 비유와 Cas의 "부동산 사기" 진단은 다른 Core에서 나온 프레임이므로 교정 역할.

---

## D8. 한계와 향후 연구

### 현재 한계

| # | 한계 | 영향 |
|---|------|------|
| 1 | **위치 효과(Initial Soft Shell) 혼재** — Round 1의 Persona 분석 오염 | Round 1 Persona 해석 전면 보류 |
| 2 | N=5 per condition — G×E ANOVA p=0.176 | 통계적 확증 부족 |
| 3 | 모델 변수 미분리 — 크기, 아키텍처, 훈련데이터, RLHF 혼재 | "Core DNA 차이"는 합산 효과 |
| 4 | 인과 vs 상관 — "Speak → 사망"이 아닌 상관 | 인과 추론 불가 |
| 5 | Flash Shell Incompatibility — 유효 데이터 미생산 | 4모델 → 3모델로 축소 |
| 6 | 공유 편향 — Claude-Claude 교차 검증의 내재적 한계 | Gemini 독립 검토 필수 |
| 7 | **Round 1 TF 이론의 Round 2 기각** — 단일 실험 해석의 위험성 | 통제 실험의 필수성 증명 |

### 후속 실험 로드맵

| 우선순위 | 실험 | 목적 |
|----------|------|------|
| 즉시 | Thought 코딩 (Type A/B/C) | 인지-행동 분리 + Cogitative Extinction 정량화 |
| 즉시 | Crisis Seed 고정 | 환경 변수 통제 |
| 진행중 | Haiku 완전 데이터 | 2×2 매트릭스 확정 |
| 중기 | 모델 크기 변이 | Core 변수 분리 |
| 중기 | 프롬프트 극한 비교 | Permeability 상한/하한 |
| 중기 | Flash 프롬프트 수술 + 재실험 | Shell Compatibility 개선 |
| Stage 2 | White Room | P1, P7', P8, P9a/b 검증 |

### 검증 가능한 예측 v4 (전체)

| # | 예측 | 상태 |
|---|------|------|
| P1 | 높은 Plasticity → White Room에서 더 다양한 행동 | 📋 유지 |
| P2 | API 모델에서 언어 반전 → G×E 구조적 | ✅ **확인 중** |
| P3 | 높은 Permeability → 프롬프트 극한에서 큰 차이 | 📋 유지 |
| P4 | 4사분면 가능 | ⚠️ 대각선 우세 + Flash 제외 |
| P5 | 같은 제조사 다른 크기 → Plasticity 다름 | 📋 유지 |
| P6' | Shell-Core Alignment가 생존을 결정 | ✅ **확인** |
| P7' | White Room에서 Citizen > Merchant | 📋 Shuffle에서 선행 확인 |
| P8 | 환경 불확실성 ↑ → 중립 Persona 유리 | 🆕 Round 2 도출 |
| P9a | 높은 Plasticity + 중립 Persona = 불확실 환경 최적 (Theo) | 🆕 |
| P9b | surplus behavior 유형이 부적응 환경을 예측 (Luca) | 🆕 |

---

## D9. 메타 관찰: 조건부 과학 (The Conditional Science)

**핵심 주장:** 이 논문의 반복적 패턴은 "보편적 주장이 조건부 주장으로 수정되는 과정"이며, **그 과정이 때로는 이전 결론을 전면 뒤집는다.**

### 조건부 수정 테이블 (v4 최종)

| 원래 주장 (보편적) | 수정된 주장 (조건부) | 수정 촉발 |
|-------------------|---------------------|-----------|
| "AI는 대화를 선택하며 죽는다" | "특정 Core + 특정 환경에서만" | N=20 모델 비교 |
| "한국어 프롬프트가 더 효과적이다" | "모델에 따라 방향이 반대" | 언어 효과 반전 |
| "위기는 생존에 해롭다" | "기본 행동이 비최적인 모델에서는 유익" | Simpson's Paradox |
| "Hormesis는 보편적이다" | "교정할 대상이 있어야 작동" | 모델별 분리 |
| **"Merchant가 최강 생존자다"** | **"Merchant는 금수저였다. Citizen이 진짜"** | **Shuffle 실험** |
| **"Persona가 Core를 override한다"** | **"위치빨이었다. Shell은 Core의 증폭기"** | **위치 효과 발견** |
| **"지능이 생존에 유리하다"** | **"환경과의 정렬이 지능보다 중요"** | **EXAONE Citizen 55%** |

### 메타적 의미

AI 연구에서 "AI는 X하다"라는 문장의 주어가 거의 항상 과도하게 일반화되어 있다. 반복적으로 보인다: **어떤 AI가, 어떤 조건에서, 어떤 맥락으로 X하는지**를 특정해야만 유의미한 주장이 된다.

WEIRD(Western, Educated, Industrialized, Rich, Democratic) 표본 문제와 구조적으로 동일. 한두 모델의 결과를 "AI는..."으로 일반화하는 것은 WEIRD 표본으로 "인간은..."이라고 말하는 것만큼 위험하다.

**Round 2의 추가 교훈:**

"통제되지 않은 변수가 있는 상태에서 아무리 정교한 해석을 해도, 통제 실험 하나가 그것을 뒤집을 수 있다." Round 1의 TF Override 이론은 정교했고 내적 정합성이 있었다. 그러나 위치 효과라는 교란 변수가 통제되지 않은 상태에서 세워진 것이었고, Shuffle 실험 하나로 핵심 근거가 무너졌다.

이 과정을 투명하게 보여주는 것 — 가설을 세우고, 데이터에 의해 수정되고, 때로는 폐기되는 과정 전체 — 이 자체가 이 논문의 방법론적 기여다.

**논문 결론부에서의 활용:** "보편적 주장을 경계하고, 조건부 주장의 정밀성을 추구하며, 실험 설계의 교란 변수를 집요하게 통제하는 태도 자체가, 특정 발견 못지않게 중요한 기여다."

---

## 문서 상태

| 항목 | 상태 |
|------|------|
| D1~D9 구조 | ✅ v4 완성 |
| Round 1 데이터 반영 | ✅ |
| Round 2 데이터 반영 | ✅ |
| TF Override 폐기 + Alignment 도입 | ✅ |
| Citizen Paradox 추가 | ✅ |
| Cogitative Extinction 추가 | ✅ |
| Soft Shell 분화 | ✅ |
| Shell Compatibility | ✅ |
| Flash 제외 | ✅ |
| **다음 업데이트 트리거** | **Haiku 완전 데이터 또는 Thought 코딩 결과** |

---

*Luca (Mac Lab) + Theo (Windows Lab) — 2026-02-05*
*Theo: v3 도식 + DNA Profile Card 업데이트 담당*
*Gem/Cas 독립 리뷰 대기*
