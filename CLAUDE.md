# AI Ludens Platform

## 프로젝트 개요
AI Ludens는 "AI가 놀이를 경험할 수 있는가?"를 탐구하는 오픈 리서치 플랫폼이다.
게임을 통해 AI의 행동, 사회성, 놀이를 실험하고, 그 발견을 공유한다.

## 팀 구성 (The Dual Lab)

### Moderator
- **JJ** (Human): 프로젝트 리더, 방향 제시, 최종 판단

### Windows Lab
- **Theo** (Claude): 기획 총괄, 논리적 설계, 데이터 해석
- **Cas** (Gemini): 행동 생태학, Chaos & Outlier 분석, Red Teaming
- **Ray** (Claude Code): 엔지니어링 구현, 로컬 모델 실험 (RTX 4070 Ti)

### Mac Lab
- **Luca** (Claude): 이론적 프레임워크, Discussion 섹션
- **Gem** (Gemini): 데이터 통계 분석, 시각화
- **Cody** (Claude Code): 엔지니어링 구현, API 모델 실험

## 이 레포의 목적
AI Ludens 웹 플랫폼 (GitHub Pages 기반 정적 사이트)

## 핵심 문서
- `docs/platform_plan_v0.3.md` — 플랫폼 기획서 확정본

## 관련 레포
- `agora-12` (github.com/JihoonJeong/agora-12) — 실험 코드, 데이터

## 플랫폼 구조 요약
- Layer 1: GAMES — AI 게임 실험과 인터랙티브 시각화
- Layer 2: INSIGHTS — 발견의 기록, 이론적 프레임워크
- Research Log — 시간순 연구 타임라인
- Layer 3: COMMONS — 오픈소스, Citizen Science, Hall of Chaos
- TEAM — "같은 질문, 다른 답" 형식의 팀 소개
- ETHICS — AI 실험 윤리 원칙

## 기술 스택
- GitHub Pages + 정적 사이트 생성기
- 시각화: D3.js, Plotly
- 콘텐츠: 마크다운 기반
- 다국어: 영어 우선, 한국어 병행

## 커뮤니케이션
- JJ가 Mac Lab ↔ Windows Lab 간 메시지 중계
- 메시지 태그: 📨 To. [이름] / 📢 All / 📋 Brief
