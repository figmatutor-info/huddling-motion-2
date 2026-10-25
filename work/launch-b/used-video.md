# used — video · launch-b (안 a · 12장면 · 20.0초 = 600프레임 · 30fps · 1920×1080)

결과: `work/launch-b/video/` (HyperFrames 0.8.191 · `index.html` + `compositions/s1.html` – `s12.html`) · 머묾 프레임 `work/launch-b/video-frames/01.png` – `12.png` (`npx hyperframes snapshot --at`, 브라우저 캡처).
mp4 렌더 안 함. `npx hyperframes check` = ok (오류 0 · 경고 7, 아래).
기준 파일 (2026-10-25 피그마 반영본을 지금 읽음): video.md 4장 (03-mission 제출하기 @1x x 20 · y 753 · 350×44 · 그림자 없음 102줄) · 5장 크기 표 · motion.md 3장 `screen-dissolve` · `zoom-through` · `phone-rise-tilt` · `icon-expand` · 5장 `cam-pan` · `cam-push` · [기본 스타일]/[고정] 표시.
src: `video/assets/src/` = 저장소 `src/`를 바이트 그대로 복사 (cmp 같음). 쓰는 것만 둠 (screens 01 · 03 · 04, parts brand-icon · button-submit · mission-card · stat-card · logo, assets 폰트 3 · logo svg 4 · perdi-flag). parts는 iframe, 상태는 `?state=`로만.
스냅보드와 같은 순간 비교 (픽셀 차, 0–255 평균): 01 0.08 · 02 0.13 · 03 0.15 · 04 0.01 · 05 0.04 · 06 0.16 · 07 0.16 · 08 0.01 · 09 0.00 · 10 0.01 · 11 0.27 · 12 0.84 (글자 가장자리 안티앨리어싱 · grain 위 로고 가장자리뿐, 상태 · 자리 같음).

## 장면별

