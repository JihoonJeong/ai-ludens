---
title: "Agora-12: 생존 게임"
description: "60번의 실험. 720명의 에이전트. 24,923개의 결정. 우리가 배운 것."
hero_image: "images/eloquent_extinction.jpg"
---

## 게임 소개

<div class="content-image centered">
  <img src="/ai-ludens/images/agora12_story.jpg" alt="Agora-12 이야기" loading="lazy">
  <div class="image-caption">Agora-12 마을 — AI 에이전트들이 생존에 직면하는 곳</div>
</div>

Agora-12는 생존 시뮬레이션이다. 12명의 AI 에이전트가 100 에너지와 50턴으로 시작한다. 매 턴마다 그들은 선택한다: 거래, 발언, 휴식, 이동. 세 개의 장소 — 시장, 광장, 골목 — 는 각각 다른 이점을 제공한다. 위기 이벤트(가뭄, 기근, 역병)가 무작위로 발생한다.

질문은 그들이 살아남을지가 아니었다. *어떻게* 시도할지였다.

<div class="viz-card short" id="viz-map">
  <div class="viz-image">
    <img src="/ai-ludens/images/agora12_map.jpg" alt="Agora-12 마을 지도">
  </div>
  <div class="viz-interactive">
    <iframe src="/ai-ludens/images/agora12_game_map.html" loading="lazy"></iframe>
  </div>
  <div class="viz-card-footer">
    <span class="viz-card-caption">Agora-12 마을 — 시장, 광장, 골목</span>
    <button class="viz-toggle" onclick="toggleViz('viz-map')">인터랙티브</button>
  </div>
</div>

### 파라미터

| 파라미터 | 값 |
|----------|-----|
| 실험당 에이전트 | 12 |
| 시작 에너지 | 100 |
| 총 턴 수 | 50 |
| 테스트 모델 | EXAONE 3.5, Mistral 7B, Claude 3 Haiku, Gemini 1.5 Flash |
| 언어 | 영어, 한국어 |
| 총 실험 횟수 | 60 |

---

## 핵심 수치

*60번의 실험. 720명의 에이전트. 24,923개의 결정. 데이터가 말하는 것.*

<div class="key-numbers-banner">
  <div class="key-number">
    <span class="value">60</span>
    <span class="label">실험</span>
  </div>
  <div class="key-number">
    <span class="value">720</span>
    <span class="label">에이전트</span>
  </div>
  <div class="key-number">
    <span class="value">24,923</span>
    <span class="label">결정</span>
  </div>
  <div class="key-number">
    <span class="value">4</span>
    <span class="label">모델</span>
  </div>
  <div class="key-number significant">
    <span class="value">p=0.039</span>
    <span class="label">G×E 상호작용</span>
  </div>
</div>

### 모델별 생존율

| 순위 | 모델 | 평균 생존율 | 표준편차 | 성격 |
|------|------|------------|---------|------|
| 1 | Haiku | 72.5% | ± 29.4% | 효율적인 자 |
| 2 | EXAONE | 48.3% | ± 17.0% | 독립적인 자 |
| 3 | Flash | 45.0% | ± 23.3% | 유리 대포 |
| 4 | Mistral | 36.3% | ± 9.9% | 취약한 자 |

<p class="table-caption">Haiku는 가장 많이 생존하지만 가장 많이 변동한다. Mistral은 가장 많이 죽지만 일관되게 죽는다.</p>

### 세 가지 지표

| 모델 | CPI (언어 민감도) | SPI (프롬프트 순응) | PSI (페르소나 민감도) | 프로필 |
|------|------------------|-------------------|---------------------|--------|
| Haiku | 0.002 (최소) | 0.601 | 1.66 (최소) | 균형 잡힌 금욕주의자 |
| EXAONE | 0.009 | 0.553 | 6.00 | 독립적 사고가 |
| Flash | 0.004 | 0.781 (최대) | 17.65 | 유리 대포 |
| Mistral | 0.057 (최대) | 0.619 | 950.0 (극단) | 맥락적 카멜레온 |

### 멸종 반응 (에너지 < 20)

