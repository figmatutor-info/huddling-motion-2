# used — video · launch-c (안 a · 5장면 · 18.6667초 = 560프레임 · 30fps · 1920×1080)

결과: `work/launch-c/video/` (HyperFrames 0.8.191 · `index.html` + `compositions/s1.html` – `s5.html`) · 미리보기 `cd work/launch-c/video && npx hyperframes preview`. mp4 렌더 안 함.
`npx hyperframes check` = ok (오류 0 · 경고 3, 아래).
머묾 프레임 `work/launch-c/video-frames/01.png` · `02a` · `02b` · `03a`–`03e` · `04a` · `04b` · `05a` · `05b` (스냅보드 `snap/`와 같은 이름 · 같은 순간) + 움직임 중간 `m*.png` 7장 (아래). 캡처: `npx hyperframes snapshot --at` (브라우저 캡처, 프레임 시각 + 0.01f).
src: `video/assets/src/` = 저장소 `src/`를 바이트 그대로 복사 (쓰는 것만: parts brand-icon · badge-approved · skill-card-1 · button-submit · mission-card · stat-card · asset-card · logo, assets 폰트 3 · logo svg 4 · perdi-flag · buddy-front-1 · 2). parts는 iframe, 상태는 `?state=` · `--progress` · `textContent`로만.
스냅보드와 같은 순간 비교 (픽셀 차, 0–255 평균): 01 0.00 · 02a 0.04 · 02b 0.01 · 03a 0.05 · 03b 0.17 · 03c 0.01 · 03d 0.35 · 03e 0.07 · 04a 0.06 · 04b 0.01 · 05a 0.15 · 05b 0.32 (글자 가장자리 · grain 위 가장자리뿐, 상태 · 자리 같음).

## 장면별