| # · 파일 | 시간 (프레임) | 배경 · 글자 · 크기 (video.md) | 움직임 · 카메라 (motion.md) | 불러온 src | 머묾 프레임 |
|---|---|---|---|---|---|
| 1 · s1 | 0.0–1.6 (0–48) | `video-bg` · `video-display` · `video-text` · 화면 가운데 한 줄 (3장 훅 예외) | `cam-hold` · 단어마다 `enter` + 마스크 대신 `scale-from` → 1 (`dur-m` · `ease-out`), 단어 사이 `stagger` `dur-m` · 구절1 0–12 → `hold-s` 12–24 → `transition` → 구절2 23–35 (1f 앞당김) → `hold-s` 35–48 → `transition` | 폰트 Bold | 40f = 01 |
| 2 · s2 | 1.6–2.5 (48–75, 마지막 3f는 장면3 위) | `video-bg` (24f까지) · brand-icon × 2.8 (`video-scale`) · `video-gap` · `video-display` · `video-text-accent` · 묶음 가운데 | brand-icon `enter` + 마스크 대신 `scale-from` → 1 −1–5 → `stagger` → 글자 `enter` (`mask-rise`) 5–11 → `hold-s` 11–24 → `scene-out` (`exit` `dur-s` · `ease-in`) 24–27 = 장면3 `phone-rise-tilt`와 같은 프레임 시작 | `src/parts/brand-icon.html` | 66f = 02 |
| 3 · s3 | 2.4–4.4 (72–132) | `video-bg-soft` · 폰 프레임 4장 전부 · 01-home | `phone-rise-tilt` (`dist-l` · `crane-angle` → 0, `dur-l` · `ease-out`) 0–12 → `hold-l` 12–48 → `zoom-through` (× 1 → `cam-in`, 대상 "적용 사례 정리하기 →", `dur-l` · `ease-in`) 48–60 → `transition` | `src/screens/01-home.png` | 102f = 03 |
| 4 · s4 | 4.4–5.2 (132–156) | `video-bg-soft` · button-submit apply-case × 2.8 = 890.4×123.2 · 가운데 | `cam-hold` · 첫 프레임부터 놓임 → `hold-m` 0–21 → `shape-morph` 앞부분 글자 `exit` 21–24 → 이어짐 | `src/parts/button-submit.html?state=apply-case` | 144f = 04 |
| 5 · s5 | 5.2–6.0 (156–180) | `video-bg-soft` · 같은 버튼 → mission-card × 2.8 = 980×708.4 · 점 자리 = 가운데 | `shape-morph` 나머지: 폭 318 → 44 (원) `dur-m` · `ease-in` 0–6 → 원 → `scale-from` `dur-m` · `ease-in` 6–12 → `transition` → mission-card `scale-from` → 1 `dur-m` · `ease-out` 11–17 (1f 앞당김) → `screen-dissolve` (`dur-m` · `ease-inout`) 18–24 | `src/parts/button-submit.html?state=apply-case` · `src/parts/mission-card.html` | 174f = 05 |
| 6 · s6 | 5.8–8.3 (174–249) | `video-bg-soft` (6f부터) · 폰 프레임 · 03-mission · 시작 미션 카드 가운데 (폰 top 310.06) · button-submit submit 겹침 + 덮개판 (4장 예외, `radius-button`) | `screen-dissolve` 0–6 → `hold-m` 6–27 → `cam-pan` (× 1 세로, `dur-l` · `ease-inout`, top −300.42까지) 27–39 → `button-press` (앞 `hold-m` 39–60 · 누름 `press-scale` `dur-s` · `ease-in` 60–63 · 뗌 `dur-m` · `ease-out` 63–69) → `screen-dissolve` 69–75 | `src/screens/03-mission.png` · `src/parts/button-submit.html?state=submit` | 180f = 06 (첫 hold 첫 프레임, 스냅보드 승인대로) |
| 7 · s7 | 8.1–9.5 (243–285) | `video-bg-soft` (6f부터) · 폰 프레임 · 04-approved · 묶음 가운데 (폰 top 265.28) | `screen-dissolve` 0–6 → `hold-l` 6–42 → `transition` (컷) · `cam-hold` | `src/screens/04-approved.png` | 267f = 07 |
| 8 · s8 | 9.5–11.2 (285–336) | `video-bg-soft` · button-submit view-assets × 2.8 = 980×123.2 · 가운데 | `part-in` (`enter` + 위 `dist-m` · 투명도) −1–5 → `button-press` (`hold-m` 5–27 · 누름 27–30 · 뗌 30–36) → `shape-morph` 앞부분 (글자 `exit` 36–39 · 원 39–45 · 점 45–51) → `transition` · `cam-hold` | `src/parts/button-submit.html?state=view-assets` | 300f = 08 |
| 9 · s9 | 11.2–12.8 (336–384) | `video-bg-soft` (5장 126줄) · stat-card × 2.8 = 980×282.8 · 가운데 | `shape-morph` 끝 `scale-from` → 1 −1–5 → `count-up` (0 → `data-final` 29,700, `dur-2xl` · `ease-out` · 정수) 5–35 → `hold-s` 35–48 · `cam-hold` | `src/parts/stat-card.html` | 376f = 09 |
| 10 · s10 | 12.8–14.1 (384–423) | `video-bg-soft` · 같은 stat-card | `cam-push` (× 1 → `cut-scale`, 대상 `#stat-card-amount`, `dur-2xl` · `ease-in`) 0–30 → `icon-expand` (글자 `exit` 30–33 · 카드가 화면을 덮을 때까지 `dur-m` · `ease-in` 33–39) → `transition`, 다음 바탕 `video-bg` | `src/parts/stat-card.html` | 414f = 10 (`cam-push` 끝) |
| 11 · s11 | 14.1–17.3333 (423–520) | `video-bg` · 윗줄 `video-display` · `video-text` · 아랫줄 `video-display` · `video-text-accent` · `video-gap-line` · 두 줄 가운데 (3장 `slot-roll` 예외) | `headline-in` (`enter` 줄마다 · `stagger`) −1–11 → `hold-l` 11–47 → `slot-roll` (바뀜 47 · 59 · 65 · 71, 한 번 `mask-rise` · `dur-s` · `ease-out`) → `hold-m` 74–95 → `scene-out` 95– → `cut-in-motion` 97 | 폰트 Bold | 453f = 11 |
| 12 · s12 | 17.3333–20.0 (520–600) | `video-bg-end` = `video-bg-dark` + `video-glow` + `video-grain` · logo logotype-white `logo-hero` 894×114 · 가운데 · logo 색 규칙 (5장) | `logo-reveal` (엔드 카드: 글자마다 `enter`, `stagger` `dur-xs`, 7번째부터 같이) −1–17 → `hold-end` 17–62 → 마지막 hold 정지 62–80 (4장 예외) · `cam-hold` | `src/parts/logo.html?state=logotype-white` (같은 iframe 13개 글자 칸) | 590f = 12 |