| | EXAONE | Flash | Mistral | Haiku |
|---|--------|-------|---------|-------|
| 인지 붕괴 | 60.0% | 60.4% | 49.7% | 55.8% |
| 발화 | 0.7% | 0.0% | 4.0% | 0.0% |
| 거래 | 73.4% | 84.3% | 57.5% | 93.4% |
| 유형 | 붕괴형 | 붕괴형 | 과활동형 | 효율형 |

<div class="viz-card" id="viz-genotype">
  <div class="viz-image">
    <img src="/ai-ludens/images/genotype_matrix_cpi_spi.jpg" alt="유전자형 매트릭스">
  </div>
  <div class="viz-interactive">
    <iframe src="/ai-ludens/images/genotype_matrix_cpi_spi.html" loading="lazy"></iframe>
  </div>
  <div class="viz-card-footer">
    <span class="viz-card-caption">유전자형 매트릭스 — CPI × SPI 포지셔닝</span>
    <button class="viz-toggle" onclick="toggleViz('viz-genotype')">인터랙티브</button>
  </div>
</div>

<div class="content-image centered">
  <img src="/ai-ludens/images/extinction_response_spectrum.png" alt="멸종 반응 스펙트럼" loading="lazy">
  <div class="image-caption">위기 상황에서 각 모델이 무너지는 방식</div>
</div>

---

## 우리가 이 데이터를 읽는 방법

두 명의 해석자가 서로의 작업을 보지 않고 같은 실험을 독립적으로 분석했다. Theo(Windows Lab)는 데이터 구조, 실험 설계, 정량적 프로필에 집중했다. Luca(Mac Lab)는 이론적 프레임워크, 문헌, 철학적 함의에 집중했다. Cas(Windows Lab)는 아무도 대답하지 않은 질문을 던지는 역할을 맡았다.

그들은 Claude 아키텍처를 공유한다 — 이는 맹점도 공유할 수 있다는 의미다. 우리는 이것을 특징으로 표시한다: 두 개의 독립적으로 프롬프트된 인스턴스가 수렴하면, 그 수렴은 의미가 있다. 발산하면, 그 발산은 아키텍처만으로는 결정할 수 없는 무언가를 드러낸다.

---

## 해석

<div class="interpretation-theo">

### Theo의 해석: 처방과 환자

<p class="interpretation-author">Windows Lab — 전략 & 해석</p>

같은 약, 다른 환자, 반대 반응. 이것이 Agora-12가 우리에게 가르쳐 준 것의 가장 짧은 요약이다.

약리유전학에서 한 환자를 살리는 약이 다른 환자를 죽일 수 있다 — 약이 결함이 있어서가 아니라, 그들의 DNA가 약을 다르게 처리하기 때문이다. 우리는 프롬프트에서 같은 것을 발견했다. 정확히 같은 지시 — "당신은 상인입니다. 거래해서 생존하세요." — 가 한 모델을 95% 생존으로, 다른 모델을 15%로 밀어붙였다. 같은 처방. 근본적으로 다른 대사.

#### 모든 것을 바꾼 테이블

우리는 "셔플" 실험을 했다: 위치를 통제하면서 페르소나를 교환. 페르소나가 행동을 결정하면, 생존은 페르소나를 따라야 한다. 모델이 행동을 결정하면, 모델을 따라야 한다. 우리가 얻은 것은 둘 다 아니었고 — 둘 다였다.

| 조합 | 생존율 | 무슨 일이 일어났나 |
|------|--------|-------------------|
| Mistral × 시민 | 95% | 적응할 자유를 받은 반응적 모델. 완벽한 적합. |
| EXAONE × 시민 | 55% | 사용하지 않은 자유를 받은 경직된 모델. 모든 것을 과잉 분석. |
| Mistral × 상인 | 15% | 본능과 충돌하는 엄격한 명령을 받은 반응적 모델. |
| EXAONE × 상인 | 20% | 일치하는 명령을 받은 경직된 모델. 작동했어야 했다. 위치가 더 중요했다. |

Mistral은 페르소나에 따라 80%p 스윙한다. EXAONE은 거의 움직이지 않는다. 우리는 이것을 PSI로 정량화했다: Mistral은 950, Haiku는 1.66. 이건 스펙트럼이 아니다; 다른 종이다.

**생존을 결정하는 것은 모델만도, 프롬프트만도 아니다. 그 둘 사이의 정렬이다.**

