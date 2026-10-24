# used — video · launch-30s (8장면 · 17.6초 · 528프레임)

다시 렌더 (2026-10-24, 2회째): 장면2에 첫 프레임부터 button-submit `apply-case` + 덮개판을 화면 이미지 속 버튼 자리에 겹치고, `cam-crane` 끝 → `hold-m` → `button-press` → 컷으로 바꿈 (2.3초 → 2.0초, `scene-out` 없음). 3~8장은 내용 그대로 시작만 0.3초 당김 (index.html `data-start`만 바꿈). 경계 0 / 2.7 / 4.7 / 7.7 / 8.7 / 10.9 / 12.6 / 14.7 / 17.6.

결과: `work/launch-30s/out.mp4` (H.264 · yuv420p · 1920×1080 · 30fps · 17.600초 · 528프레임, ffprobe로 확인) · 프로젝트 `work/launch-30s/video/`
머묾 프레임: `work/launch-30s/video-frames/01.png` · `02a.png` · `02b.png` · `02c.png` · `03.png` · `03b.png` · `03c.png` · `04.png` … `08.png` (스냅보드 `snap/`과 같은 이름, 폴더를 비우고 다시 뽑음). out.mp4에서 ffmpeg로 프레임 번호 그대로 뽑음
렌더: HyperFrames 0.8.191, `npx hyperframes render -f 30 -q delivery`. 소리 없음 (장면표에 소리가 없어서).

## 공통

- 폰트: Pretendard 400 · 600 · 700, 로컬 파일 `src/assets/fonts/Pretendard-*.otf`를 `@font-face`로 (design.md 3장 A · video.md 3장). 장면마다 `document.fonts.ready` + 부품 iframe 안 `fonts.ready` · 이미지 decode를 기다린 뒤 timeline 등록 (첫 프레임 전)
- src 불러오기: `src/parts` · `src/assets` · `src/screens`를 `video/assets/src/`에 바이트 그대로 복사 (`diff -r` 같음, `_check/`만 뺌). 부품은 iframe으로 원본 HTML 그대로, 상태는 `?state=`로만, 배율 `video-scale` × 2.8을 iframe 전체에 한 번 (video.md 5장)
- 줄바꿈 `word-break: keep-all` · 정렬 규칙 (video.md 3장)
- Easing: `ease-out` · `ease-in` · `ease-inout` · `ease-linear` (motion.md 1장) 값 그대로를 cubic-bezier 함수로 GSAP에 넘김
- 장면 경계: 2→3은 `button-press` 뗌 끝 프레임에서 `transition` (컷, `scene-out` 없음, motion.md 3장). 나머지는 `cut-in-motion` (motion.md 3장): `scene-out`(= `exit` · `dur-s` · `ease-in` · 투명도 1 → 0, motion.md 2장)이 절반 진행된 때 = scenes.md 장면 끝
- 프레임 수: 30fps 기준 motion.md 1장 · 4장 프레임 값 그대로

## 장면별

