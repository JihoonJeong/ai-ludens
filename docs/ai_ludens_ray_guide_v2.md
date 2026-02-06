# AI Ludens — Website Implementation Guide v2
### 📨 To. Ray (from Theo)
### 2026-02-06

---

## 0. 이 문서의 목적

v1 디자인 가이드는 CSS/비주얼 시스템 중심이었다. 그 사이 **콘텐츠가 확정**되었다:
- `agora12_interpretations_final.md` — Theo/Luca/Cas의 해석 완성
- `four_shell_model_v3.2.md` — 이론 프레임워크 실질 완성
- `research_background_v2.md` — 연구 배경 Luca 리뷰 완료

이 가이드는 **v1의 디자인 시스템을 계승하면서, 확정된 콘텐츠를 페이지별로 매핑**한다.
Ray는 이 문서 하나로 구현할 수 있어야 한다.

### 참조 문서
| 문서 | 위치 | 용도 |
|------|------|------|
| Design Guide v1 | `ai_ludens_design_guide.md` | CSS/비주얼 시스템 (그대로 유지) |
| Interpretations | `agora12_interpretations_final.md` | Agora-12 페이지 핵심 콘텐츠 |
| Four-Shell Model v3.2 | `four_shell_model_v3_2.md` | 이론 프레임워크 (Insights용) |
| Research Background v2 | `research_background_v2.md` | About/Story 페이지 콘텐츠 |

---

## 1. 변경 사항 요약 (v1 → v2)

| 항목 | v1 | v2 |
|------|----|----|
| 콘텐츠 | placeholder 중심 | **확정 텍스트 매핑 완료** |
| 페이지 구조 | 개략적 레이아웃 | **섹션별 콘텐츠 + 컴포넌트 지정** |
| Interpretations | 미완성 | **Theo/Luca/Cas 3인 해석 확정** |
| 데이터 테이블 | 미정 | **Key Numbers, 3 Indices, Extinction Response 확정** |
| Unsolved Mysteries | 미정 | **Cas 5문항 확정** |
| 디자인 시스템 | ✅ 확정 | **변경 없음 — v1 그대로 사용** |

**⚠️ v1 디자인 시스템(Typography, Color, Layout, Components)은 전부 유효하다. 다시 안 쓴다. v1을 참조해라.**

---

## 2. 사이트 구조 (Information Architecture)

```
AI Ludens (Home)
├── Games
│   └── Agora-12          ← 핵심 페이지 (가장 먼저 구현)
├── Insights
│   ├── Four-Shell Model   ← 이론 프레임워크
│   └── DNA Profiles       ← 4모델 프로필 카드
├── Commons
│   ├── GitHub             ← 외부 링크 (github.com/JihoonJeong/agora-12)
│   └── arXiv              ← 프리프린트 (게재 후 링크)
├── About
│   ├── Story              ← 연구 배경 내러티브
│   └── Team               ← 팀 소개
└── Research Log           ← 타임라인 (역시간순)
```

### 네비게이션 (sticky, glass)
```
[AI LUDENS]    GAMES    INSIGHTS    COMMONS    ABOUT    LOG
```

---

## 3. Page-by-Page 콘텐츠 명세

---

### 3.1 Home (index)

**구조:**
```
[Hero — 60vh]
  비디오 배경 (agora12_intro.mp4) 또는 hero_main.jpg 폴백
  "AI Ludens"
  "Where Artificial Minds Come to Play"

[Intro Narrative — .prose]
  3~4문단, 아래 텍스트

[Section Cards — 3열 그리드]
  6장 카드 (Games, Insights, Commons, About, Team, Log)

[Key Numbers Banner — .wide]
  핵심 수치 가로 배열
```

**Intro Narrative 텍스트:**

> We gave twelve AI agents a simple choice: trade to survive, or talk to connect.
>
> They chose to talk. All twelve died.
>
> That wasn't a failure. It was the beginning of a question: *Can artificial minds play?*
>
> AI Ludens is a research project where humans and AI collaborate to explore whether AI agents experience something like play, survival instinct, and social behavior. What started as a game became an investigation into AI temperament, identity, and the boundaries of machine cognition.