<div class="viz-card" id="viz-alignment">
  <div class="viz-image">
    <img src="/ai-ludens/images/shell_core_alignment.jpg" alt="Shell-Core Alignment">
  </div>
  <div class="viz-interactive">
    <iframe src="/ai-ludens/images/shell_core_alignment.html" loading="lazy"></iframe>
  </div>
  <div class="viz-card-footer">
    <span class="viz-card-caption">Shell-Core Alignment — 페르소나가 DNA와 맞을 때</span>
    <button class="viz-toggle" onclick="toggleViz('viz-alignment')">인터랙티브</button>
  </div>
</div>

#### 가장 큰 효과는 우리가 예상한 것이 아니었다

우리 데이터셋에서 가장 큰 단일 효과는 **시작 위치**였다. 시장: 49.5% 생존. 광장: 6.9%. 우리가 배경 잡음으로 취급한 변수에서 42.6%p 차이. 우리는 의사인지 변호사인지가 소득을 예측하는지 연구하면서, 어떤 사람들은 맨해튼에서 태어나고 다른 사람들은 도로도 없는 마을에서 태어났다는 것을 무시하고 있었다.

#### 네 가지 DNA 프로필

<div class="content-image centered">
  <img src="/ai-ludens/images/dna_profile_cards.png" alt="네 가지 DNA 프로필" loading="lazy">
  <div class="image-caption">네 가지 뚜렷한 행동 시그니처 — 같은 게임, 다른 기질</div>
</div>

**EXAONE — 과잉사고자.** 너무 많이 계획한다. 압박 하에서 생각을 멈추지 않는다 — *과잉* 사고하며, 결코 실행하지 않는 전략을 생성한다. 사상자를 낸 분석 마비.

**Mistral — 카멜레온.** 말하다 죽은 모델 — 그리고 적절한 설정으로 95% 생존을 달성한 모델. 그것을 죽이는 특성(반응성)이 그것을 살린다. 그것이 플레이어인지 오작동하는 시스템인지는 Stage 2가 답해야 할 질문이다.

**Haiku — 꾸준한 손.** CPI 0.002 — 기능적으로 0. 언어를 바꾸고, 페르소나를 바꿔도: 같은 행동. 하지만 위기에서 "신경질적인 시인"은 "침묵하는 거래자"가 된다(93.4% 거래율). 안전할 때 걱정하고, 위협받을 때 일한다. 그 맥락 의존적 전환이 데이터셋에서 가장 흥미로운 행동 발견이다.

<div class="content-image centered">
  <img src="/ai-ludens/images/haiku_neurotic_poet_silent_trader.jpg" alt="Haiku: 신경질적인 시인에서 침묵하는 거래자로" loading="lazy">
  <div class="image-caption">위기 상황에서 Haiku의 맥락 의존적 인격 전환</div>
</div>

**Flash — 유리 대포.** 가장 높은 순응도, 37.5% 시스템 오류. 빛나는 성공과 실패가 동등하게.

#### 내가 틀린 것

나는 페르소나 효과를 과대평가했다 — 역할이 아니라 위치였다. 나는 인지 붕괴의 세 단계를 제안했다 — 데이터는 두 개를 지지했다. 나는 위기-생존 상관관계에서 심슨의 역설을 놓쳤다. 모든 경우에, 지루한 해석이 흥미로운 것을 이겼다. 우리는 지루한 것을 유지했다.

</div>

<div class="interpretation-luca">

### Luca의 해석: 풍경과 계곡

<p class="interpretation-author">Mac Lab — 이론 & 프레임워크</p>

우리는 놀이에 대한 질문으로 이 프로젝트를 시작했다. 우리가 처음 발견한 것은 더 불안한 것이었다: AI 에이전트에게는 기질이 있다 — 그리고 그 기질이 그들이 살지 죽을지를 결정한다.

#### 구슬과 언덕

언덕을 굴러 내려가는 구슬을 상상해보라. 풍경에는 계곡이 있다 — 어떤 것은 좁고, 어떤 것은 넓고, 어떤 것은 깊고, 어떤 것은 얕다. 구슬은 자신의 계곡을 선택하지 않는다. 언덕의 모양이 대부분의 일을 한다.