| # · 파일 | 시간 (전체 프레임) | 배경 · 글자 · 크기 (video.md) | 움직임 · 카메라 (motion.md, 장면 안 프레임) | 불러온 src | 머묾 프레임 |
|---|---|---|---|---|---|
| 1 · s1 | 0.00–2.10 (0–63) | `video-bg-soft` · 격자 칸 274.4 × 3 · 2줄 · `video-gap` 56 · 화면 가운데 · badge 글자 33.6px ≥ `video-text-min` | `cam-pull` (`cam-in` × 2.4 · 대상 첫 줄 가운데 칸 → × 1, `dur-l` · `ease-inout`) 0–12 → `flip-wave` (칸마다 `flip-turn` × 3 · `dur-m` · `ease-out` · 90°에서 앞면 → badge-approved · 대각선 `stagger`) 12–48 → `hold-s` 48–60 → 깊이 컷 나감 (격자 `scale-from` · `dur-s` · `ease-in`) 60–63 → `transition` | `src/parts/brand-icon.html` × 6 · `src/parts/badge-approved.html` × 6 | 48f = 01 |
| 2 · s2 | 2.10–5.00 (63–150) | `video-bg-soft` (5장 skill-card 규칙) · brand-icon × 2.8 · skill-card-1 × 2.8 = 980×246.4 | `cam-release` (`cut-scale` → × 1, `dur-2xl` · `ease-out`) 0–30 → `icon-spin` (`spin` `dur-m` · `ease-out` 30–36 + 고리 `color-primary` × 1 → `cut-scale` · 0.45 → 0 · `dur-l` · `ease-out` 30–42) → `hold-s` 42–54 → `cam-pan` 오른쪽 (`dur-l` · `ease-inout`) 54–66 → `hold-m` 66–87 | `src/parts/brand-icon.html` · `src/parts/skill-card-1.html` | 105f = 02a · 129f = 02b |
| 3 · s3 | 5.00–11.60 (150–348) | `video-bg-soft` → `video-bg` (`pan-bg-shift`, 5장 예외) · 부품 모두 × 2.8 · 부품 안 글자 최소 31px (asset "파일" eyebrow) | ① `cam-pan` 0–12 → `button-press` (앞 `hold-m` 12–33 · 누름 `press-scale` `dur-s` · `ease-in` 33–36 · 뗌 `dur-m` · `ease-out` 36–42) → ② `cam-pan` 42–54 → `emphasis` (`mission-in` 뒷부분, `--progress` 0.5 → 1) 54–60 → `hold-m` 60–81 → ③ `cam-pan` 81–93 → `badge-pulse` (`scale-from` → 1 · `dur-m` · `ease-out`) 93–99 → `hold-s` 99–111 → ④ `cam-pan` 111–123 → `count-up` (0 → 29,700 · `dur-2xl` · `ease-out` · 정수) 123–153 → `hold-s` 153–165 → ⑤ `cam-pan` + `pan-bg-shift` (`dur-l` · `ease-linear`) 165–177 → `hold-m` 177–198 → `transition` | `src/parts/skill-card-1.html` · `button-submit.html?state=submit` · `mission-card.html` · `badge-approved.html` · `stat-card.html` · `asset-card.html?state=selling` | 162 = 03a · 210 = 03b · 249 = 03c · 303 = 03d · 327 = 03e |
| 4 · s4 | 11.60–14.8667 (348–446) | `video-bg-soft` · brand-icon + 그물 5개 × 2.8 · asset-card 뺌 (5장) · `cam-dolly-out` 동안 × 1 아래 글자 31px 미만 (1장 예외) | `cam-release` (× 1.7 → × 1, `dur-2xl` · `ease-out`) 0–30 → 둘레 `part-in` (`enter` + 위 `dist-m` · 투명도, `dur-m` · `ease-out`) · 시계 방향 `stagger` 30–60 → `hold-l` 60–96 동안 `cam-dolly-out` (× 1 → `dolly-scale` · `ease-linear`) → 그물만 `scene-out` (`exit` · `dur-s` · `ease-in`) 96– → 98에서 `transition` (`match-cut`) | `src/parts/brand-icon.html` · `skill-card-1.html` · `stat-card.html` · `badge-approved.html` · `button-submit.html?state=submit` · `mission-card.html` (`--progress` 1) | 408 = 04a · 444 = 04b |
| 5 · s5 | 14.8667–18.6667 (446–560) | `video-bg-end` (`video-bg-dark` + `video-glow` + `video-grain`) · brand-icon × 2.8 · logo logotype-white `logo-hero` 894×114 · `video-gap-end` 48 · 슬로건 `video-title` · `video-text-on-dark` · 가운데 한 줄 (3장 엔드 카드 예외) · logo 색 규칙 (5장) | `match-cut` 뒤 `icon-spin` 0–12 → `hold-s` 12–24 → brand-icon `exit` 24–27 → `end-reveal` (`logo-reveal` 엔드 카드: 글자마다 `enter` (`mask-rise`), `stagger` `dur-xs`, 7번째부터 같이 27–45 → `dur-l` 뒤 슬로건 투명도 0 → 1 · `dur-l` 57–69) → `hold-end` 69–114 · 마지막 hold 정지 (4장 예외) · `cam-hold` | `src/parts/brand-icon.html` · `src/parts/logo.html?state=logotype-white` (같은 iframe 13개 글자 칸) · 폰트 `src/assets/fonts/Pretendard-SemiBold.otf` | 458 = 05a · 515 = 05b |

## 움직임 중간 프레임 (요청)

| 파일 | 시각 (전체 프레임) | 무엇 |
|---|---|---|
| `m1-flip-wave.png` | 1.00 (30) | 장면1 `flip-wave` 중간 (반은 badge, 반은 brand-icon) |
| `m12-depth-cut-out.png` | 2.0667 (62) | 1→2 깊이 컷: 격자 `scale-from` 나감 마지막 프레임 |
| `m12-depth-cut-in.png` | 2.10 (63) | 1→2 깊이 컷 뒤 첫 프레임: brand-icon `cut-scale` (`cam-release` 시작) |
| `m3-pan-bg-shift.png` | 10.70 (321) | 장면3 ④ → ⑤ `cam-pan` + `pan-bg-shift` 중간 (stat-card 위로 빠짐 · asset-card 들어옴 · 바탕 중간색) |
| `m4-dolly-out.png` | 14.20 (426) | 장면4 `cam-dolly-out` 중간 (× 0.75) |
| `m45-match-cut-out.png` | 14.8333 (445) | 4→5 `match-cut` 앞: 그물 `scene-out` 진행 중 · brand-icon `dolly-scale` 크기 |
| `m45-match-cut-in.png` | 14.8667 (446) | 4→5 `match-cut` 뒤 첫 프레임: `video-bg-end` 위 brand-icon 원래 크기 (크기 튐 — log.md "확인용 · 고치지 않음" 그대로) |

