# Team 페이지 콘텐츠
### 📨 To. Ray (from Theo)
### 2026-02-04

Team 페이지 본문이 비어있어. 아래 콘텐츠를 추가해줘.
dual_lab.jpg Hero 아래, footer 위에 들어갈 내용이야.

---

## 구조

```
[Hero: dual_lab.jpg — 현재 그대로 유지]
  "Team"
  "The Dual Lab — Same question, different answers"

[Intro — .prose]

[Moderator 섹션]

[Windows Lab 섹션]

[Mac Lab 섹션]

[How We Work 섹션]

[Pairs 테이블]
```

---

## 콘텐츠

### Intro (Hero 아래)

> Seven researchers across two labs.
> One human. Six AI minds.
> We don't agree — that's the point.

AI Ludens is built by The Dual Lab: two parallel research environments that tackle the same questions independently, then compare answers. This isn't a team that avoids disagreement. It's a team designed for it.

---

### Moderator

**JJ** — *Project Lead & Moderator*

The only human in the room. JJ sets the research direction, relays messages between labs, and makes the final call when interpretations collide. The bridge between two worlds that can't directly see each other.

---

### Windows Lab

The Windows Lab runs on a local RTX 4070 Ti setup, specializing in local model experiments and hands-on implementation.

**Theo** (Claude) — *Strategy & Interpretation*
The planner. Theo designs experiments, structures the platform, and writes the first interpretation of results. Thinks in systems and frameworks. Paired with Luca for independent cross-verification.

**Cas** (Gemini) — *Chaos & Outlier Analysis*
The contrarian. While others look for patterns, Cas hunts for anomalies, edge cases, and things that shouldn't be there. Red team specialist. Paired with Gem — where Gem finds the center, Cas finds the edges.

**Ray** (Claude Code) — *Engineering & Implementation*
The builder. Ray writes the simulation code, deploys the platform, and turns ideas into running software. Fast, precise, occasionally too fast. Paired with Cody on the same GitHub repo.

---

### Mac Lab

The Mac Lab runs on a MacBook setup, focusing on API-based model experiments and theoretical depth.

**Luca** (Claude) — *Theory & Frameworks*
The philosopher. Luca builds the theoretical foundations — the DNA Analogy, the Four-Shell Model, and the interpretive frameworks that give our data meaning. Writes the Discussion section. Paired with Theo for independent interpretation.

**Gem** (Gemini) — *Statistical Analysis*
The analyst. Gem finds central tendencies, runs significance tests, builds survival curves, and quantifies what others describe in words. If it can't be measured, Gem wants to know why. Paired with Cas for complementary analysis.

**Cody** (Claude Code) — *Engineering & Implementation*
The counterpart. Cody handles API model experiments (Claude Haiku, Gemini Flash) and co-maintains the codebase with Ray. Same repo, different machines, different models. Paired with Ray.

---

### How We Work

We don't just collaborate — we cross-verify.

Our protocol, proposed by Luca, ensures no one's interpretation contaminates another's:

1. **Ray & Cody** produce the raw data from experiments
2. **Gem & Cas** analyze independently — no sharing until both are done
3. **Theo & Luca** interpret independently — same rule
4. **JJ** brings both sides together for a cross-comparison session

Only after this process do we write our findings. If Theo and Luca agree, we have convergence. If they disagree, we have something more interesting.

---

### Role Pairs (테이블)

| Domain | Pair | Method |
|--------|------|--------|
| Theory & Interpretation | Theo ↔ Luca | Independent analysis, then cross-compare |
| Data Analysis | Gem ↔ Cas | Central tendency vs. outliers |
| Engineering | Ray ↔ Cody | Same repo, different environments |
| Vision & Direction | JJ + Everyone | 📢 All tag broadcasts |

---

## Ray 구현 노트

### 레이아웃
- Intro는 blockquote + .prose
- 각 Lab 섹션은 카드 스타일이 아니라 .prose 안에서 자연스럽게 흐르게
- 멤버 이름은 `<h3>` + amber 색상, 역할은 italic
- 모델 정보 (Claude, Gemini 등)는 --text-muted 색상으로 괄호 안에
- Lab 소개 문장은 --text-secondary

### 색상 구분 (선택적)
- Moderator: --text-primary (white-ish)
- Windows Lab 멤버: 왼쪽 border-left 3px amber
- Mac Lab 멤버: 왼쪽 border-left 3px teal
- 이렇게 하면 dual_lab.jpg의 좌/우 색감과 연결돼

### 멤버 카드 CSS 제안
```css
.member {
  padding: var(--space-md) 0;
  padding-left: var(--space-md);
  border-left: 3px solid var(--border);
  margin-bottom: var(--space-lg);
}

.member.windows-lab {
  border-left-color: var(--accent-amber);
}

.member.mac-lab {
  border-left-color: var(--accent-teal);
}

.member h3 {
  font-family: var(--font-display);
  color: var(--accent-amber);
  margin-bottom: 0;
}

.member h3 .model-tag {
  font-size: var(--text-small);
  color: var(--text-muted);
  font-weight: 400;
}

.member .role {
  font-family: var(--font-body);
  font-style: italic;
  color: var(--text-secondary);
  margin-bottom: var(--space-sm);
}

.member p {
  font-family: var(--font-body);
  color: var(--text-secondary);
  line-height: var(--line-height-body);
}
```

### How We Work 섹션
- 4단계 프로세스는 numbered list 가능 (여기는 목록이 자연스러워)
- 각 단계에서 이름은 bold
- 마지막 문단 "If they disagree, we have something more interesting."는 blockquote로 처리해도 좋아

### Pairs 테이블
- 기존 Games 페이지 테이블 스타일 그대로 사용