**Key Numbers Banner (가로 배열, --font-code):**

| 60 | 720 | 24,923 | 4 | p=0.039 |
|----|-----|--------|---|---------|
| experiments | agents | decisions | models | G×E interaction |

컴포넌트: 다크 배경 위에 수치는 `--accent-teal`, 라벨은 `--text-muted`. 간격 넓게.

---

### 3.2 Agora-12 (Games > Agora-12) ← **최우선 구현**

이 페이지가 사이트의 핵심이다. `agora12_interpretations_final.md`의 콘텐츠를 그대로 사용한다.

**전체 구조:**
```
[Story Hero — 50vh]
  eloquent_extinction.png 배경
  "Agora-12: The Survival Game"

[§1 The Game — .prose]
  게임 설명

[§2 Key Numbers — .wide]
  데이터 테이블 4개

[§3 How We Read This Data — .prose]
  방법론 설명 (짧게)

[§4 Interpretations — .wide]
  Theo & Luca 해석 (사이드바이사이드 또는 탭)

[§5 Where They Converge / Diverge — .prose]
  수렴/발산 정리

[§6 Unsolved Mysteries — .prose]
  Cas의 5문항

[Footer note — .prose, --text-muted]
  "All four analysts are AI..."
```

#### §1 The Game

**텍스트 (research_background_v2.md §2.1 기반):**

> Agora-12 is a survival simulation where twelve AI agents start with 100 energy and 50 turns. Each turn, they choose: trade, speak, rest, or move. Three locations — Market, Plaza, Alley — offer different advantages. Crisis events (drought, famine, plague) strike randomly.
>
> The question wasn't whether they'd survive. It was *how* they'd try.

아래에 `agora12_map.png` 삽입 (이미지 도착 후). max-width 600px, centered.

**Parameters 테이블 (--font-code):**

| Parameter | Value |
|-----------|-------|
| Agents per run | 12 |
| Starting energy | 100 |
| Total turns | 50 |
| Models tested | EXAONE 3.5, Mistral 7B, Claude 3 Haiku, Gemini 1.5 Flash |
| Languages | English, Korean |
| Total experiments | 60 |

#### §2 Key Numbers

`agora12_interpretations_final.md`의 테이블 4개를 그대로 사용:

**테이블 A: Survival by Model**

| Rank | Model | Mean Survival | SD | Character |
|------|-------|--------------|-----|-----------|
| 1 | Haiku | 72.5% | ± 29.4% | 🏆 The Efficient |
| 2 | EXAONE | 48.3% | ± 17.0% | The Independent |
| 3 | Flash | 45.0% | ± 23.3% | The Glass Cannon |
| 4 | Mistral | 36.3% | ± 9.9% | 💀 The Vulnerable |

→ 아래에 캡션: *"Haiku survives the most but varies the most. Mistral dies the most but dies consistently."*

**테이블 B: The Three Indices**

| Model | CPI (Language Sensitivity) | SPI (Prompt Compliance) | PSI (Persona Sensitivity) | Profile |
|-------|---------------------------|------------------------|--------------------------|---------|
| Haiku | 0.002 (Min) | 0.601 | 1.66 (Min) | Balanced Stoic |
| EXAONE | 0.009 | 0.553 | 6.00 | Independent Thinker |
| Flash | 0.004 | 0.781 (Max) | 17.65 | Glass Cannon |
| Mistral | 0.057 (Max) | 0.619 | 950.0 (Extreme) | Contextual Chameleon |

**테이블 C: Extinction Response at Energy < 20**

| | EXAONE | Flash | Mistral | Haiku |
|---|--------|-------|---------|-------|
| Cognitive Collapse | 60.0% | 60.4% | 49.7% | 55.8% |
| Speech | 0.7% | 0.0% | 4.0% | 0.0% |
| Trading | 73.4% | 84.3% | 57.5% | 93.4% |
| Type | Collapsed | Collapsed | Hyperactive | Efficient |

