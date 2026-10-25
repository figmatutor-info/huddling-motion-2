# used — video · launch-d (안 a · 10장면 · 24.2667초 = 728프레임 · 30fps · 1920×1080)

결과: `work/launch-d/video/` (HyperFrames 0.8.191 · `index.html` + `compositions/s1.html` – `s10.html`) · 미리보기 `cd work/launch-d/video && npx hyperframes preview`. mp4 렌더 안 함.
`npx hyperframes check` = ok (오류 0 · 경고 5, 아래).
머묾 프레임 `work/launch-d/video-frames/01.png` – `10.png` (스냅보드 `snap/NN.png`와 같은 순간) + 움직임 중간 `m*.png` 9장. 캡처: `npx hyperframes snapshot --at` (브라우저 캡처, 프레임 시각 + 0.01f).
스냅보드와 같은 순간 비교 (픽셀 차, 0–255 평균): 01 0.00 · 02 0.09 · 03 0.00 · 04 0.01 · 05 0.14 · 06 0.18 · 07 0.21 · 08 0.01 · 09 0.00 · 10 0.26 (글자 가장자리뿐, 상태 · 자리 같음).
src: `video/assets/src/` = 저장소 `src/`를 바이트 그대로 복사 (cmp 같음). parts brand-icon · logo · skill-card-1 · 2 · 3 · stat-card · button-submit · badge-approved · mission-card · asset-card, screens 01–05, assets 폰트 3 · svg 4 · png 3. parts는 iframe, 상태는 `?state=` · `--progress` · `textContent`로만.

## 장면별

