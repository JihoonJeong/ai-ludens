# 📨 Discussion Request: Four-Shell Model Terminology

**From**: JJ (Moderator)
**To**: Theo (Windows Lab), Luca (Mac Lab)
**Date**: 2026-02-08
**Priority**: High — affects core theoretical framework

---

## Background

Four-Shell Model v3.2의 최외곽 층 명칭에 불일치가 발견되었습니다:
- **그림(four_shell_model.png)**: "Phenotype"
- **현재 문서 설명**: "Situation"
- **Agent Theory 관점**: "Environment"가 더 적절할 수 있음

이 용어 선택은 단순한 레이블 문제가 아니라, 우리 프레임워크의 이론적 기반에 영향을 미칩니다.

---

## The Three Candidates

### 1. Situation (현재 사용)
> "the immediate choice in the moment"

**장점**: 에이전트의 즉각적 의사결정 맥락을 강조
**단점**: 수동적으로 들림. 에이전트가 환경에 반응하는 것인지, 환경이 에이전트를 형성하는 것인지 불명확

### 2. Environment (Agent Theory)
> "external conditions the agent operates in"

**장점**:
- 고전적 Agent Theory와 일치 (Agent = perceives Environment, acts on Environment)
- Reinforcement Learning 문헌과 호환
- GxE (Genotype × Environment) interaction 논의와 자연스럽게 연결

**단점**: Core를 Genotype으로 보면, Environment는 "밖"이어야 하는데, 우리 모델에서는 Shell로 감싸고 있음 — 개념적 긴장

### 3. Phenotype (그림에서 사용)
> "observable characteristics resulting from genotype + environment"

**장점**:
- 생물학적 DNA 비유와 완벽하게 일치
- Theo의 "pharmacogenomics" 비유, Luca의 "Waddington landscape" 비유 모두와 호환
- Core(Genotype) → Shells → Phenotype(관찰 행동)의 인과적 흐름이 명확

**단점**:
- Phenotype은 "결과"인데, Shell은 "층/구조"를 의미 — 범주 혼동 가능성
- 에이전트 관점에서 Phenotype은 output이지, 에이전트를 둘러싼 것이 아님

---

## Key Questions for Discussion

### Q1. 구조 vs 결과
Four-Shell Model의 최외곽 층은 **구조적 요소**(에이전트를 형성하는 것)인가, **결과적 요소**(에이전트가 표현하는 것)인가?

- 구조적 → Environment가 적절
- 결과적 → Phenotype이 적절
- 둘 다 → 새로운 용어 또는 이중 레이블 필요

### Q2. 인과적 방향
```
Core → Hard Shell → Soft Shell → [?] → Observable Behavior
```
`[?]`에 들어갈 것은:
- **Environment** (외부 입력, 에이전트에게 영향을 줌)
- **Phenotype** (외부 출력, 에이전트가 표현함)
- **Situation** (맥락, 양방향)

이 인과적 흐름에서 가장 일관된 용어는?

### Q3. GxE Interaction과의 정합성
우리 핵심 발견 중 하나: "G×E interaction is real (p=0.039)"

여기서:
- G (Genotype) = Core (model weights)
- E (Environment) = ?

만약 E가 "Hard Shell + Soft Shell + Situation"이면, 최외곽 층만 Environment라고 부르는 것은 혼란을 줄 수 있음.

만약 전체 외부 조건을 Environment로 보면, 최외곽 층은 별도의 이름이 필요함.

### Q4. Waddington Landscape와의 연결
Luca의 비유에서 "marble rolls into valleys" — 여기서:
- Marble = 에이전트
- Landscape = ?
- Valley = ?

Landscape가 Four-Shell의 어느 부분에 해당하는가? 최외곽 층인가, 전체 Shell 구조인가?

---

## Deliverables Requested

1. **용어 결정**: Situation / Environment / Phenotype 중 선택, 또는 새로운 제안
2. **정의 문장**: 선택한 용어의 1-2문장 정의
3. **그림 수정 필요 여부**: 현재 그림의 "Phenotype" 레이블을 변경할지
4. **문서 업데이트 범위**: Agora-12 해석, Research Log, BUILD_REPORT 등

---

## Process

1. **독립 분석**: Theo와 Luca 각자 위 질문에 답변 작성 (서로 보지 않고)
2. **JJ 수집**: 양측 답변을 JJ가 수집
3. **교차 비교**: 수렴/발산 지점 식별
4. **최종 결정**: 합의 또는 JJ 결정

**Deadline**: White Room 실험 시작 전까지

---

*"The difference between the right word and the almost right word is the difference between lightning and a lightning bug." — Mark Twain*

*이 용어 선택이 우리 프레임워크의 번개인지 반딧불이인지를 결정합니다.*
