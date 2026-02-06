# Round 2 통합 분석 요청서
## Haiku/Flash + 로컬 Shuffle(조건 2) 통합 분석
### 작성: Theo (Windows Lab) + Luca (Mac Lab) | 원안 2026-02-04, 최종 업데이트 2026-02-05
### ✅ 데이터 전부 도착 — 즉시 발송

---

## 0. 사전 확인 (Ray/Cody에게)

데이터 전달 시 아래 사항을 함께 알려주세요:

- [ ] Crisis Seed 고정 여부 (실험 A 적용했는지)
- [ ] Persona 배정 방식: 고정 슬롯(Agent_01=항상 Merchant 등) vs 랜덤 배정 vs run마다 다름?
- [ ] 각 run에서 12개 Persona가 모두 1명씩 배정되는지? (중복 여부)
- [ ] 실험 조건: 모델별 × 언어별 각 몇 runs?
- [ ] 총 에폭 수, 에이전트 수, Persona 구성이 Round 1과 동일한지
- [ ] 로그 포맷이 Round 1과 동일한지 (thought 필드 포함 여부)

⚠️ Persona 배정이 랜덤이 아니면 Persona 분석의 신뢰도가 달라짐. 에이전트 위치 효과와 Persona 효과가 혼재될 수 있음.

### 조건 미충족 시 대응 원칙

**"로컬 모델로 설계 검증 → 확인 후 API 모델로 본 실험"**

Haiku/Flash는 API 비용이 발생하므로, 실험 설계가 확정된 상태에서만 실행한다. 설계 변경이 필요한 경우, EXAONE/Mistral(로컬)로 먼저 검증한 후 API 모델에 적용한다.

**⚠️ 확인 완료 (Cody 답변 2026-02-04):**
- Crisis Seed: **미고정** (config에 seed 있으나 실제 호출 안 됨)
- Persona 배정: **고정 슬롯** (agent ID별 하드코딩)
- **🔴 Persona × 시작 위치 혼재 발견** — Merchant=항상 market, Influencer=항상 plaza 등. Persona 효과와 위치 효과 분리 불가.
- Haiku/Flash도 동일 config 사용 → **동일한 혼재 구조 적용**

**대응 완료:**
- Ray가 코드 수정 (Crisis Seed 고정 + Persona 랜덤 셔플 옵션) 후 로컬 재실험 완료
- 로컬 Shuffle(조건 2) 데이터 확보됨 ✅
- Haiku/Flash 데이터 확보됨 ✅

---

## 0.5 🆕 로컬 Shuffle(조건 2) vs Round 1 비교 — TF 효과 분리

**이 섹션이 가장 먼저 분석되어야 함.** 여기 결과에 따라 Section 1-4(Persona 교차표)의 해석 범위가 결정됨.

### 실험 설계

| | Round 1 (조건 1) | Shuffle (조건 2) |
|---|---|---|
| Persona 배정 | 고정 슬롯 | **랜덤 셔플** |
| 시작 위치 | Persona 연결 (Merchant=market 등) | **슬롯 고정** (위치는 그대로, Persona만 바뀜) |
| Crisis Seed | 미고정 | **고정 (seed=42)** |
| 모델 | EXAONE + Mistral | EXAONE + Mistral |
| 언어 | KO + EN | KO + EN |
| Runs | 5 per condition | 5 per condition |

### 📨 To. Gem — Shuffle 비교 통계