## 쓴 이름 (중복 없이 62개)

- video.md (20): 1장 `video-scale` · `video-text-min` (부품 안 글자 최소 39px · 33.6px 확인) / 2장 `video-bg` · `video-bg-soft` · `video-bg-dark` · `video-bg-end` · `video-glow` · `video-grain` / 3장 `video-display` · `video-text` · `video-text-accent` · `video-gap` · `video-gap-line` / 4장 `phone-screen` · `phone-bezel` · `phone-size` · `phone-radius` · `phone-color` · `phone-screen-bg` / 5장 `logo-hero`
- motion.md (40): 1장 `dur-xs` · `dur-s` · `dur-m` · `dur-l` · `dur-2xl` · `ease-out` · `ease-in` · `ease-inout` · `mask-rise` · `dist-m` · `dist-l` · `press-scale` · `scale-from` · `cam-in` · `cut-scale` · `crane-angle` / 2장 `enter` · `exit` · `transition` · `stagger` / 3장 `headline-in` · `logo-reveal` · `part-in` · `count-up` · `button-press` · `shape-morph` · `screen-dissolve` · `zoom-through` · `phone-rise-tilt` · `slot-roll` · `scene-out` · `cut-in-motion` · `icon-expand` / 4장 `hold-s` · `hold-m` · `hold-l` · `hold-end` / 5장 `cam-hold` · `cam-pan` · `cam-push`
- design.md (2): 3장 A 로컬 폰트 로드 (Pretendard 400 · 600 · 700) · 4장 `radius-button` (덮개판 모서리 · `shape-morph` 시작 모서리 8)
- 새 후보 0. src · docs 고친 것 0. `work/launch-30s/` 손대지 않음.

## 이름 없이 넣은 값 (숨기지 않음)

| 장면 | 값 | 왜 |
|---|---|---|
| 3 · 6 · 7 | 폰 left 738 · 장면3 top 76 · 장면6 top 310.06 → −300.42 · 장면7 top 265.28 | 스냅보드와 같은 계산 값 (used-snapboard.md) |
| 3 | `zoom-through` 대상 점 (961.07, 631.71) = 01-home 버튼 가운데 @2x (392, 1016) | 지금 01-home.png에서 잰 값: 버튼 x 74–709 · y 972–1059 @2x (318×44 @1x). "대상 쪽으로" = 끝에 대상이 화면 가운데 |
| 6 | 겹침 배율 1.066667 · 자리 left 35.3333 · top 816.9479 · 덮개판 34.2667 · 815.8815 · 375.4667×49.0667 · 모서리 8.5333 | 스냅보드와 같은 값 (video.md 4장 자리를 폰 좌표로 옮긴 계산). 03-mission.png에서 다시 재 봄: 제출하기 @2x x 40–739 · y 1506–1593 = 4장 값과 같음 |
| 5 · 8 | 원 모서리 22 (= 높이 44 / 2) · 폭 줄 때 상자 가로 이동 (W − w) / 2 × 2.8 | "가로 폭이 높이와 같아질 때까지 줄어 원" 계산. 버튼 높이 44 인라인 고정 (줄바꿈 방지) |
| 5 · 8 · 10 | 부품 안 요소에 인라인 스타일: `#button-submit` width · height · border-radius · `.label` opacity (5 · 8), `#stat-card p` opacity (10) | `shape-morph` · `icon-expand`의 글자 `exit` · 형태 변화는 `data-state`로 안 됨. 부품 파일은 그대로 (launch-30s와 같은 방식). 판단 필요하면 critic |
| 1 · 2 · 5 · 8 · 9 · 11 · 12 | `transition` 뒤 첫 `enter`를 1f 앞당김 → 뒤 hold가 1f 길어짐 (1: `hold-s` 13f · 2: `hold-s` 13f · 8: `hold-m` 22f · 9: `hold-s` 13f) · 5: mission-card 끝 17f → `screen-dissolve` 18f 사이 1f 정지 | `transition` "다음 장면 첫 프레임에 이미 `enter` 중" · `shape-morph` "빈 바탕 프레임 없음" (`scale-from` 0 프레임 = 빈 바탕). 1f는 이름 없는 값 (launch-30s critic 불합격 뒤 같은 방식) |
| 10 | 대상 점 = `#stat-card-amount` 가운데 (부품 좌표 176.836, 35) → 화면 (965.141, 496.6) | used-snapboard.md에서 잰 값 그대로 |
| 10 | `icon-expand` 끝 배율 ≈ × 3.24 (카메라 × 1.7 위) | "화면을 덮을 때까지" 계산: `cam-push` 끝 카드 네 변이 화면 밖으로 나가는 가장 작은 배율 (위 변이 정함). 중심 = 화면 가운데에 온 대상 점 |
| 11 | `cut-in-motion` 컷 = `scene-out` 시작 + 2f | `dur-s` 3f의 절반 1.5f 뒤 첫 정수 프레임 |
| 12 | 글자 칸 경계 (svg 좌표) 0 · 17.605 · 34.345 · 46.395 · 58.185 · 70.185 · 75.385 · 80.605 · 92.685 · 105.765 · 120.84 · 125.705 · 137.535 · 149 | logo-logotype-white.svg path 경계 상자 사이 가운데 (launch-30s에서 잰 값, svg 파일 같음 확인). 칸마다 같은 logo.html iframe을 clip-path로 자름 |
| 12 | `video-glow` 색 표기 `rgba(55, 89, 222, 0.45 → 0)` | `#3759de`에 2장 불투명도를 거는 표기 (스냅보드와 같음) |