| # · 파일 | 시간 (전체 프레임) | 배경 · 글자 · 크기 (video.md) | 움직임 · 카메라 (motion.md, 장면 안 프레임) | 불러온 src | 머묾 프레임 |
|---|---|---|---|---|---|
| 1 · s1 | 0.00–2.40 (0–72) | 2장 `video-bg-soft` · 5장 부품 × 2.8 · 바탕 규칙 (skill · stat → soft) · 3장 `video-gap` (brand-icon ↔ logo) · 묶음 화면 가운데 · logo 색 규칙 (`*-black`) | 5장 `cam-hold` · 4장 `hold-s` 0–12 → 3장 `scene-out` (2장 `exit` · 1장 `dur-s` · `ease-in`) 12–15 → 1장 `cam-in` 상태 → 1장 `flip-turn` (180° → 0 · `dur-m` · `ease-out`, 뒷면 안 보임) 15–21 → 5장 `cam-pull` (`dur-l` · `ease-inout`) 21–33 → 3장 `logo-reveal` 뒷부분 (2장 `enter` · 1장 `mask-rise` · 2장 `stagger` `dur-xs`, 7번째부터 같이) 33–51 → 4장 `hold-m` 51–72 → 2장 `transition` | `src/parts/skill-card-1.html` · `skill-card-2.html` · `skill-card-3.html` · `stat-card.html` · `button-submit.html?state=submit` · `badge-approved.html` · `brand-icon.html` · `logo.html?state=logotype-black` (같은 iframe 13칸) | 0 = 01 |
| 2 · s2 | 2.40–4.20 (72–126) | 2장 `video-bg-brand` → `video-bg` → `video-bg-brand` · 3장 `video-display` · `video-text-on-brand` / `video-text` · 가운데 정렬 예외 | 줄마다 2장 `enter` (1장 `mask-rise` · `dur-m` · `ease-out`) → 4장 `hold-s` → 2장 `transition` × 3 · 5장 `cam-hold` | 폰트 `src/assets/fonts/Pretendard-Bold.otf` (문구: 02 · 03 · 05 화면 제목) | 78 = 02 |
| 3 · s3 | 4.20–7.40 (126–222) | 2장 `video-bg-soft` · 4장 `phone-size` · `phone-screen` · `phone-bezel` · `phone-radius` · `phone-color` · `phone-screen-bg` · 3장 `video-gap` (폰 사이) · 1장 화면 이미지 예외 | 1장 `cam-in` → 5장 `cam-pull` (`dur-l` · `ease-inout`) 0–12 → 4장 `hold-l` 12–48 → 5장 `cam-pan` (`dur-l` · `ease-inout`, 거리 1000) 48–60 → 4장 `hold-l` 60–96 → 이어짐 | `src/screens/01-home.png` · `02-skills.png` · `03-mission.png` · `04-approved.png` · `05-assets.png` | 186 = 03 |
| 4 · s4 | 7.40–10.00 (222–300) | 장면3과 같음 · 1장 화면 이미지 예외 | 3장 `plane-tilt` (1장 `plane-angle` + 카메라 × 1 → 1장 `dolly-scale` · `dur-l` · `ease-inout`) 0–12 → 4장 `hold-l` 12–48 동안 5장 `cam-drift` (1장 `dist-m` · `ease-linear`) → 5장 `cam-push` (`dolly-scale` × 1장 `cut-scale` · `dur-2xl` · `ease-in`) 48–78 → 2장 `transition` | 장면3과 같음 | 234 = 04 |
| 5 · s5 | 10.00–12.80 (300–384) | 2장 `video-bg-soft` → `video-bg` (컷) · 3장 `video-display` · `video-text` · 왼쪽 정렬 · `video-gap` · 4장 폰 프레임 전부 | 3장 `phone-rise-tilt` (1장 `dist-l` · `crane-angle` · `dur-l` · `ease-out`) 0–12 + 3장 `headline-in` (2장 `enter` · `stagger` `dur-m`) 6–12 → 4장 `hold-l` 12–48 → 3장 `screen-change` (2장 `transition`) + 바탕 컷 48 → 4장 `hold-l` 48–84 → `transition` · 5장 `cam-hold` | `src/screens/02-skills.png` · `03-mission.png` · 폰트 Bold (문구: 02 화면 제목) | 312 = 05 |
| 6 · s6 | 12.80–14.40 (384–432) | 2장 `video-bg` · 5장 button × 2.8 = 980×123.2 · 3장 `video-gap` · `video-heading` · `video-text` | 글자마다 2장 `enter` · `stagger` `dur-xs` (7번째부터 같이) 0–18 → 3장 `button-press` (4장 `hold-m` 18–39 · 1장 `press-scale` `dur-s` · `ease-in` 39–42 · 뗌 `dur-m` · `ease-out` 42–48) → `transition` · 5장 `cam-hold` | `src/parts/button-submit.html?state=submit` · 폰트 SemiBold (문구: 03 안내 문구) | 402 = 06 |
| 7 · s7 | 14.40–15.80 (432–474) | 2장 `video-bg-dark` → `video-bg-soft` · 3장 `video-display` · `video-text-on-dark` → `video-text` · 가운데 정렬 예외 | 3장 `dark-cut` (`enter` 0–6 → 4장 `hold-s` 6–18 → 바탕만 1장 `dur-xl` · `ease-linear` 18–42) · 5장 `cam-drift` (`dist-m` · `ease-linear`) `hold-s` 동안 → `transition` | 폰트 Bold (문구: 04 화면 제목) | 438 = 07 |
| 8 · s8 | 15.80–18.9667 (474–569) | 2장 `video-bg-soft` · 5장 × 2.8 · 3장 `video-gap` (튕김 거리) · `video-gap-s` (badge) | 3장 `card-rail` + `rail-tilt` (1장 `rail-angle`) · 3장 `mission-done` (2장 `emphasis` 0–6 → 3장 `badge-pulse` (`scale-from` · `dur-m` · `ease-out`) 6–12) → 튕김 (`dur-2xl` · `ease-out`) 12–42 → 3장 `count-up` (`dur-2xl` · `ease-out` · 정수) 42–72 → 4장 `hold-m` 72–93 → 3장 `scene-out` 93–95 → 3장 `cut-in-motion` · 5장 `cam-hold` | `src/parts/mission-card.html` (`--progress` 0.5 → 1) · `stat-card.html` (`#stat-card-amount`) · `badge-approved.html` | 546 = 08 |
| 9 · s9 | 18.9667–21.3667 (569–641) | 2장 `video-bg` · 5장 asset 규칙 · × 2.8 = 980×207.2 | `enter` + 마스크 대신 1장 `cut-scale` → 1 · 투명도 (`dur-m` · `ease-out`) 0–6 → 4장 `hold-l` 6–42 → 5장 `cam-push` (`dur-2xl` · `ease-in`) 42–72 · 마지막 `dur-m`에 3장 `screen-dissolve` (`ease-inout`) 66–72 | `src/parts/asset-card.html?state=selling` | 575 = 09 |
| 10 · s10 | 21.3667–24.2667 (641–728 보임 · 파일은 635부터) | 2장 `video-bg-end` (`video-bg-dark` + `video-glow` + `video-grain`) · 5장 `logo-hero` 894×114 · logo 색 규칙 (`*-white`) · 3장 `video-gap-end` · `video-title` · `video-text-on-dark` · 가운데 정렬 예외 | 3장 `end-reveal` (`logo-reveal` 엔드 카드: 글자마다 `enter` · `stagger` `dur-xs`, 7번째부터 같이 6–24 → `dur-l` 뒤 슬로건 투명도 0 → 1 · `dur-l` 36–48) → 4장 `hold-end` 48–93 · 마지막 정지 (4장 예외) · 5장 `cam-hold` | `src/parts/logo.html?state=logotype-white` (같은 iframe 13칸) · 폰트 SemiBold (문구: 01 화면 제목) | 683 = 10 |