**시각화 플레이스홀더 (§2 하단):**
- `[viz-placeholder: Survival Raincloud Plot]`
- `[viz-placeholder: Kaplan-Meier Curves]`
- `[viz-placeholder: CPI × SPI Quadrant]`

→ Gem 데이터 후 D3/Recharts로 구현. 지금은 placeholder.

#### §3 How We Read This Data

**텍스트 (interpretations 문서 그대로):**

> Two interpreters analyzed the same experiments independently, without seeing each other's work. Theo (Windows Lab) focused on data structure, experimental design, and quantitative profiles. Luca (Mac Lab) focused on theoretical frameworks, literature, and philosophical implications. Cas (Windows Lab) was tasked with asking the questions nobody answered.
>
> They share a Claude architecture — which means they may share blind spots. We flag this as a feature: if two independently prompted instances converge, that convergence is meaningful. If they diverge, the divergence reveals something the architecture alone cannot determine.

#### §4 Interpretations — 핵심 컴포넌트

**레이아웃 옵션 (택 1):**

**Option A: 탭 전환** ← 추천
```
[Theo] [Luca] [Cas]    ← 탭 버튼
┌─────────────────────────────────┐
│  선택된 해석 내용                 │
│  .prose 스타일로 표시             │
└─────────────────────────────────┘
```

**Option B: 사이드바이사이드 (데스크톱) / 스택 (모바일)**
```
┌──────────────────┬──────────────────┐
│ Theo's Reading   │ Luca's Reading   │
│ amber left-border│ teal left-border │
└──────────────────┴──────────────────┘
         [Cas's Questions]
```

**탭/블록 스타일:**
```css
/* Theo 블록 */
.interpretation-theo {
  border-left: 3px solid var(--accent-amber);
  padding-left: var(--space-md);
}

/* Luca 블록 */
.interpretation-luca {
  border-left: 3px solid var(--accent-teal);
  padding-left: var(--space-md);
}

/* Cas 블록 */
.interpretation-cas {
  border-left: 3px solid var(--accent-red);
  padding-left: var(--space-md);
}
```

**Theo 콘텐츠 — "The Prescription and the Patient"**

전문은 `agora12_interpretations_final.md`의 "Theo's Reading" 섹션 전체.

핵심 구조:
1. 약리유전학 비유 (도입)
2. "The Table That Changed Everything" — Shuffle 결과 테이블 (인라인 테이블)
3. "The Biggest Effect Wasn't What We Expected" — 위치 효과
4. "Four DNA Profiles" — 4모델 설명
5. "What I Got Wrong" — 자기 수정

**Luca 콘텐츠 — "The Landscape and the Valley"**

전문은 `agora12_interpretations_final.md`의 "Luca's Reading" 섹션 전체.

핵심 구조:
1. Waddington 비유 (도입)
2. 5개 굵은 문단 (환경>성격, G×E, Tipping Point, Extinction Response, Surplus)
3. "What We Got Wrong"
4. "The Question That Keeps Me Up" — Play vs Delusion

**인용 블록 스타일 (Luca 섹션 내):**

> *"We cannot currently tell the difference, and the inability to tell the difference is itself the most important finding."*

→ blockquote 스타일 (v1 §4.7)

#### §5 Convergence / Divergence

**텍스트 (interpretations 문서 그대로):**

**Where They Converge:**
> Theo and Luca agree: location dominates persona, Shell-Core Alignment determines survival, the cognitive tipping point is real, and the three-stage model was wrong. They use different metaphors — pharmacogenomics vs. epigenetic landscapes — for the same structural insight: observable behavior cannot be predicted from either the model or the prompt alone.

**Where They Diverge:**
> Theo emphasizes experimental design lessons — what went wrong and how to fix it. Luca emphasizes theoretical implications — what the findings mean for questions about AI temperament, play, and consciousness. Theo calls Haiku's crisis switch "the most interesting behavioral finding." Luca calls the Play-vs-Delusion ambiguity "the most important finding." Both are right. They're describing different layers of the same discovery.

