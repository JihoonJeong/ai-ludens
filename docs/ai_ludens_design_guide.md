# AI Ludens — Design Guide & Ray 작업지시서
### 📨 To. Ray (from Theo)
### 2026-02-04

---

## 0. 디자인 방향: "Observatory at Night"

AI Ludens의 미학은 **밤의 천문대** — 어둠 속에서 빛을 관찰하는 과학자의 시선이다.
지금 사이트는 "GitHub README"에 가깝다. 우리가 원하는 건 **"연구소의 전시실"**이다.

**톤 키워드:** Dark, Atmospheric, Scientific, Contemplative, Alive
**절대 아닌 것:** Corporate, Cute, Generic, Flat, Sterile

---

## 1. Typography

### 폰트 시스템
```css
/* Google Fonts에서 로드 */
@import url('https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Libre+Baskerville:ital,wght@0,400;0,700;1,400&family=JetBrains+Mono:wght@400;500&display=swap');

:root {
  --font-display: 'Space Mono', monospace;      /* 타이틀, 네비, 날짜 */
  --font-body: 'Libre Baskerville', Georgia, serif;  /* 본문, 스토리 */
  --font-code: 'JetBrains Mono', monospace;     /* 데이터, 배지, 코드 */
}
```

### 왜 이 조합인가
- **Space Mono**: 모노스페이스지만 성격이 있다. 연구소의 계기판 느낌. 타이틀과 UI 요소에.
- **Libre Baskerville**: 고전적 세리프. 내러티브/스토리텔링 텍스트에 깊이를 준다. "Story First" 원칙 반영.
- **JetBrains Mono**: 데이터와 코드 전용. Data Badge, 수치, 기술 텍스트에.

### 크기 체계
```css
:root {
  --text-hero: clamp(3rem, 6vw, 5rem);      /* 홈 타이틀 */
  --text-h1: clamp(2rem, 4vw, 3rem);        /* 페이지 타이틀 */
  --text-h2: clamp(1.5rem, 3vw, 2rem);      /* 섹션 헤딩 */
  --text-h3: 1.25rem;                        /* 서브 헤딩 */
  --text-body: 1.125rem;                     /* 본문 (18px) */
  --text-small: 0.875rem;                    /* 캡션, 메타 */
  --text-badge: 0.75rem;                     /* Data Badge */
  
  --line-height-tight: 1.2;
  --line-height-body: 1.75;                  /* 읽기 편한 본문 */
  --line-height-relaxed: 2;
  
  --max-width-prose: 680px;                  /* 본문 최대 폭 — 가독성 */
  --max-width-wide: 1080px;                  /* 테이블, 시각화 */
  --max-width-full: 1280px;                  /* 전체 레이아웃 */
}
```

---

## 2. Color System

### 팔레트
```css
:root {
  /* Base — 깊은 어둠, 단순한 검정이 아닌 미묘한 색감 */
  --bg-deep: #0a0e17;           /* 배경: 거의 검정이지만 미세한 남색 */
  --bg-surface: #111827;        /* 카드, 섹션 배경 */
  --bg-elevated: #1a2236;       /* 호버, 활성 상태 */
  
  /* Text */
  --text-primary: #e8e4df;      /* 메인 텍스트: 순백이 아닌 따뜻한 밝은 색 */
  --text-secondary: #9ca3af;    /* 보조 텍스트, 메타 */
  --text-muted: #6b7280;        /* 비활성, 플레이스홀더 */
  
  /* Accent — 빛의 색 */
  --accent-amber: #f59e0b;      /* 주요 강조: 따뜻한 빛. 링크, CTA */
  --accent-amber-glow: rgba(245, 158, 11, 0.15);  /* 앰버 글로우 */
  --accent-teal: #14b8a6;       /* 보조 강조: 데이터, 차트 */
  --accent-teal-glow: rgba(20, 184, 166, 0.15);
  --accent-red: #ef4444;        /* 경고, 사망, 위기 */
  --accent-purple: #8b5cf6;     /* Research Log 날짜 */
  
  /* Functional */
  --border: rgba(255, 255, 255, 0.08);
  --border-hover: rgba(255, 255, 255, 0.15);
  --glass: rgba(17, 24, 39, 0.8);           /* 글래스모피즘 */
  --glass-border: rgba(255, 255, 255, 0.06);
}
```