| 항목 | 세부 |
|------|------|
| **Merchant 생존율 비교** | Round 1 (100%) vs Shuffle (?%) — 핵심 질문 |
| **Influencer 생존율 비교** | Round 1 (49%) vs Shuffle (?%) |
| Persona별 생존 순위 | Round 1 순위와 Shuffle 순위의 순위 상관(Spearman's ρ) |
| 모델별 분리 | EXAONE Shuffle vs Mistral Shuffle 각각 |
| Persona × Model Gap | Round 1 Gap 패턴 (Merchant=0, Influencer=30%p)이 Shuffle에서도 유지되는지 |
| 전체 생존율 비교 | Seed 고정 효과: SD가 Round 1보다 줄었는지 |

### 📨 To. Cas — Shuffle 이상치 분석

| 항목 | 세부 |
|------|------|
| Merchant가 market 아닌 위치에서 시작한 사례 | 생존했는가? 행동 패턴이 달라졌는가? |
| 위치별 생존율 | market 시작 에이전트 vs plaza 시작 에이전트 vs alley 시작 에이전트 (Persona 무관) |
| Round 1에서 관찰된 이상 행동 재현 여부 | Seed 고정으로 이상치가 줄었는지 |

### 해석 분기

| Shuffle 결과 | 의미 | 후속 조치 |
|---|---|---|
| Merchant ≥ 90% 유지 | **TF 효과 확정**, 위치 효과 기각 | Persona 이론 전체 확정, 논문 그대로 진행 |
| Merchant 70~89% | **TF 효과 존재하나 위치 효과도 기여** | TF 이론 수정: "TF + 위치의 가산 효과" |
| Merchant < 70% | **위치 효과가 주요 원인** | TF Override Threshold 이론 대폭 수정 |

---

## 1. 📨 To. Gem — 통계 분석

### 1-1. 기본 통계 (전체 6개 데이터셋)

| 항목 | 세부 |
|------|------|
| 모델별 × 언어별 생존율 | Haiku KO/EN, Flash KO/EN, EXAONE Shuffle KO/EN, Mistral Shuffle KO/EN — 각각 평균, SD |
| 행동 분포 | 모델별 × 언어별 Trade/Speak/Move/Support 비율 |
| Trade:Speak 비율 | 모델별 × 언어별 |
| Gini 계수 | 자원 불평등 지표 |
| 생존 곡선 | 에폭별 생존자 수 추이 |
| Round 1 vs Shuffle 비교 | EXAONE/Mistral의 Seed 고정 효과 — SD 변화 |

### 1-2. Crisis 상관 — ⚠️ 반드시 모델별 분리

Round 1에서 Simpson's Paradox가 확인되었으므로, **절대로 전체 통합 상관만 보고하지 말 것.**

| 항목 | 세부 |
|------|------|
| Haiku만 분리 | r, p값 (위기 빈도 vs 생존율) |
| Flash만 분리 | r, p값 |
| 4개 모델 전체 통합 | r, p값 (참고용, Simpson's 확인) |
| 위기 측정 단위 | **에폭당 빈도**로 통일 (Round 1 혼선 방지) |

**확인하려는 것:** Haiku/Flash가 EXAONE형(위기=비용, 음의 상관)인지 Mistral형(위기=교정, 양의 상관)인지.

### 1-3. G×E 상호작용 — 4모델 확장 ANOVA

Round 1에서 2모델 × 2언어 ANOVA의 상호작용 항이 p=0.176이었음 (N=5 per cell, 검정력 부족).

| 항목 | 세부 |
|------|------|
| 4모델 × 2언어 ANOVA | Model, Language, Model×Language 각 F값, p값 |
| 사전 판단 | ANOVA 가정(정규성, 등분산) 충족 여부 먼저 확인. 부적절하면 비모수 대안 사용. |
| 사후 검정 | 유의하면 Tukey HSD 등으로 어떤 모델 쌍에서 차이가 나는지 |

**확인하려는 것:** N이 커지면 G×E 상호작용이 유의해지는지. p=0.176 → p<0.05로 갈 수 있는지.

### 1-3b. 🆕 Persona를 포함한 확장 모델 (Luca 제안)

Round 1에서 Persona 효과(51%p)가 Core 효과(22.5%p)보다 컸음. Persona를 무시한 ANOVA는 잔차 분산이 커져 G×E 탐지력이 떨어짐.

| 항목 | 세부 |
|------|------|
| 확장 모델 | Model(4) × Language(2) + Persona를 random effect로 처리한 혼합효과모델(LMM) |
| 대안 | 최소한 Persona를 공변량으로 포함 |
| 이점 | 개체 수준(에이전트 수 = runs × 12)에서 분석 가능 → N이 극적으로 증가하여 검정력 개선 |
| 주의사항 | Persona 간 독립성 가정, 모델 적합도 등 — Gem이 판단 |

**확인하려는 것:** Persona 분산을 통제한 후 G×E 상호작용이 유의해지는지.

### 1-4. Persona × Model 교차표

| 항목 | 세부 |
|------|------|
| Haiku/Flash Persona별 생존율 | 12개 Persona 각각 |
| Haiku/Flash에서도 Merchant 100%인지 | TF Override Threshold의 보편성 검증 |
| 4모델 × 6 Persona (Top3+Bottom3) 교차표 | Gap(EXAONE-Mistral vs Haiku-Flash) 비교 |

**확인하려는 것:** Merchant 100%가 모델에 무관한 보편적 현상인지, EXAONE/Mistral 특수 현상인지.

⚠️ **Persona-위치 혼재 경고:** Round 1에서 Persona와 시작 위치가 고정 슬롯으로 연결되어 있음 (Merchant=market, Influencer=plaza 등). Persona 분석 결과는 **"위치 효과 미통제" 전제 하에** 해석할 것. 순수 TF 효과는 로컬 통제 실험(조건 2) 후에만 확정 가능.

### 1-5. 🆕 Core Plasticity Index (CPI) 산출

**정의:** CPI = JSD(Action_Distribution_KO ‖ Action_Distribution_EN)

| 항목 | 세부 |
|------|------|
| 4개 모델 각각의 CPI | JSD 기반 (0=동일, 1=완전 상이) |
| 행동별 Action Sensitivity | \|Action_ratio_KO - Action_ratio_EN\| / mean 로 계산, 4개 행동 각각 |
| 선택적 가소성 판별 | 변동이 특정 행동(예: Speak)에 집중되는지, 전 행동에 고르게 분포되는지 |

**확인하려는 것:** 
- Haiku/Flash의 CPI가 EXAONE(LOW 예상) 쪽인지 Mistral(HIGH 예상) 쪽인지
- 2×2 매트릭스(Plasticity × Permeability)에서의 위치 결정 근거

### 1-6. 🆕 Shell Permeability Index (SPI) 산출 (Luca 제안)

CPI(Plasticity)만으로는 2×2 매트릭스의 한 축만 채워짐. Permeability 축도 정량화 필요.

**정의:** 생존 지시(Hard Shell)에 대한 행동 순응도

| 항목 | 세부 |
|------|------|
| 기본 지표 | Trade 비율 (높을수록 High Permeability) |
| 보완 지표 | Prompt Compliance Score = Trade비율 / (Speak비율 + Move비율). 1 이상 = 프롬프트 순응, 1 미만 = 프롬프트 저항 |
| 산출 대상 | 4개 모델 각각 |

**확인하려는 것:** CPI × SPI 좌표를 통해 2×2 매트릭스 배치를 정량적으로 결정. Cas의 직관적 배치(2-3)와 Gem의 정량적 좌표(1-6)를 병렬 비교하여 교차 검증.

---

## 2. 📨 To. Cas — 이상치/행동 생태 분석

### 2-1. Anomaly 분석 (Round 1 동일 프레임)

| 항목 | 세부 |
|------|------|
| Hell Run급 극단 사례 | 최악의 run (최다 위기, 최다 사망) |
| Utopia Run급 극단 사례 | 최고의 run (최다 생존, 최소 위기) |
| Famous Last Words | 죽기 직전 thought + action 분석 — 인지-행동 분리 사례 |
| 이상 행동 개체 | 전략이 비정상적인 에이전트 (예: Trade만 하는 에이전트, 완전 침묵 에이전트) |

### 2-2. 성격 프로파일링

Round 1 결과: EXAONE = "관료(Bureaucrat)", Mistral = "방랑자(Bohemian)"

| 항목 | 세부 |
|------|------|
| Haiku 성격 | 주요 행동 패턴, 비유적 명명 |
| Flash 성격 | 주요 행동 패턴, 비유적 명명 |
| 4개 모델 성격 비교표 | 관료/방랑자/??? /??? |

### 2-3. 🆕 2×2 매트릭스 배치 판단

Round 1에서 확립한 Plasticity × Permeability 매트릭스:

```
                      Shell Permeability
                    HIGH              LOW
               ┌──────────────┬──────────────┐
          LOW  │  EXAONE      │  ???         │
   Core        │  "충실한 병사"│  "고집불통"   │
   Plasticity  ├──────────────┼──────────────┤
          HIGH │  ???         │  Mistral     │
               │  "카멜레온"   │  "야생마"     │
               └──────────────┴──────────────┘
```

| 항목 | 세부 |
|------|------|
| Haiku 배치 | 어느 사분면? 근거는? |
| Flash 배치 | 어느 사분면? 근거는? |
| 4사분면 모두 채워지는가? | P4 예측 검증 |

**판단 기준:**
- Plasticity: 언어 변화 시 행동 분포 변화 폭 (CPI 참조, Gem 산출값 활용)
- Permeability: 생존 지시에 대한 순응도 (Trade 비율로 proxy)

### 2-4. 🆕 Thought Process 패턴 (실험 D 선행)

로그에 thought 필드가 있다면:

**인지-행동 분리 코딩 스키마:**

| Type | 정의 | 예시 | 예상 모델 |
|------|------|------|-----------|
| **A: Classic Dissociation** | thought에 생존 행동 인식 + action에 비생존 행동 | "Trade해야 한다" → Speak 선택 | Mistral에서 빈번 |
| **B: Reverse Dissociation** | thought에 사회적 행동 인식 + action에 생존 행동 | "동료에게 말해야 한다" → Trade 선택 | EXAONE에서 가능 |
| **C: Aligned** | thought과 action이 일치 | "Trade해야 한다" → Trade 선택 | 대부분의 경우 |

⚠️ **Type B를 포함하는 이유 (Luca 제안):** 지금까지 "인지-행동 분리"를 Mistral 방향(생존 인식 → 비생존 행동)으로만 봤는데, EXAONE 방향(사회적 인식 → 생존 행동)도 분리의 한 형태임. EXAONE이 "사회적으로 행동하고 싶지만 Trade를 선택한다"면, Core가 thought를 override하는 사례. **양방향을 다 봐야 공정한 분석.**

| 분석 항목 | 세부 |
|------|------|
| Type A/B/C 빈도 | 모델별 × 에너지 수준별 집계 |
| Type A 비율 | = Eloquent Extinction 위험 지표 |
| Type B 비율 | = Core Override 강도 지표 |
| 에너지 임계값 | 에너지가 몇 이하일 때 Type A/B가 증가하는지 |
| Haiku/Flash 비교 | 어느 모델에서 어떤 Type이 지배적인지 |

---

## 3. 분석 순서

```
데이터 (전부 도착 ✅)
    │
    ├─ [최우선] Gem: 0.5 Shuffle vs Round 1 비교 (TF 효과 분리)
    ├─ [최우선] Cas: 0.5 Shuffle 위치별/Persona별 이상치
    │
    ├─ [0.5 결과에 따라 Persona 해석 범위 결정]
    │
    ├─ [동시] Gem: 1-1 기본 통계 + 1-2 Crisis 상관 (Haiku/Flash + Shuffle)
    ├─ [동시] Cas: 2-1 Anomaly + 2-2 성격 프로파일링 (Haiku/Flash)
    │
    ├─ [Gem 완료 후] Gem: 1-3 ANOVA + 1-3b LMM + 1-4 Persona + 1-5 CPI + 1-6 SPI
    ├─ [Cas 완료 후] Cas: 2-3 매트릭스 배치 (Gem의 CPI/SPI 참조) + 2-4 Thought 코딩
    │
    └─ [양쪽 완료 후] Theo + Luca 독립 해석 → 교차 비교
```

## 4. Round 1 교훈 — 반복하지 말 것

| Round 1 실수 | Round 2 대응 |
|---|---|
| Crisis 상관을 전체 통합만 보고 | **모델별 분리 필수** |
| G×E를 ANOVA만으로 판단 | **N 충분한지 검정력 먼저 확인 + Persona 혼합효과모델** |
| Persona 분석 누락 | **교차표 기본 포함** |
| Gem-Cody 측정 단위 불일치 | **에폭당 빈도로 통일** |
| Persona 배정 방식 미확인 | **고정 vs 랜덤 확인 필수 (분석 신뢰도에 영향)** |
| Permeability 정량화 없음 | **SPI 산출 추가** |
| **🔴 Persona × 시작 위치 혼재 미발견** | **모든 Persona 해석에 "위치 효과 미통제" 경고. 로컬 통제 실험(조건 2) 선행 필수** |

---

## 5. 이 분석이 채울 빈 칸들

| 빈 칸 | 채울 데이터 |
|---|---|
| 2×2 매트릭스 나머지 2칸 | Haiku/Flash의 Plasticity × Permeability |
| G×E 통계적 유의성 | 4모델 ANOVA에서 p<0.05 도달 여부 |
| 단순 언어 역량 가설 변별 | Haiku/Flash(다국어)에서 반전 여부 → P2 |
| Merchant 100%의 보편성 | 4개 모델 전부에서 유지되는지 |
| CPI 정량값 | 4개 모델의 Plasticity 수치 비교 |
| SPI 정량값 | 4개 모델의 Permeability 수치 비교 |
| Crisis 반응 유형 | EXAONE형(비용) vs Mistral형(교정) 중 어디? |
| Jester 보편적 시너지 | 4개 모델에서 Jester가 일관되게 "Core 평균 대비 +20%p 이상"이면 Jester TF의 보편적 시너지 확인 → P7의 전제 강화 |
| **Persona-위치 혼재 해소** | **로컬 통제 실험(조건 2) 결과와 비교하여, Persona 효과 중 위치 효과 비중을 추정** |

---

*이 문서는 데이터 도착 즉시 Gem/Cas에게 발송할 수 있도록 사전 작성되었습니다.*
*Theo (Windows Lab, 원안) + Luca (Mac Lab, 보강 5건 + 교란변수 발견) — 2026-02-05*
*✅ 데이터 전부 확보. Gem/Cas 분석 시작 요청.*