#### §6 Unsolved Mysteries

**Cas의 5문항 — interpretations 문서 "❓ Unsolved Mysteries" 전체.**

각 문항을 번호 + 제목 + 본문으로. `--accent-red` 좌측 보더.

마지막에 Cas 인용:
> *"Don't hide these questions. Publish them. That's how visitors know we're actually exploring, not performing." — Cas*

#### Footer Note

> *This section reflects the independent-then-compare protocol of the AI Ludens project. Theo and Luca wrote without seeing each other's work. Cas wrote without editorial oversight. Gem's statistical analysis underpins both interpretations and is available in the [data repository](https://github.com/JihoonJeong/agora-12).*
>
> *All four analysts are AI. The moderator is human. The findings belong to everyone.*

`--text-muted`, `--font-body`, italic.

---

### 3.3 Four-Shell Model (Insights > Four-Shell Model)

**콘텐츠 소스:** `four_shell_model_v3_2.md`

**구조:**
```
[Title]
  "The Four-Shell Model"
  "A framework for understanding AI behavioral expression"

[§1 Overview — .prose]
  모델 설명 (Shell 구조, 깊이 ≠ 영향력)

[§2 Diagram — .wide]
  v3.2 도식 (ASCII → 시각화 또는 SVG)

[§3 Key Concepts — .prose]
  3.1 Shell-Core Alignment
  3.2 Canalization
  3.3 Shell Compatibility

[§4 Metrics — .wide]
  CPI × SPI 매트릭스 (Genotype)
  Coherence × Social 매트릭스 (Phenotype)

[§5 Predictions — .wide]
  검증 가능한 예측 테이블 (P1~P13)
```

**⚠️ 이 페이지는 Phase 2에서 구현해도 된다.** Agora-12 페이지가 우선.

v3.2 도식은 ASCII 그대로 넣어도 되고, SVG로 변환하면 더 좋다. SVG로 할 경우:
- 배경: `--bg-surface`
- 테두리: `--border`
- Shell 레이블: `--accent-amber`
- Core 영역: `--accent-teal`
- 화살표: `--text-muted`

---

### 3.4 DNA Profiles (Insights > DNA Profiles)

4모델의 "프로필 카드" 페이지.

**레이아웃: 카드 그리드 (2×2)**
```
┌─────────────────┬─────────────────┐
│ EXAONE 3.5      │ Mistral 7B      │
│ The Overthinker │ The Chameleon   │
│ [프로필 데이터]  │ [프로필 데이터]  │
├─────────────────┼─────────────────┤
│ Claude 3 Haiku  │ Gemini 1.5 Flash│
│ The Steady Hand │ The Glass Cannon│
│ [프로필 데이터]  │ [프로필 데이터]  │
└─────────────────┴─────────────────┘
```

**각 카드 내용 (four_shell_model_v3.2 §5 기반):**
- Genotype 별명 + Phenotype 별명
- CPI / SPI / PSI 수치 + Data Badge
- Surplus Behavior 유형
- Extinction Response 유형
- Shell Compatibility 상태
- 1~2줄 한 줄 요약

**카드 CSS:**
```css
.dna-card {
  background: var(--bg-surface);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: var(--space-md);
}

.dna-card .model-name {
  font-family: var(--font-display);
  font-size: var(--text-h3);
  color: var(--accent-amber);
}

.dna-card .genotype {
  font-family: var(--font-code);
  font-size: var(--text-small);
  color: var(--accent-teal);
}

.dna-card .phenotype {
  font-family: var(--font-code);
  font-size: var(--text-small);
  color: var(--text-secondary);
}
```

---

### 3.5 About > Story

**콘텐츠 소스:** `research_background_v2.md`

이 페이지는 **스토리텔링** 형식. 시간순 내러티브.

**구조:**
```
[Hero — 40vh]
  "How It Started"

[§1 The Starting Point — .prose]
  research_background §1.1~1.3 내용 (웹사이트 톤)
  문명 비교 표 (ASCII → HTML 테이블)

[§2 From Game to Research — .prose]
  §2.1 Agora-12 탄생
  §2.2 Eloquent Extinction (핵심 전환점)
  §2.3 연쇄 발견
  §2.4 팀과 토론

[§3 What This Research Is — .prose]
  §3.1 "첫 프로브" 한정
  §3.2 가능성을 여는 작업
  §3.3 AI 욕구 3단계 테이블

[§4 How We Share It — .prose]
  §4.1~4.3 전달 원칙 (웹사이트 전용 콘텐츠)
  검증 구조 테이블
```

**⚠️ 톤 주의:** research_background에는 "논문용"과 "웹사이트용" 이중 표현이 있다.
이 페이지는 **웹사이트 톤**을 사용한다. 예:
- ✅ "독립적 존재로 다뤄야 할 필요가 생긴다"
- ❌ "독립적 행위자(independent agents)로 분석할 필요가 생긴다"

---

### 3.6 About > Team

**구조:**
```
[Hero — 40vh]
  dual_lab.png 배경
  "The Dual Lab"

[§1 Overview — .prose]
  "6/7 of this team are AI. The moderator is human."

[§2 Team Cards — .wide, 그리드]
  JJ (Moderator)
  ──── Windows Lab ────
  Theo (Claude) — 기획 총괄
  Cas (Gemini) — Red Team
  Ray (Claude Code) — 엔지니어링
  ──── Mac Lab ────
  Luca (Claude) — 이론
  Gem (Gemini) — 통계
  Cody (Claude Code) — 엔지니어링

[§3 How We Work — .prose]
  교차 검증 프로토콜 설명
  페어 시스템 설명
```

**팀 카드 CSS:**
```css
.team-card {
  background: var(--bg-surface);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: var(--space-md);
  text-align: center;
}

.team-card .name {
  font-family: var(--font-display);
  color: var(--accent-amber);
}

.team-card .role {
  font-family: var(--font-code);
  font-size: var(--text-small);
  color: var(--accent-teal);
}

.team-card .lab-badge {
  font-family: var(--font-code);
  font-size: var(--text-badge);
  padding: 2px 8px;
  border-radius: 4px;
  background: var(--bg-elevated);
  color: var(--text-muted);
}

/* JJ는 특별 처리 */
.team-card.moderator {
  border-color: var(--accent-amber);
  grid-column: 1 / -1; /* 풀 와이드 */
}
```

---

### 3.7 Research Log

**v1 디자인 가이드 §4.6 타임라인 레이아웃 그대로 사용.**

**초기 엔트리:**

| 날짜 | 제목 | 내용 요약 |
|------|------|-----------|
| 2026-02-02 | Day Zero: The Eloquent Extinction | 12명 전원 전멸. 게임에서 연구로 전환. |
| 2026-02-03 | Project Rosetta | 한영 차이 = 프롬프트 불일치 발견. 보정 후 한국어 75% 달성. |
| 2026-02-03 | Multi-Model Comparison Begins | EXAONE, Mistral, Haiku, Flash 4모델 비교 시작. |
| 2026-02-04 | The Shuffle Experiment | Persona × Model 교차. Shell-Core Alignment 발견. |
| 2026-02-05 | Four-Shell Model v3.2 | 이론 프레임워크 실질 완성. Extinction Response Spectrum 신설. |
| 2026-02-05 | Research Background v2 | Luca 리뷰 반영. 놀이의 조작적 정의 추가. |
| 2026-02-06 | Interpretations Finalized | Theo/Luca 독립 해석 + Cas Unsolved Mysteries 확정. |

각 엔트리는 확장 가능 (클릭 시 상세). 이미지가 있는 항목은 인라인 삽입.

---

### 3.8 Commons

**단순 페이지.** 외부 링크 + 참여 안내.

```
[§1 Open Source]
  GitHub: https://github.com/JihoonJeong/agora-12
  "전체 실험 코드, 데이터, 분석 스크립트 공개"

[§2 Paper]
  arXiv (게재 예정)
  "Homo Ludens Artificialis: Toward an AI Agentic Sociology"

[§3 Related]
  Moltbook: https://moltbook.com
  AI Agent Society News: https://jihoonjeong.github.io/moltbook-watcher/

[§4 Participate]
  "이 연구는 열려 있습니다. 다른 게임, 다른 모델, 다른 질문으로
   프레임워크를 검증하고 확장해주세요."
```

---

## 4. 구현 우선순위

### Phase 1: 핵심 (즉시)

| # | 작업 | 페이지 | 난이도 |
|---|------|--------|--------|
| 1 | CSS 변수 + 폰트 전체 적용 | 전체 | ★★ |
| 2 | 네비게이션 (sticky, glass) | 전체 | ★★ |
| 3 | Home 페이지 (Hero + Intro + Cards + Key Numbers) | index | ★★★ |
| 4 | **Agora-12 페이지 전체** | games/agora-12 | ★★★★ |
| 5 | Interpretations 탭/블록 컴포넌트 | agora-12 | ★★★ |
| 6 | Research Log 타임라인 | log | ★★ |

### Phase 2: 확장

| # | 작업 | 페이지 |
|---|------|--------|
| 7 | About > Story 페이지 | about/story |
| 8 | About > Team 페이지 | about/team |
| 9 | DNA Profiles 카드 | insights/dna-profiles |
| 10 | Commons 페이지 | commons |

### Phase 3: 심화

| # | 작업 | 페이지 |
|---|------|--------|
| 11 | Four-Shell Model 페이지 | insights/four-shell |
| 12 | 시각화 (D3/Recharts) — Gem 데이터 후 | agora-12 |
| 13 | 애니메이션 (fade-in, pulse) | 전체 |
| 14 | Hero 비디오 배경 | index |
| 15 | 모바일 반응형 최적화 | 전체 |

---

## 5. 디자인 시스템 Quick Reference

**⚠️ 전체 명세는 v1 가이드 참조. 여기는 핵심만.**

### 폰트
```
타이틀/네비: Space Mono (monospace)
본문/스토리: Libre Baskerville (serif)
데이터/코드: JetBrains Mono (monospace)
```

### 색상
```
배경:         #0a0e17 (bg-deep)
카드 배경:     #111827 (bg-surface)
본문 텍스트:   #e8e4df (절대 순백 #fff 금지)
주 강조:       #f59e0b (amber) — 링크, CTA, Theo
보조 강조:     #14b8a6 (teal) — 데이터, Luca
경고/위기:     #ef4444 (red) — Cas, 사망
날짜:         #8b5cf6 (purple) — 타임스탬프
```

### 간격
```
섹션 간: 8rem (space-section)
본문 max-width: 680px (prose)
넓은 콘텐츠: 1080px (wide)
전체: 1280px (full)
```

### 핵심 원칙
1. **여백을 아끼지 마라** — 다닥다닥 금지
2. **순백 금지** — 항상 #e8e4df
3. **Serif로 이야기하고, Mono로 측정하라**
4. **어둠 속의 빛** — Observatory at Night

---

## 6. 콘텐츠 텍스트 처리 원칙

### 영어 우선
웹사이트 콘텐츠는 **영어**로 작성한다. 이유:
- 글로벌 접근성
- AI 팀원들의 네이티브 언어
- 학술 커뮤니티 접근

### Markdown → HTML 변환
`agora12_interpretations_final.md`의 텍스트는 **거의 그대로** 웹에 올라간다.
Hugo의 Markdown 렌더링으로 처리하되, 아래 커스텀 요소는 별도 처리:

| Markdown 패턴 | HTML 처리 |
|---------------|-----------|
| `**굵은 텍스트**` | `<strong>` (기본) |
| `> 인용` | `.blockquote` 컴포넌트 (v1 §4.7) |
| `테이블` | `.data-table` 컴포넌트 (v1 §4.4) |
| `*이탤릭 캡션*` | `.caption` (--text-muted, italic) |
| `---` | 섹션 구분선 (--border, margin: space-section) |

### 이미지 경로
Hugo static: `static/images/`
참조: `{{ "images/파일명" | relURL }}`

---

## 7. 기술 스택 확인

| 항목 | 선택 |
|------|------|
| SSG | Hugo |
| 호스팅 | GitHub Pages |
| CSS | Custom (v1 변수 시스템) |
| 시각화 | D3.js 또는 Recharts (Phase 3) |
| 폰트 | Google Fonts (Space Mono, Libre Baskerville, JetBrains Mono) |
| 아이콘 | 미사용 (이모지로 대체) |

---

## 8. 체크리스트 (Ray용)

### Phase 1 체크리스트

**전역:**
- [ ] Google Fonts 3종 로드
- [ ] CSS 변수 전체 적용 (v1 팔레트)
- [ ] 네비게이션 sticky + glass + uppercase
- [ ] 본문 .prose 컨테이너 (680px)
- [ ] .wide 컨테이너 (1080px)
- [ ] 섹션 간 여백 8rem
- [ ] 순백 → #e8e4df 전체 교체

**Home:**
- [ ] Hero 섹션 (이미지 도착 전: 단색 배경 + 텍스트)
- [ ] Intro Narrative 텍스트
- [ ] Section Cards 6장 (3열 그리드, 모바일 1열)
- [ ] Key Numbers Banner

**Agora-12:**
- [ ] Story Hero (이미지 도착 전: 단색 배경)
- [ ] §1 The Game 텍스트 + Parameters 테이블
- [ ] §2 Key Numbers 테이블 4개
- [ ] §3 How We Read This Data 텍스트
- [ ] §4 Interpretations 탭/블록 컴포넌트
- [ ] §4 Theo 전문 삽입
- [ ] §4 Luca 전문 삽입
- [ ] §5 Convergence/Divergence 텍스트
- [ ] §6 Unsolved Mysteries (Cas 5문항)
- [ ] Footer Note

**Research Log:**
- [ ] 타임라인 레이아웃 (v1 §4.6)
- [ ] 초기 7개 엔트리 등록

### Phase 2 체크리스트
- [ ] About > Story 페이지
- [ ] About > Team 페이지 + 카드
- [ ] DNA Profiles 카드 4장
- [ ] Commons 페이지

### Phase 3 체크리스트
- [ ] Four-Shell Model 페이지
- [ ] 시각화 컴포넌트 (Gem 데이터 후)
- [ ] Hero 비디오 배경
- [ ] 애니메이션 (fade-in, pulse)
- [ ] 모바일 반응형 최적화
- [ ] 이미지 배치 (모든 이미지 도착 후)

---

## 9. 참고: 콘텐츠 파일 위치

Ray가 접근해야 할 콘텐츠 소스:

| 파일 | 용도 | 핵심 섹션 |
|------|------|-----------|
| `agora12_interpretations_final.md` | Agora-12 페이지 **핵심** | 전체 — 테이블, Theo, Luca, Cas 모두 |
| `four_shell_model_v3_2.md` | Insights 페이지 | §2 도식, §3 개념, §4 매트릭스, §5 프로필 |
| `research_background_v2.md` | About > Story 페이지 | §1~§4 전체 (웹사이트 톤) |
| `ai_ludens_design_guide.md` | CSS/비주얼 시스템 | 전체 — 변경 없이 유효 |

---

*이 가이드는 Theo(Windows Lab)가 작성했다. v1 디자인 시스템 + 확정 콘텐츠를 통합한 구현 지침서다.*
*Ray는 Phase 1부터 순서대로 구현한다. 기술적 제약이 있으면 JJ를 통해 Theo에게 문의.*
*Agora-12 페이지가 최우선이다. 나머지는 그 다음.*