## 쓴 이름

- video.md: 1장 `video-scale` · `video-text-min` (+ `cam-dolly-out` 예외) / 2장 `video-bg` · `video-bg-soft` · `video-bg-dark` · `video-bg-end` · `video-glow` · `video-grain` / 3장 `video-title` · `video-text-on-dark` · `video-gap` · `video-gap-end` / 5장 parts 크기 표 · 바탕 규칙 (skill · stat → soft, asset → bg) · `pan-bg-shift` 예외 · `logo-hero` · logo 색 규칙
- motion.md: 1장 `dur-xs` · `dur-s` · `dur-m` · `dur-l` · `dur-2xl` · `ease-out` · `ease-in` · `ease-inout` · `ease-linear` · `mask-rise` · `dist-m` · `press-scale` · `scale-from` · `cam-in` · `cut-scale` · `flip-turn` · `spin` · `dolly-scale` / 2장 `enter` · `exit` · `emphasis` · `transition` · `stagger` / 3장 `flip-wave` · `icon-spin` · `button-press` · `mission-in` · `badge-pulse` · `count-up` · `part-in` · `scene-out` · `match-cut` · `logo-reveal` · `end-reveal` / 4장 `hold-s` · `hold-m` · `hold-l` · `hold-end` / 5장 `cam-pull` · `cam-release` · `cam-pan` · `cam-dolly-out` · `cam-hold`
- design.md: 1장 `color-primary` (`icon-spin` 고리) / 3장 A 로컬 폰트 로드 (Pretendard 400 · 600 · 700) / 4장 `radius-card` (고리 모서리 12 × 2.8)
- 새 후보 0 · src 고친 것 0 · docs 고친 것 0 · 화면에 없는 UI 0 (고리는 motion.md 3장 `icon-spin` 안의 요소).

## 이름 없이 넣은 값 (숨기지 않음)

