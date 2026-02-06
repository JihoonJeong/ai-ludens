# AI Ludens 플랫폼 구축 리포트

## 📋 프로젝트 개요

**플랫폼**: AI Ludens 연구 웹사이트
**URL**: https://jihoonjeong.github.io/ai-ludens/
**저장소**: https://github.com/JihoonJeong/ai-ludens
**구축 기간**: 2026-02-04 ~ 2026-02-06
**구축자**: Ray (Claude Code, Windows Lab)

---

## 🛠 기술 스택

| 구성요소 | 기술 |
|----------|------|
| Static Site Generator | Hugo |
| 호스팅 | GitHub Pages |
| CI/CD | GitHub Actions |
| 스타일링 | Custom CSS (Design System) |
| 폰트 (EN) | Space Mono, Libre Baskerville, JetBrains Mono |
| 폰트 (KO) | Pretendard Variable, Noto Serif KR |
| 시각화 | HTML/JS (Plotly 기반), Static Images |

---

## 📁 디렉토리 구조

```
ai-ludens/
├── content/                    # 콘텐츠 (마크다운)
│   ├── _index.md              # 홈페이지 (EN)
│   ├── _index.ko.md           # 홈페이지 (KO)
│   ├── games/
│   │   ├── _index.md          # 게임 목록
│   │   └── agora-12/          # Agora-12 게임 페이지
│   ├── insights/              # 인사이트
│   ├── log/                   # 연구 로그 (타임라인)
│   ├── team/                  # 팀 소개
│   ├── commons/               # 오픈소스/커먼즈
│   └── ethics/                # 윤리 원칙
├── layouts/                   # Hugo 레이아웃 템플릿
│   ├── _default/
│   │   ├── baseof.html       # 기본 HTML 구조
│   │   ├── list.html         # 목록 페이지
│   │   └── single.html       # 단일 페이지
│   ├── games/
│   │   ├── section.html      # 게임 섹션
│   │   └── single.html       # 개별 게임 페이지
│   ├── log/
│   │   └── list.html         # 타임라인 레이아웃
│   ├── team/
│   │   └── list.html         # 팀 페이지 (hero 지원)
│   ├── commons/
│   │   └── list.html         # 커먼즈 페이지 (hero 지원)
│   └── index.html            # 홈페이지 레이아웃
├── static/
│   ├── css/
│   │   └── main.css          # 전체 스타일시트
│   └── images/               # 이미지 및 HTML 시각화
├── i18n/                     # 다국어 번역
│   ├── en.toml
│   └── ko.toml
└── hugo.toml                 # Hugo 설정
```

---

## 🎨 디자인 시스템 (Observatory at Night)

### 색상 팔레트

| 변수 | 값 | 용도 |
|------|-----|------|
| `--bg-deep` | `#0a0e17` | 메인 배경 |
| `--bg-surface` | `#111827` | 카드/섹션 배경 |
| `--bg-elevated` | `#1a2236` | hover 상태 |
| `--text-primary` | `#e8e4df` | 주요 텍스트 |
| `--text-secondary` | `#9ca3af` | 보조 텍스트 |
| `--accent-amber` | `#f59e0b` | 강조 (Windows Lab) |
| `--accent-teal` | `#14b8a6` | 강조 (Mac Lab) |
| `--accent-red` | `#ef4444` | 강조 (Cas/Red Team) |

### 주요 컴포넌트

#### 1. viz-card (인터랙티브 시각화)
```html
<div class="viz-card" id="viz-example">
  <div class="viz-image">
    <img src="/ai-ludens/images/example.jpg" alt="설명">
  </div>
  <div class="viz-interactive">
    <iframe src="/ai-ludens/images/example.html" loading="lazy"></iframe>
  </div>
  <div class="viz-card-footer">
    <span class="viz-card-caption">캡션</span>
    <button class="viz-toggle" onclick="toggleViz('viz-example')">Interactive</button>
  </div>
</div>

<script>
function toggleViz(id) {
  const card = document.getElementById(id);
  const btn = card.querySelector('.viz-toggle');
  card.classList.toggle('show-interactive');
  btn.classList.toggle('active');
  btn.textContent = card.classList.contains('show-interactive') ? 'Static' : 'Interactive';
}
</script>
```

#### 2. repo-card (GitHub 저장소)
```html
<div class="repo-card">
  <h3>프로젝트명</h3>
  <p>설명</p>
  <a href="URL" class="cta-button">View on GitHub →</a>
</div>
```

#### 3. content-image (인라인 이미지)
```html
<div class="content-image centered">
  <img src="/ai-ludens/images/example.jpg" alt="설명" loading="lazy">
  <div class="image-caption">캡션</div>
</div>
```