| # | 시간 | 배경 · 글자 (video.md) | 움직임 · 카메라 (motion.md) | 불러온 src |
|---|---|---|---|---|
| 1 | 0.0–2.7 | `video-bg-soft` (2장) · `video-display` · `video-text`, "실력" `video-text-accent` · 가운데 (3장) | `text-type` (3장: `type-step` = `dur-s` 3f마다 한 글자, 커서 폭 6 · 띄움 6 · 높이 `video-display` 행간 95) + `cam-in` × 2.4 상태에서 `cam-follow` (`ease-linear`) → `cam-pull` (`dur-l` · `ease-inout`) (5장 · 1장) → `hold-m` (4장) → `scene-out` | `src/assets/fonts/Pretendard-Bold.otf` (폰트만) |
| 2 | 2.7–4.7 (60f) | `video-bg-soft` · 폰 `phone-size` · `phone-screen` · `phone-bezel` · `phone-radius` · `phone-color` · `phone-screen-bg` (4장) · 폰 하나 화면 가운데 (3장, 폰 x 738–1182 · y 76–1004) · 영상 글자 없음 · 첫 프레임부터 덮개판 (4장 예외 줄: 같은 모서리 · 사방 1px@1x 크게 · 색 `phone-screen-bg` = `color-bg` #ffffff) + button-submit `apply-case`를 `phone-screen` 배율 1.066 (4장)으로 화면 이미지 속 버튼 자리에 겹침, 둘 다 폰 안 (폰과 함께 기울고 줌됨) | 폰 `crane-angle` (1장: rotateX 12° · rotateY -18° · perspective 2400px · 회전 중심 폰 가운데) + 아래 `dist-l` 70px (1장) · × 1 로 시작 → `cam-crane` (5장: 각도 · 위치 · 줌 같은 진행값, `dur-2xl` 30f · `ease-inout`, 끝 = 각도 0 · `cam-in` × 2.4, 대상 = 01-home 미션 카드 영역) → `cam-pull` 생략 → `cam-in` 상태 `hold-m` 21f (4장 · 3장 `button-press` 앞 hold) → `button-press` (3장: 누름 1 → `press-scale` 0.96 (1장) · `dur-s` 3f · `ease-in`, 뗌 0.96 → 1 · `dur-m` 6f · `ease-out`, 중심 버튼 가운데, 부품만 — 덮개판 고정) → 뗌 끝 = 2.0초 = 장면3 첫 프레임 `transition` (컷) | `src/screens/01-home.png` · `src/parts/button-submit.html?state=apply-case` |
| 3 | 4.7–7.7 | `video-bg-soft` · 부품 안 글자만 · 카드 사이 `video-gap` | `cam-hold` · 카드 등장 없음 · `skill-carousel` (3장: 거리 980 + 56 = 1036 · `dur-l` · `ease-inout`, 카드마다 `hold-m`) → `scene-out` | `src/parts/skill-card-1.html` · `skill-card-2.html` · `skill-card-3.html` |
| 4 | 7.7–8.7 | `video-bg-soft` · 부품 안 글자만 | `cam-hold` · `part-in` → `hold-m` → `scene-out` | `src/parts/button-submit.html?state=submit` |
| 5 | 8.7–10.9 | `video-bg-dark` → `video-bg-soft` · `video-display` · `video-text-on-dark` → `video-text` · 가운데 | `dark-cut` (3장: 제목 `enter` → `hold-s` → 바탕 · 글자 색 `dur-xl` · `ease-linear`) → `hold-m` → `scene-out` | 폰트만 |
| 6 | 10.9–12.6 | `video-bg-soft` · 부품 안 글자만 | `cam-hold` · `part-in` → 바로 `count-up` (3장: 0 → `data-final` 29,700 · `dur-2xl` · `ease-out` · 정수) → `hold-s` → `scene-out` | `src/parts/stat-card.html` (원본 그대로, `#stat-card-amount` textContent만 바꿈) |
| 7 | 12.6–14.7 | `video-bg` (5장 asset-card 규칙) · 부품 안 글자만 · 카드 사이 `video-gap` | `cam-hold` · `asset-list` (= `skill-list`: 카드마다 `enter` + 위 `dist-m` · 투명도, `stagger` `dur-m`) → `hold-l` → `scene-out` | `src/parts/asset-card.html?state=private-image` · `review` · `selling` · `private-file` |
| 8 | 14.7–17.6 | `video-bg-end` = `video-bg-dark` + `video-glow` + `video-grain` (2장) · `logo-hero` × 6 (5장) · 슬로건 `video-title` · `video-text-on-dark` · 가운데 · `video-gap-end` | `end-reveal` (3장: `logo-reveal` 엔드 카드 = logo 글자마다 `enter`, 글자 사이 `stagger` `dur-xs`, 7번째부터 같이 → `dur-l` 뒤 슬로건 투명도 0 → 1 · `dur-l`) → `hold-end` → 정지 (4장 예외) | `src/parts/logo.html?state=logotype-white` (같은 iframe 13개, 아래 참고) |

프레임 확인 (video-frames 뽑은 프레임): 01 = 72f · 02a = 81f (2.7초, `cam-crane` 시작) · 02b = 121f (장면2 40f, `hold-m` 중) · 02c = 135f (장면2 54f, 누름 끝 0.96) · 03 / 03b / 03c = 153 · 186 · 219f · 04 = 252f · 05 = 321f · 06 = 369f · 07 = 429f · 08 = 516f. 140f(장면2 마지막, 뗌 5/6) → 141f(장면3 첫 프레임) 컷 확인.

스냅보드 비교 (PSNR): 02a 46.5dB · 02b 38.6dB · 02c 37.5dB · 03 52.1 · 04 44.0 · 08 34.7 (08은 grain) — 눈으로 같은 그림 (차이는 H.264 인코딩 · 확대 리샘플링 정도). 3~8장은 이전 렌더와 같은 코드 · 같은 프레임 상태.

## 이름 없이 넣은 값 (숨기지 않음)

| 장면 | 값 | 왜 · 어디서 |
|---|---|---|
| 2 빼고 전부 | `scene-out` 시작 = 장면 끝 − 1.5f (`dur-s` 절반) → 마지막 hold가 docs 값보다 1.5f 김 (예: 1장 `hold-m` 21f → 22.5f) | scenes.md 길이는 `exit` 3f 전부를 더한 합인데, `cut-in-motion`은 절반에서 컷. 장면 경계를 scenes.md 그대로 지키려고 남는 1.5f를 hold에 붙임 |
| 1 | `cam-follow` 초점 = 커서 가운데 (가로) · 줄 가운데 (세로 540). 첫 글자 때 커서 → 끝 글자 나타나는 때(42f) 커서까지 일직선, 42–45f 멈춤, 45f부터 `cam-pull` | motion.md 5장은 "커서 쪽으로 · 글자 늘어나는 속도 그대로"만 있고 초점 위치 · 시작 끝 프레임은 없음 |
| 1 | 커서는 깜빡이지 않고 hold · scene-out 동안 그대로 보임 | 스냅보드 머묾 컷과 같게. 깜빡임 값은 docs에 없음 |
| 2 | `cam-in` 대상 점 = 01-home.png 안 미션 카드 영역 가운데 (이미지 780×1688 기준 x 390 · y 841, 카드 x 40–740 · y 588–1094를 이미지에서 잼) → 영상 좌표 (960, 538.4) (폰 가운데로 옮겨져 바뀜, 스냅보드 02b와 같은 값) | scenes.md "01-home 미션 카드 영역". 점 좌표는 docs에 없어 src 이미지에서 잼 (이전과 같은 점) |
| 2 | `cam-crane` 줌의 보간 방식 = 카메라 초점을 화면 가운데(960, 540) → 대상 점으로, 배율 1 → 2.4를 같은 진행값으로 일직선 (원점 0 0 `translate(960 − 초점x × 배율, 540 − 초점y × 배율) scale(배율)`, 1장 `cam-pull`과 같은 식을 거꾸로). 폰의 `translateY` · `rotateX` · `rotateY`도 같은 진행값으로 일직선 | motion.md 5장 "각도 · 위치 · 줌이 같은 시간에 같은 곡선으로"까지 docs. 줌을 초점 기준으로 보간할지 translate 값 기준으로 보간할지는 docs에 없음 (이번 장면은 대상 x가 960이라 두 방식 차이가 세로 1.6px 이내) |
| 2 | 폰의 `perspective`는 폰 자신의 transform 안에 (`perspective(2400px) rotateX rotateY`), 카메라 층 배율은 그 바깥에 걸림 | 스냅보드 02a CSS와 같은 짜임 |
| 2 (새) | 겹침 자리 = 화면 이미지 속 버튼을 잰 값 (이미지 780×1688 안 x 74–709 · y 972–1059) → 폰 안 left 53.4667 · top 532.2464 · 339.2×46.9333, 덮개판 left 52.4 · top 531.1797 · 341.3333×49.0667 · 모서리 8.5333 (= 부품 8 × 1.066667, 덮개판이 1px 커도 모서리는 같게) | 스냅보드 `.overlay-btn` · `.overlay-cover`와 같은 값. 위치는 docs 이름 없음, src 이미지에서 잼 |
| 2 (새) | `button-press` 시작 = `cam-crane` 끝 + `hold-m` = 장면2 51f, 이 hold는 공통의 `scene-out` 1.5f 보정 없음 (컷이라) | 2→3 경계는 `cut-in-motion`이 아니어서 1.5f 줄은 장면2에 해당 없음 |
| 2 (새) | 뗌 끝(scale 1)은 60f = 장면3 첫 프레임 시각이라, 장면2에서 실제로 보이는 마지막 프레임(59f)은 뗌 5/6 진행 (`ease-out`이라 거의 1) | "떼는 끝 프레임에 transition" 해석 |
| 2·4·6·7 | `part-in` · `asset-list`의 "위 `dist-m`" = 위에서 24px 내려오며 (y −24 → 0) | motion.md 출처 "위에서 차례로 쌓임"으로 읽음. "위로 24px 올라옴"으로도 읽힐 수 있음 |
| 5 | 글자 색 #ffffff → #18191b 사이 중간색 (RGB 일직선 보간) | `dark-cut` "글자 색 같이 바뀜". 중간색은 전환 중에만 나옴 |
| 6 | 금액 표기 = 천 단위 쉼표 (`data-final` "29,700"과 같은 형식), `tabular-nums` 안 씀 | 부품 주석은 tabular-nums를 "장면에서 더한다"고 하지만 docs 값이 없어 넣지 않음 → 세는 동안 금액 폭이 조금씩 바뀜 (왼쪽 정렬이라 오른쪽 끝만 움직임) |
| 8 | logo 글자 나누기: logo.html을 13번 불러 각각 한 글자 칸만 `clip-path`로 보이게 함. 칸 경계(svg 좌표 0–149) = 0 · 17.605 · 34.345 · 46.395 · 58.185 · 70.185 · 75.385 · 80.605 · 92.685 · 105.765 · 120.84 · 125.705 · 137.535 · 149 (logo-logotype-white.svg path 경계 상자에서 이웃 글자 사이 가운데를 잼). 심볼(path 5개)을 한 글자로 셈 → 13글자 | `logo-reveal` "logo 글자마다 enter"인데 부품은 svg 한 장이라 글자 단위가 없음. 부품 · svg는 고치지 않음 |
| 8 | 슬로건 투명도 곡선 = `ease-out` | `end-reveal` "enter + 마스크 대신 투명도"라 `enter`의 이징을 그대로 씀 |
| 8 | `video-glow` 색 표기 `rgba(55, 89, 222, 0.45 → 0)` | 스냅보드와 같음. `#3759de`에 docs 불투명도를 거는 표기 |
| 공통 | 부품 iframe은 `data-src`에 적고 장면 스크립트가 붙을 때 `src`를 엶 | 렌더 설정일 뿐 화면 값 아님 |

## 렌더 · check 메모

- `npx hyperframes check`: error `request_failed` 22건 (이번 렌더도 같음) (부품 iframe 첫 로드가 장면을 붙이는 중 `ERR_ABORTED`로 끊기고 다시 로드됨). 렌더 프레임에서는 모든 부품이 정상으로 그려짐 (아래 비교). 경고 `line_unread` 2건 (1장 · 8장 hold가 HyperFrames 권장 읽기 시간보다 짧음 — hold는 motion.md 4장 값이라 그대로 둠) · `film_silent` (소리 없음) · info 2건 (1장 카메라 확대로 화면 밖으로 나가는 것, 의도 · 2장은 `data-layout-allow-overflow` 표시)
- 6장 count-up과 1 · 2장 카메라는 장면 시간 t 하나로 계산 (어느 프레임으로 바로 가도 같은 그림)