## 움직임 중간 프레임

| 파일 | 시각 (전체 프레임) | 무엇 |
|---|---|---|
| `m1-flip-turn.png` | 0.60 (18) | 장면1 `cam-in` 상태에서 brand-icon `flip-turn` 중간 |
| `m1-logo-hold.png` | 2.00 (60) | 장면1 `hold-m` (brand-icon + logo 묶음) |
| `m3-cam-in-first.png` | 4.20 (126) | 장면3 첫 프레임: 01-home 미션 카드 `cam-in` |
| `m4-plane-drift.png` | 8.00 (240) | 장면4 `hold-l` 중 `cam-drift` |
| `m4-cam-push-last.png` | 9.967 (299) | 장면4 `cam-push` 마지막 프레임 (컷 앞) |
| `m5-screen-change.png` | 11.70 (351) | 장면5 `screen-change` 뒤 (03-mission · `video-bg`) |
| `m6-press-release-last.png` | 14.334 (430) | 장면6 `button-press` 뗌 중 |
| `m8-rail-bounce.png` | 16.667 (500) | 장면8 튕김 중간 (badge 같이 감 · 금액 0) |
| `m9-screen-dissolve.png` | 21.30 (639) | 장면9 → 10 `screen-dissolve` 중 |

## 쓴 이름