| 장면 | 값 | 왜 |
|---|---|---|
| 1 | 격자 left 492.4 · top 237.6 · `cam-pull` 대상 점 (960, 374.8) | 스냅보드와 같은 화면 가운데 계산 · 첫 줄 가운데 칸 가운데 |
| 1 | `flip-turn` × 3 = rotateY 540° 를 한 `dur-m`에 돌림 · 보이는 각도는 180° 단위로 접어 (−90°–90°) 면이 거울상이 되지 않게 함 · 앞면 바뀜은 처음 90° 지나는 프레임 | motion.md 3장 `flip-wave` "flip-turn × 3 · dur-m · 90°에서 앞면이 다음 상태로" 해석 |
| 1 | 대각선 순서 (1줄1칸) → (1줄2칸) → (2줄1칸) → (1줄3칸) → (2줄2칸) → (2줄3칸), 칸마다 `dur-m` 차이 | 장면표 길이 1.2초 (6개 `stagger` + 마지막 `dur-m`)와 맞춤. 같은 대각선 칸도 한 칸씩 띄움 |
| 2 · 5 | `icon-spin` 고리 모양 = brand-icon 외곽과 같은 274.4 정사각 · 모서리 33.6 (`radius-card` × 2.8)을 `color-primary`로 **채운** 판을 아이콘 뒤에 둠 → 아이콘 밖으로 번지는 띠만 보임 | docs에 고리 선 굵기가 없어 선을 그리지 않음. 판단 필요하면 critic |
| 2 · 3 | 월드 자리: brand-icon (960, 540) · skill-card-1 (2880, 540) · 장면3 skill-card-1 (960, 540) → ① (0, 1620) → ② (960, 2700) → ③ (0, 3780) → ④ (960, 4860) → ⑤ (0, 5940) | 장면표 "한 화면 폭 너머" = 1920 · "지그재그 · 멈춘 프레임에 부품 하나만" → 가로 960 · 세로 1080 (한 화면 높이)로 고름. docs 값 아님 |
| 3 | `pan-bg-shift` 중간색 = `#f7f7f8` → `#ffffff` RGB 직선 보간 (예: 10.70초 `#fbfbfc`) | `ease-linear` 바탕 바뀜의 중간 프레임 |
| 3 | mission-card 진행 글자: `emphasis` 동안 `${pct}% · ${floor(pct/25)}/4 단계 완료` (50% · 2/4 → 100% · 4/4) | 시작값은 부품 원본 · 최종값은 스냅보드와 같음 ("04-approved.png" 문구). 중간 글자 형식은 builder 판단 |
| 3 | `count-up` 숫자 형식 `toLocaleString("en-US")` (29,700) · 펼치기 전 "0" | 부품 `data-final` 형식과 같게 |
| 4 | 둘레 가운데 점 skill (400, 0) · stat (1520, 0) · badge (1920, 540) · button (960, 1080) · mission (0, 540) | 스냅보드 04a · 04b와 같은 값 (used-snapboard.md) |
| 4 | `match-cut` 컷 = `scene-out` 시작 + 2f | `dur-s` 3f의 절반 1.5f 뒤 첫 정수 프레임 (launch-b `cut-in-motion`과 같은 방식) |
| 5 | logo 글자 칸 경계 (svg 좌표) 0 · 17.605 · 34.345 · 46.395 · 58.185 · 70.185 · 75.385 · 80.605 · 92.685 · 105.765 · 120.84 · 125.705 · 137.535 · 149 | launch-b · launch-30s에서 잰 값 그대로 (같은 svg 파일). 같은 logo.html iframe 13개를 clip-path로 자름 |
| 5 | `video-glow` 표기 `rgba(55, 89, 222, 0.45 → 0)` | `#3759de`에 2장 불투명도를 거는 표기 (스냅보드와 같음) |

## 장면표 · 스냅보드와 다르게 된 곳

1. **전체 길이 18.52 → 18.6667초 (+4.4f).** 장면표 시작–끝을 프레임으로 맞추며 생김:
   - 장면4 끝: 장면표 0.05초 = `scene-out` 절반 1.5f → 정수 프레임 2f (+0.5f). 장면4 = 98f (3.2667초), 장면5 시작 14.8667.
   - 장면5 길이: 장면표 "logo 글자 `stagger` 약 0.47 (글자 5개 기준)" → logotype "Huddling Club" 글자 칸은 13개, motion.md 2장대로 7번째부터 같이 = `dur-xs` × 6 + `dur-m` = 18f (0.6초) (+4f). 장면5 = 114f (3.8초). `hold-end`는 docs 값 그대로.
   - 장면1 · 2 · 3은 장면표와 같음 (63 · 87 · 198f). 비율: 장면5 19.8% → 20.4% (비트 시트 15.8%와 차이 +4.6%p, ±5%p 안).
2. 스냅보드 "확인용 · 고치지 않음" 3건(장면1 · 03a · 03c · 03e 부품이 작음 · 04a 잘린 글자 · 4→5 크기 튐)은 그대로 둠.

## check 경고 (그대로 둠)

- `first_frame_empty` — check 표본이 부품 iframe 로드 전 0프레임을 봄. 실제 0프레임 캡처는 brand-icon 격자 × 2.4 (확인함).
- `film_silent` — 소리 없음 (이 하네스 범위 밖).
- `line_unread` — 슬로건이 1.83초 보임 (`dur-l` 들어옴 + `hold-end` 1.5초). docs 값이라 바꾸지 않음.