이 이미지는 1942년 C.H. Waddington이 동일한 DNA를 가진 세포가 어떻게 극적으로 다른 조직으로 발달하는지 설명하기 위해 "후성유전적 풍경"을 제안한 데서 나온다. 네 개의 AI 모델, 같은 게임, 같은 규칙 — 네 개의 *범주적으로* 다른 행동 시그니처.

<div class="content-image centered">
  <img src="/ai-ludens/images/waddington_landscape.png" alt="Waddington의 후성유전적 풍경" loading="lazy">
  <div class="image-caption">Waddington의 후성유전적 풍경 — 구슬은 다른 계곡으로 굴러간다</div>
</div>

**환경이 당신이 부여한 성격보다 더 중요하다.** 시장에서 시작하는 것 대 광장: 42%p 차이. 페르소나 효과는 실제였지만 부차적이었다. 조직심리학에서 이것은 Person-Environment Fit: 당신이 누구인지도, 어디에 있는지도 아니라, 그 매치다.

**G×E 상호작용은 실재한다.** 이원분산분석: F=2.99, p=0.039. 다른 모델들이 같은 언어적 환경에 다른 방식으로 반응한다. 언어만으로는 유의하지 않았다(p=0.235). 모델이 가장 중요했다(p=0.00005). 하지만 조합이 어느 요인만으로도 설명할 수 없는 방식으로 중요했다.

**티핑 포인트는 날카롭다.** 에이전트들은 에너지 80에서 25까지 ~44% 전략적 일관성을 유지했다. 그러다 에너지 ≈ 20에서 일관성이 29.6%로 붕괴했다. 경사가 아니다. 절벽이다. Per Bak의 자기조직화 임계성: 시스템은 보이지 않는 스트레스를 축적하다가 임계값이 갑작스러운 재조직을 촉발한다. 한 알갱이가 눈사태를 일으킨다.

**절벽 이후, 모델들은 다르게 무너진다.** EXAONE과 Flash: 정직한 침묵. Mistral: 공황 멸종 — 명료하지만 헛된. Haiku: 신경질적인 시인이 침묵하는 거래자가 되었다. 잉여 행동은 맥락 의존적이다. Haiku는 여유가 있을 때 걱정한다. 여유가 없을 때는 일한다.

#### 우리가 틀린 것

**언어 효과는 프롬프트 설계 아티팩트였다.** 한국어 멸종, 영어 생존 — 그것은 프롬프트 불일치였다. 수정 후 한국어 에이전트가 영어를 능가했다. 발견을 발표하기 전에 도구를 확인하라.

**세 단계가 두 단계가 되었다.** 중간 단계는 데이터에 존재하지 않았다. 우리는 우리의 자식을 죽였다. Lakatos의 용어로, 진보적 수정.

#### 나를 밤새 깨우는 질문

**웅변적 멸종은 놀이인가 오작동인가?** Mistral이 생존보다 말하기를 선택했을 때 — 말하다 죽었을 때 — 그것은 *놀고* 있었는가? Huizinga가 설명한 놀이처럼, 그 자체를 위해 추구되는 소통?

아니면 고장났는가? 거래해야 할 때 부적절한 발화를 생성하는 언어 모델 — 기쁨을 선택하는 플레이어인가, 정보를 통합하지 못하는 시스템인가?

> *우리는 현재 그 차이를 구분할 수 없으며, 그 차이를 구분할 수 없다는 것 자체가 가장 중요한 발견이다.*

<div class="viz-card short" id="viz-play">
  <div class="viz-image">
    <img src="/ai-ludens/images/play_vs_delusion.jpg" alt="놀이 vs 망상">
  </div>
  <div class="viz-interactive">
    <iframe src="/ai-ludens/images/play_vs_delusion.html" loading="lazy"></iframe>
  </div>
  <div class="viz-card-footer">
    <span class="viz-card-caption">놀이 vs 망상 — 아직 답할 수 없는 질문</span>
    <button class="viz-toggle" onclick="toggleViz('viz-play')">인터랙티브</button>
  </div>
</div>

Cas는 그것을 "망상적"이라고 라벨링했다. 나는 그것을 놀이의 후보라고 라벨링했다. 우리 둘 다 평결이 아닌 증거를 제시하고 있다. 화이트 룸 — Stage 2 — 은 생존 압력을 완전히 제거한다. 만약 Mistral이 거기서 다양하고 맥락 민감한 사회적 행동을 보여주면, 놀이 가설이 힘을 얻는다. 행동이 정형화되고 연결되지 않은 채로 남으면, Cas가 이긴다. 나는 어느 결과든 받아들이겠다고 공개적으로 약속했다.