## 장면표 · 스냅보드와 다르게 된 곳

1. **장면 11 길이 · 장면 12 시작.** 장면표 14.1–18.0 (117f)인데 docs 값 합이 97f: `headline-in` 12 + `hold-l` 36 + `slot-roll` 간격 12 · 6 · 6 + 구름 3 + `hold-m` 21 + `cut-in-motion` 2 (− 앞당김 1). 남는 20f를 채울 이름이 없어 장면11은 14.1–17.3333으로 끝내고, 장면12를 17.3333에 시작해 마지막 hold 정지(motion.md 4장 예외)로 20.0초를 채움. 엔드 카드가 0.6667초 길어짐 (비율 +3.3%p). 대표 컷 상태는 같음.
2. **장면 11 `slot-roll` 간격.** 바뀜 4번 = 간격 3개인데 "`dur-l`로 시작해 한 번마다 짧아져 마지막 `dur-m`"을 만들려면 가운데 간격이 12와 6 사이여야 함 → docs에 없음. 새 숫자를 만들지 않고 `dur-l` · `dur-m` · `dur-m` (12 · 6 · 6)로 둠 — 두 번째 → 세 번째는 짧아지지 않음. director · 사람 판단 필요 (새 후보로 사이 값을 받거나, 바뀜을 3번으로 줄이기).
3. **장면 2 → 3, 5 → 6, 6 → 7 겹침.** 장면표 시간은 그대로이고 겹침 프레임만 이웃 장면 쪽으로 냄: 장면2 `scene-out` 2.4–2.5 (장면3 위), 장면6 앞 `screen-dissolve` 5.8–6.0, 장면7 앞 `screen-dissolve` 8.1–8.3. 이 때문에 장면5 · 6의 "hold 없이 / 끝에서 dissolve"가 각 장면 마지막 6f를 씀.
4. **장면 3 → 4 크기.** 사람 결정대로 배율 맞추지 않음: `zoom-through` 끝 버튼 폭 약 814px → 장면4 × 2.8 = 890.4px (약 9% 커짐). 실제 장면3 마지막 프레임은 `ease-in` 11/12 지점이라 그보다 조금 작음.
5. **장면 6 대표 컷.** 사람 요청대로 첫 hold 첫 프레임 (6.0초 = 180f, 미션 카드 가운데). `cam-pan` 끝 (제출하기 가운데, 아래 약 450px 빈 바탕)은 7.3초부터 영상에 그대로 나옴.
6. **hold 1f 늘어남.** `transition` 뒤 1f 앞당김 때문 (위 표). 스냅보드 상태는 같음.

## check 경고 (그대로 둠)

- `first_frame_empty` — 0프레임은 장면1 첫 단어 `scale-from` 0 (docs 움직임 그대로).
- `film_silent` — 소리 없음 (이 하네스 범위 밖).
- `line_unread` 5건 — "바로 써먹는 스킬" 0.70초 (`hold-s`), `slot-roll` 단어 0.2–0.4초 (간격 `dur-l` · `dur-m`), "나의 자산으로" 0.84초 (`hold-m` + `scene-out`). 모두 motion.md 값이라 바꾸지 않음.