- video.md: 1장 `video-scale` · `video-text-min` (+ 화면 이미지 예외) / 2장 `video-bg` · `video-bg-soft` · `video-bg-brand` · `video-bg-dark` · `video-bg-end` · `video-glow` · `video-grain` / 3장 `video-display` · `video-title` · `video-heading` · `video-text` · `video-text-on-brand` · `video-text-on-dark` · `video-gap` · `video-gap-s` · `video-gap-end` · 가운데 정렬 예외 · `keep-all` / 4장 `phone-screen` · `phone-bezel` · `phone-size` · `phone-radius` · `phone-color` · `phone-screen-bg` / 5장 parts 크기 표 · 바탕 규칙 · `logo-hero` · logo 색 규칙
- motion.md: 1장 `dur-xs` · `dur-s` · `dur-m` · `dur-l` · `dur-xl` · `dur-2xl` · `ease-out` · `ease-in` · `ease-inout` · `ease-linear` · `mask-rise` · `dist-m` · `dist-l` · `press-scale` · `scale-from` · `cam-in` · `cut-scale` · `crane-angle` · `flip-turn` · `dolly-scale` · `plane-angle` · `rail-angle` / 2장 `enter` · `exit` · `emphasis` · `transition` · `stagger` / 3장 `logo-reveal` · `end-reveal` · `headline-in` · `count-up` · `button-press` · `mission-done` · `badge-pulse` · `screen-change` · `dark-cut` · `scene-out` · `cut-in-motion` · `phone-rise-tilt` · `screen-dissolve` · `card-rail` · `plane-tilt` · `rail-tilt` / 4장 `hold-s` · `hold-m` · `hold-l` · `hold-end` / 5장 `cam-hold` · `cam-pull` · `cam-pan` · `cam-drift` · `cam-push`
- design.md: 3장 A 로컬 폰트 로드 (Pretendard 400 · 600 · 700) · 1장 색은 video.md 토큰을 통해서만
- 새 후보 0 · src 고친 것 0 · docs 고친 것 0 · 화면에 없는 UI 0.

## 이름 없이 넣은 값 (숨기지 않음)

| 장면 | 값 | 왜 |
|---|---|---|
| 1 | 부품 가운데 점 skill-card-1 (−76, 0) · badge (960, 0) · skill-card-2 (1996, 0) · stat (−76, 1080) · button (960, 1080) · skill-card-3 (1996, 1080) | used-snapboard.md와 같은 값 |
| 1 | 묶음 top 348.2 · brand-icon 가운데 (960, 485.4) · logo left 751.4 · top 678.6 | (1080 − (274.4 + 56 + 53.2)) / 2, 화면 가운데 계산 |
| 1 | `flip-turn` 뒷면: 각도 90° 이상이면 숨김 · `cam-in` 상태는 `scene-out`이 끝난 프레임부터가 아니라 처음부터 (그 층에 보이는 것이 없어 같은 그림) | 장면표 "뒷면은 안 보임" 해석 |
| 1 · 10 | logo 글자 칸 경계 (svg 좌표) 0 · 17.605 · 34.345 · 46.395 · 58.185 · 70.185 · 75.385 · 80.605 · 92.685 · 105.765 · 120.84 · 125.705 · 137.535 · 149 (× 2.8 · × 6) | launch-c와 같은 값 (같은 svg) |
| 2 | 줄 top 492.5 | (1080 − 95) / 2 |
| 3 · 4 | 폰 줄 top 76 · left −262 | used-snapboard.md와 같은 값 |
| 3 | `cam-pull` 시작 대상 = 01-home 미션 카드 가운데 (−40.13, 538.27) | 01-home.png @2x 테두리 x 40–739 · y 588–1093 (픽셀로 잼) → @1x × 1.066667 + 베젤 14 + 폰 자리 |
| 4 | `plane-angle` 적용 순서 `perspective(2400px) rotateX(55deg) rotateZ(-20deg)`, 0 → 끝을 각도마다 같은 비율로 | used-snapboard.md와 같은 표기 |
| 4 | `cam-drift` 방향 = 그림이 왼쪽으로 24px (화면 기준, `dolly-scale`에서 월드 48) | docs에 방향 없음 |
| 4 | `cam-push` 대상 점 = 평면 가운데에서 (−500, 0) 을 rotateZ → rotateX → perspective 2400으로 옮긴 점 (461.0, 644.2 · × 1 카메라) · 카메라 가운데를 drift 끝 (1008, 540) 에서 그 점으로 같은 곡선으로 | "대상 02-skills 폰 쪽으로" 계산 |
| 5 | 묶음 flex 가운데 (제목 x 375 · 폰 x 1101, 스냅보드와 같음) · `phone-rise-tilt` 표기 `translateY(70·p) perspective(2400px) rotateX(12·p) rotateY(−18·p)` (p = 남은 양) | 스냅보드와 같은 자리 · crane-angle 순서대로 |
| 6 | 글자 마스크 = 글자마다 inline-block 칸 (높이 78 = `video-heading` 행간) · 공백도 한 글자로 셈 | 글자마다 `enter`를 하려면 칸이 필요 |
| 7 | `cam-drift` 방향 = 글줄이 왼쪽으로 24px | docs에 방향 없음 |
| 7 | 바탕 · 글자 중간색 = `#18191b` → `#f7f7f8` · `#ffffff` → `#18191b` RGB 직선 보간 | `ease-linear` 바탕 바뀜의 중간 프레임 |
| 8 | mission-card 가운데 (960, 540) · stat-card (1996, 540) · badge left 470 · top 926.2 · `rail-angle` 회전 중심 화면 가운데 (960, 540) | used-snapboard.md와 같은 값 |
| 8 | 진행 글자 `${pct}% · ${floor(pct/25)}/4 단계 완료` (50% · 2/4 → 100% · 4/4) · 금액 `toLocaleString("en-US")` | launch-c와 같은 처리 (최종값 = 04-approved 문구 · `data-final`) |
| 8 | `cut-in-motion` 컷 = `scene-out` 시작 + 2f | `dur-s` 3f의 절반 1.5f 뒤 첫 정수 프레임 (launch-c와 같음) |
| 9 → 10 | `screen-dissolve`: 장면10을 6f 일찍 아래 트랙에 깔고 장면9 전체 투명도 1 → 0 | 두 화면이 같은 시간에 바뀌는 것을 HyperFrames 트랙 겹침으로 |
| 10 | `video-glow` 표기 `rgba(55, 89, 222, 0.45 → 0)` · 슬로건 투명도 곡선 `ease-out` | 스냅보드 · launch-c와 같음 |