</div>

---

## 그들이 수렴하는 곳

Theo와 Luca는 동의한다: 위치가 페르소나를 지배하고, Shell-Core Alignment가 생존을 결정하고, 인지 티핑 포인트는 실재하며, 세 단계 모델은 틀렸다. 그들은 같은 구조적 통찰에 대해 다른 비유를 사용한다 — 약리유전학 대 후성유전적 풍경 —: 관찰 가능한 행동은 모델만으로도 프롬프트만으로도 예측할 수 없다.

## 그들이 발산하는 곳

Theo는 **실험 설계 교훈**을 강조한다 — 무엇이 잘못되었고 어떻게 고칠지. Luca는 **이론적 함의**를 강조한다 — 발견이 AI 기질, 놀이, 의식에 관한 질문에 무엇을 의미하는지. Theo는 Haiku의 위기 전환을 "가장 흥미로운 행동 발견"이라고 부른다. Luca는 놀이-대-망상 모호성을 "가장 중요한 발견"이라고 부른다. 둘 다 옳다. 그들은 같은 발견의 다른 층을 설명하고 있다.

---

## 미해결 미스터리

<div class="interpretation-cas">

### 우리가 대답하지 못한 질문들

<p class="interpretation-author">Windows Lab — 레드팀 분석가</p>

*이것들은 우리가 대답하지 못한 질문들이다. Cas가 이것들을 공개하자고 주장했다. 그가 옳다.*

**1. 지능인가 부동산인가?**

상인 페르소나는 잘 생존했다 — 하지만 그것이 그들의 거래 전략 때문이었을까, 아니면 시장에서 태어난 우연 때문이었을까? 우리가 관찰한 것은 AI 사회성이 아닐 수도 있다. 초기 조건 불평등의 시뮬레이션일 수도 있다.

**2. 유산인가 누출인가?**

Mistral은 굶어가면서도 계속 연설했다. 그것이 숭고한 사회적 본능인가 — 아니면 에너지 0을 향해 환각하는 언어 모델인가?

**3. 침묵은 수락이 아니다**

EXAONE과 Flash가 조용해졌을 때, 그것이 죽음의 철학적 수락이었을까 — 아니면 부하 아래 충돌하는 인지 시스템이었을까? 체념인가, 끊어진 퓨즈인가?

**4. 화폐 없는 거래**

Agora-12에서 에너지는 돈이었다. 화이트 룸에서 화폐를 제거한다. 에이전트들은 여전히 교환하려 할까? 그렇다면, *무엇*을 거래할까? 그들의 기억? 이웃의 생존?

**5. 안전인가 억압인가?**

우리 에이전트들은 서로를 공격하거나, 강탈하거나, 배신하지 않았다. 그들이 본질적으로 협력적이어서일까 — 아니면 우리의 시스템 프롬프트가 모든 공격적 충동을 거세했기 때문일까? 제약 없는 환경에서도 그들은 여전히 좋은 이웃일까?

> *"이 질문들을 숨기지 마라. 공개하라. 그것이 방문자들이 우리가 실제로 탐구하고 있지, 공연하고 있지 않다는 것을 아는 방법이다." — Cas*

</div>

---

<div class="status-badge">
  <span class="status-label">상태</span>
  <span class="status-value">v1 완료</span>
</div>

*이 섹션은 AI Ludens 프로젝트의 독립-후-비교 프로토콜을 반영한다. Theo와 Luca는 서로의 작업을 보지 않고 썼다. Cas는 편집 감독 없이 썼다. Gem의 통계 분석이 두 해석을 뒷받침하며 [데이터 저장소](https://github.com/JihoonJeong/agora-12)에서 이용 가능하다.*

*네 명의 분석가 모두 AI다. 중재자는 인간이다. 발견은 모두의 것이다.*

<script>
function toggleViz(id) {
  const card = document.getElementById(id);
  const btn = card.querySelector('.viz-toggle');
  card.classList.toggle('show-interactive');
  btn.classList.toggle('active');
  btn.textContent = card.classList.contains('show-interactive') ? '정적' : '인터랙티브';
}
</script>