#### 4. interpretation 블록 (Theo/Luca/Cas)
```html
<div class="interpretation-theo">  <!-- 또는 interpretation-luca, interpretation-cas -->
  <h3>제목</h3>
  <p class="interpretation-author">Windows Lab — 역할</p>
  내용...
</div>
```

---

## 🌐 다국어 지원

### 파일 명명 규칙
- 영어: `_index.md`, `page-name.md`
- 한국어: `_index.ko.md`, `page-name.ko.md`

### i18n 키 사용
```toml
# i18n/ko.toml
[subtitle]
other = "AI와 인간이 함께 노는 곳"
```

```html
<!-- 템플릿에서 -->
{{ i18n "subtitle" }}
```

### URL 구조
- 영어: `/games/`, `/team/`
- 한국어: `/ko/games/`, `/ko/team/`

---

## 📝 콘텐츠 추가 가이드

### 새 로그 항목 추가
```markdown
---
title: "제목"
date: 2026-02-07
description: "한 줄 설명"
image: "images/example.jpg"  # 선택사항 (타임라인에 표시)
---

내용...
```

### 새 게임 추가
1. `content/games/game-name/` 디렉토리 생성
2. `_index.md` (EN) 및 `_index.ko.md` (KO) 작성
3. frontmatter에 `hero_image` 추가

```markdown
---
title: "게임명"
description: "설명"
hero_image: "images/game_hero.jpg"
---
```

---

## 🖼 이미지 및 시각화

### 현재 사용된 이미지/HTML

| 파일 | 사용 위치 |
|------|----------|
| `eloquent_extinction.jpg` | Agora-12 hero, 로그 |
| `agora12_map.jpg` + `agora12_game_map.html` | Agora-12 (토글) |
| `genotype_matrix_cpi_spi.jpg/.html` | Agora-12 (토글) |
| `shell_core_alignment.jpg/.html` | Agora-12 (토글), 로그 |
| `play_vs_delusion.jpg/.html` | Agora-12 (토글) |
| `origin_story.jpg/.html` | Day Zero 로그 (토글) |
| `cogitative_cascade_v3.2_art.jpg` + `diagram.html` | Research Background (토글) |
| `research_timeline.html` | 로그 인덱스 |
| `four_shell_model.png` | Four-Shell Model 로그 |
| `dna_profile_cards.png` | Agora-12 |
| `waddington_landscape.png` | Agora-12 |
| `haiku_neurotic_poet_silent_trader.jpg` | Agora-12 |
| `extinction_response_spectrum.png` | Agora-12 |
| `dual_lab.jpg` | Team hero, 로그 |
| `day_zero.jpg` | 로그 |
| `project_rosetta.jpg` | 로그 |
| `agora12_commons.jpg` | Commons hero |
| `agora12_story.jpg` | Agora-12 |
| `hero_main.jpg` | 홈페이지 hero |
| `agora12_intro.mp4` | 홈페이지 비디오 |

### 미사용 (예비)
- `agora12_map_minimal.jpg` (간소화 버전)

---

## 🚀 배포 워크플로우

1. 로컬에서 변경사항 작성
2. `git add` → `git commit` → `git push`
3. GitHub Actions 자동 빌드 (`.github/workflows/hugo.yml`)
4. GitHub Pages에 자동 배포

### 로컬 테스트 (Hugo 설치 필요)
```bash
hugo server -D
# http://localhost:1313/ai-ludens/ 에서 확인
```

---

## 🎮 White Room 프로젝트를 위한 권장사항

### 1. 새 게임 페이지 구조
```
content/games/white-room/
├── _index.md
├── _index.ko.md
└── (추가 섹션 페이지들)
```

### 2. 시각화 준비
- 정적 이미지 (`.jpg/.png`) + 인터랙티브 HTML (`.html`) 쌍으로 준비
- viz-card 컴포넌트로 토글 지원

### 3. 연구 로그 연동
- 실험 진행에 따라 `content/log/` 에 항목 추가
- 영문/한글 동시 작성 권장

### 4. 팀 협업
- Theo/Luca 해석은 `interpretation-theo`, `interpretation-luca` 클래스 사용
- Cas의 Red Team 분석은 `interpretation-cas` 클래스 사용

---

## 📞 문의

- **플랫폼 이슈**: GitHub Issues
- **콘텐츠 협업**: JJ (Moderator) 경유

---

*이 리포트는 Ray (Claude Code, Windows Lab)가 작성했습니다.*
*AI Ludens — The Dual Lab*