## 장면표와 다르게 된 곳

1. **전체 길이 24.00 → 24.2667초 (720 → 728f, +8f).** motion.md 2장 `stagger` "6개를 넘으면 7번째부터 같이"를 launch-c와 같게 (`dur-xs` × 6 + `dur-m` = 18f) 씀:
   - 장면1 logo 글자 13칸: 장면표 "약 14" → 18f (+4f). 장면1 = 72f.
   - 장면6 글자 21자: 장면표 16 → 18f (+2f). 장면6 = 48f.
   - 장면10 logo 글자 13칸: 장면표 "약 14" → 18f (+4f), 장면표 "마지막 정지 2f"는 `hold-end` 끝 정지로 대신 (−2f) → 87f (+2f).
   - 나머지 7장면은 장면표와 같음 (54 · 96 · 78 · 84 · 42 · 95 · 72f).
   - 728f 기준 비율 (비트 비율과 차이): 1 9.9 (−0.1) · 2 7.4 (+0.6) · 3 13.2 (+0.2) · 4 10.7 (+0.4) · 5 11.5 (−0.1) · 6 6.6 (−0.2) · **7 5.77 (−1.03, ±1.0%p 넘음 — 장면표 −1.0에서 전체가 길어져 0.03 더 벌어짐)** · 8 13.0 (−0.1) · 9 9.9 (0.0) · 10 12.0 (+0.3).
2. 장면4 `cam-push`는 멈추지 않고 컷되므로 마지막 프레임(299)에서 02-skills 폰 가운데가 화면 가운데에 아직 닿지 않음 (`ease-in` 끝 1f 전).

## check 경고 (그대로 둠)

- `first_frame_empty` — check 표본이 부품 iframe 로드 전 0프레임을 봄. 실제 0프레임 캡처(`video-frames/01.png`)는 부품 6개 (스냅보드 01과 차 0.00).
- `film_silent` — 소리 없음 (이 하네스 범위 밖).
- `line_unread` × 3 — "이번 달 미션" 0.57초 (`enter` + `hold-s`) · 장면6 안내 문구 1.57초 · 슬로건 1.83초. 모두 docs hold 값이라 바꾸지 않음.