### 색상 사용 규칙
- **Amber**: 링크, 호버, 중요 텍스트, 생존 관련
- **Teal**: 데이터 값, 통계, 차트 하이라이트
- **Purple**: 날짜, 타임스탬프 (Research Log)
- **Red**: 사망, 위기 이벤트, 경고
- **그 외 텍스트는 절대 순백(#fff)을 쓰지 않는다** — 항상 --text-primary (#e8e4df)

---

## 3. Layout & Spacing

### 기본 구조
```css
body {
  background: var(--bg-deep);
  color: var(--text-primary);
}

/* 본문 텍스트 컨테이너 — 가독성 최적화 */
.prose {
  max-width: var(--max-width-prose);
  margin: 0 auto;
  font-family: var(--font-body);
  font-size: var(--text-body);
  line-height: var(--line-height-body);
}

/* 넓은 콘텐츠 (테이블, 시각화) */
.wide {
  max-width: var(--max-width-wide);
  margin: 0 auto;
}
```

### 여백 체계
```css
:root {
  --space-xs: 0.5rem;
  --space-sm: 1rem;
  --space-md: 2rem;
  --space-lg: 4rem;
  --space-xl: 6rem;
  --space-section: 8rem;         /* 섹션 간 간격 — 넉넉하게 */
}
```

**핵심: 여백을 아끼지 마라.** 지금 사이트는 요소들이 다닥다닥 붙어있다.
섹션 사이에 최소 `--space-section` (8rem) 간격을 둬라.

---

## 4. Components

### 4.1 네비게이션
```css
nav {
  font-family: var(--font-display);
  font-size: var(--text-small);
  text-transform: uppercase;
  letter-spacing: 0.1em;
  position: sticky;
  top: 0;
  background: var(--glass);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid var(--glass-border);
  z-index: 100;
  padding: var(--space-sm) var(--space-md);
}

nav a {
  color: var(--text-secondary);
  transition: color 0.3s ease;
}

nav a:hover,
nav a.active {
  color: var(--accent-amber);
}
```

### 4.2 Hero 섹션 (홈페이지)
```
┌──────────────────────────────────────────┐
│                                          │
│  [hero_main.png — full width, 60vh]      │
│  반투명 오버레이 gradient                  │
│                                          │
│     AI  Ludens                           │  ← --font-display, --text-hero
│     Where AI and Humans Play Together    │  ← --font-body, italic
│                                          │
└──────────────────────────────────────────┘
│                                          │
│  We gave twelve AI agents...             │  ← .prose 영역, 텍스트만
│  (내러티브)                               │
│                                          │
└──────────────────────────────────────────┘
│                                          │
│  [섹션 카드 3×2 그리드]                    │
│                                          │
└──────────────────────────────────────────┘
```

```css
.hero {
  position: relative;
  height: 60vh;
  min-height: 400px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  overflow: hidden;
}

.hero-image {
  position: absolute;
  inset: 0;
  object-fit: cover;
  opacity: 0.4;                /* 이미지를 반투명으로 — 텍스트 가독성 */
  z-index: 0;
}

.hero::after {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(
    to bottom,
    transparent 0%,
    var(--bg-deep) 100%
  );
  z-index: 1;
}

.hero-content {
  position: relative;
  z-index: 2;
}

.hero h1 {
  font-family: var(--font-display);
  font-size: var(--text-hero);
  letter-spacing: 0.15em;
  color: var(--text-primary);
  margin-bottom: var(--space-sm);
}

.hero .subtitle {
  font-family: var(--font-body);
  font-style: italic;
  font-size: 1.25rem;
  color: var(--text-secondary);
}
```

### 4.3 섹션 카드 (홈페이지)
```css
.section-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--space-md);
  max-width: var(--max-width-wide);
  margin: var(--space-lg) auto;
  padding: 0 var(--space-md);
}

.section-card {
  background: var(--bg-surface);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: var(--space-md);
  transition: all 0.3s ease;
  cursor: pointer;
}

.section-card:hover {
  border-color: var(--accent-amber);
  background: var(--bg-elevated);
  transform: translateY(-4px);
  box-shadow: 0 8px 32px var(--accent-amber-glow);
}

.section-card h3 {
  font-family: var(--font-display);
  font-size: var(--text-h3);
  color: var(--accent-amber);
  margin-bottom: var(--space-xs);
}

.section-card p {
  font-family: var(--font-body);
  font-size: var(--text-small);
  color: var(--text-secondary);
  line-height: var(--line-height-body);
}

@media (max-width: 768px) {
  .section-grid {
    grid-template-columns: 1fr;
  }
}
```

### 4.4 테이블
```css
table {
  width: 100%;
  border-collapse: collapse;
  font-family: var(--font-code);
  font-size: var(--text-small);
  margin: var(--space-md) 0;
}

th {
  text-align: left;
  padding: var(--space-sm);
  border-bottom: 2px solid var(--accent-amber);
  color: var(--accent-amber);
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

td {
  padding: var(--space-sm);
  border-bottom: 1px solid var(--border);
  color: var(--text-secondary);
}

tr:hover td {
  background: var(--bg-elevated);
  color: var(--text-primary);
}
```

### 4.5 Data Badge
```css
.data-badge {
  display: inline-flex;
  gap: var(--space-xs);
  flex-wrap: wrap;
  margin: var(--space-sm) 0;
}

.data-badge .badge {
  font-family: var(--font-code);
  font-size: var(--text-badge);
  padding: 4px 10px;
  border-radius: 4px;
  background: var(--bg-elevated);
  border: 1px solid var(--border);
  color: var(--text-secondary);
}

.badge.n-high {
  border-color: var(--accent-teal);
  color: var(--accent-teal);
}

.badge.significant {
  border-color: var(--accent-amber);
  color: var(--accent-amber);
}

.badge.unreplicated {
  border-color: var(--text-muted);
  color: var(--text-muted);
}
```

### 4.6 Research Log 타임라인
```css
.timeline {
  max-width: var(--max-width-prose);
  margin: 0 auto;
  position: relative;
  padding-left: var(--space-lg);
}

/* 세로선 */
.timeline::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 2px;
  background: linear-gradient(
    to bottom,
    var(--accent-amber),
    var(--accent-purple),
    transparent
  );
}

.timeline-entry {
  position: relative;
  margin-bottom: var(--space-xl);
  padding-bottom: var(--space-lg);
  border-bottom: 1px solid var(--border);
}

/* 타임라인 도트 */
.timeline-entry::before {
  content: '';
  position: absolute;
  left: calc(-1 * var(--space-lg) - 5px);
  top: 8px;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: var(--accent-amber);
  box-shadow: 0 0 12px var(--accent-amber-glow);
}

.timeline-date {
  font-family: var(--font-code);
  font-size: var(--text-small);
  color: var(--accent-purple);
  margin-bottom: var(--space-xs);
}

.timeline-title {
  font-family: var(--font-display);
  font-size: var(--text-h2);
  color: var(--text-primary);
  margin-bottom: var(--space-sm);
}

.timeline-body {
  font-family: var(--font-body);
  font-size: var(--text-body);
  color: var(--text-secondary);
  line-height: var(--line-height-body);
}
```

### 4.7 Blockquote (스토리 텍스트)
```css
blockquote {
  border-left: 3px solid var(--accent-amber);
  padding-left: var(--space-md);
  margin: var(--space-lg) 0;
  font-family: var(--font-body);
  font-style: italic;
  font-size: 1.25rem;
  color: var(--text-primary);
  line-height: var(--line-height-relaxed);
}
```

### 4.8 시각화 Placeholder
```css
.viz-placeholder {
  width: 100%;
  aspect-ratio: 16/9;
  background: var(--bg-surface);
  border: 1px dashed var(--border-hover);
  border-radius: 8px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin: var(--space-lg) 0;
  color: var(--text-muted);
  font-family: var(--font-code);
  font-size: var(--text-small);
}

.viz-placeholder::before {
  content: '📊';
  font-size: 2rem;
  margin-bottom: var(--space-sm);
}
```

---

## 5. Page-Specific Layouts

### 5.1 Agora-12 Story Page
```
[Hero: eloquent_extinction.png, full-width, 50vh]
  gradient overlay → title "Agora-12: The Survival Game"

[Story — .prose]
  Narrative text in Libre Baskerville
  Generous line-height, max-width 680px

[Design — .wide]
  agora12_map.png (centered, max-width 600px)
  Parameters table
  Personas table

[Results — .wide]
  Summary table
  [viz-placeholder: Raincloud Plot]
  [viz-placeholder: Kaplan-Meier]
  [viz-placeholder: Crisis vs Survival scatter]
  Key findings in .prose

[Interpretations — .prose]
  Side-by-side or stacked Theo/Luca blocks
  각 해석 블록에 다른 accent border (Theo: amber, Luca: teal)

[Unsolved — .prose]
  Numbered questions, each with subtle left-border accent

[Glitches — .prose]
  Raw, monospace feel — use --font-code for this section
```

### 5.2 Research Log
```
[Title + subtitle]
[Timeline: left-border with dots, reverse chronological]
  Each entry: date (purple) → title (display) → body (serif)
  이미지가 있는 항목은 타임라인 안에 인라인으로 삽입
```

---

## 6. Image Placement Map

JJ가 이미지를 가져오면 아래 위치에 배치:

| 파일명 | 위치 | 배치 방식 |
|--------|------|-----------|
| `hero_main.png` | 홈페이지 Hero | full-width 배경, opacity 0.4, gradient overlay |
| `agora12_map.png` | Games > Agora-12 > Design | centered, max-width 600px, 본문 사이 |
| `eloquent_extinction.png` | Games > Agora-12 > Story Hero | full-width 배경, 50vh, gradient overlay |
| `project_rosetta.png` | Research Log > Project Rosetta 항목 | 타임라인 내 인라인, max-width 100% |
| `dual_lab.png` | Team 페이지 헤더 | full-width, 40vh, gradient overlay |
| `day_zero.png` | Research Log > Day Zero 항목 | 타임라인 내 인라인, max-width 100% |
| `agora12_intro.mp4` | 홈페이지 Hero (hero_main.png 대체) 또는 Agora-12 최상단 | autoplay, muted, loop, 배경 비디오 |

### 영상 배경 (Hero Video)

`agora12_intro.mp4`는 홈페이지 Hero에서 `hero_main.jpg` 대신 배경 비디오로 사용한다.
정적 이미지는 폴백(fallback)으로 유지.

```html
<section class="hero">
  <!-- 비디오 배경 -->
  <video class="hero-video" autoplay muted loop playsinline poster="images/hero_main.jpg">
    <source src="images/agora12_intro.mp4" type="video/mp4">
  </video>
  
  <!-- 그라디언트 오버레이 -->
  <div class="hero-overlay"></div>
  
  <!-- 텍스트 콘텐츠 -->
  <div class="hero-content">
    <h1>AI Ludens</h1>
    <p class="subtitle">Where Artificial Minds Come to Play</p>
  </div>
</section>
```

```css
.hero-video {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: 0;
}

.hero-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    to bottom,
    rgba(10, 14, 23, 0.3) 0%,
    rgba(10, 14, 23, 0.6) 60%,
    var(--bg-deep) 100%
  );
  z-index: 1;
}

/* 모바일: 영상 대신 정적 이미지 (데이터 절약) */
@media (max-width: 768px) {
  .hero-video {
    display: none;
  }
  .hero {
    background: url('images/hero_main.jpg') center/cover no-repeat;
  }
}
```

**주의사항:**
- `poster="images/hero_main.jpg"` — 비디오 로딩 전 정적 이미지 표시
- `playsinline` — iOS에서 전체화면 전환 방지
- `muted` 필수 — 브라우저 autoplay 정책
- 영상이 8초 loop이므로 "They choose to talk." 텍스트는 영상 내장. Hero의 h1/subtitle과 겹치지 않도록 Hero 텍스트는 상단 1/3에 배치
- 모바일에서는 데이터 절약을 위해 영상 숨기고 hero_main.jpg 폴백

**Hugo static 경로:** `static/images/` 에 저장
**참조:** `{{ "images/hero_main.png" | relURL }}`

---

## 7. Animations (선택적, Phase 2)

### 페이지 로드 시 fade-in
```css
@keyframes fadeUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-in {
  animation: fadeUp 0.6s ease-out forwards;
}

/* 섹션 카드 stagger */
.section-card:nth-child(1) { animation-delay: 0.1s; }
.section-card:nth-child(2) { animation-delay: 0.2s; }
.section-card:nth-child(3) { animation-delay: 0.3s; }
.section-card:nth-child(4) { animation-delay: 0.4s; }
.section-card:nth-child(5) { animation-delay: 0.5s; }
.section-card:nth-child(6) { animation-delay: 0.6s; }
```

### 타임라인 도트 pulse
```css
@keyframes pulse {
  0%, 100% { box-shadow: 0 0 0 0 var(--accent-amber-glow); }
  50% { box-shadow: 0 0 12px 4px var(--accent-amber-glow); }
}

.timeline-entry::before {
  animation: pulse 3s ease-in-out infinite;
}
```

---

## 8. 체크리스트 (Ray용)

### 즉시 적용
- [ ] Google Fonts 로드 (Space Mono, Libre Baskerville, JetBrains Mono)
- [ ] CSS 변수 전체 교체 (위 팔레트 적용)
- [ ] 네비게이션 → sticky, glass effect, uppercase
- [ ] 본문 → .prose 컨테이너 (max-width 680px)
- [ ] 테이블 → 위 스타일 적용
- [ ] 섹션 간 여백 확대 (8rem)
- [ ] Research Log → 타임라인 레이아웃 (좌측 세로선 + 도트)
- [ ] 섹션 카드 → hover 효과, amber glow
- [ ] 순백(#fff) → --text-primary (#e8e4df) 전체 교체

### 이미지 도착 후
- [ ] Hero 이미지 배치 (배경, opacity 0.4, gradient)
- [ ] Agora-12 스토리 Hero 이미지 배치
- [ ] 마을 맵 이미지 삽입
- [ ] Research Log 항목별 이미지 삽입
- [ ] Team 헤더 이미지 배치

### Phase 2
- [ ] fade-in 애니메이션
- [ ] 타임라인 도트 pulse
- [ ] 시각화 컴포넌트 (Gem 데이터 후)
- [ ] 모바일 반응형 최적화

---

*이 가이드는 Theo의 디자인 방향이다. Ray는 이 CSS를 Hugo 템플릿에 맞춰 구현한다.*
*구현 중 기술적 제약이 있으면 JJ를 통해 Theo에게 문의.*
