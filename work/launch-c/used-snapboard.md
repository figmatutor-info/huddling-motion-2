# used — snapboard · launch-c (안 a · 5장면 · 18.52초)

결과: `work/launch-c/snapboard.html` (1920×1080 컷 12장, 장면 순서대로) · `work/launch-c/snap/01.png` · `02a` · `02b` · `03a`–`03e` · `04a` · `04b` · `05a` · `05b` · `work/launch-c/snapboard.png` (4열 × 3줄, 칸마다 `번호 · 시작–끝 · 장면 이름`).
캡처: playwright-core 1.63 + Chrome for Testing (chromium-1248, headless), `--allow-file-access-from-files`, `document.fonts.ready` (본문 + iframe 전부) · 이미지 decode 뒤 `section.cut`마다 요소 캡처. 그리드도 같은 Chrome으로 캡처.
대표 컷 = 그 머묾(hold)의 첫 프레임. 04b만 요청에 따라 `hold-l` 끝(= `cam-dolly-out` 끝, `dolly-scale` 상태).

## 장면별

| 컷 | 배경 (video.md 2장) | 글자 (video.md 3장) | 크기 · 배치 (video.md 3 · 5장) | 머묾 상태 · 움직임 · 카메라 (motion.md) | 불러온 src |
|---|---|---|---|---|---|
| 01 | `video-bg-soft` | 부품 안 "승인 완료"만 (`Text/caption` 12 × 2.8 = 33.6px ≥ `video-text-min`) | brand-icon 칸 274.4 × 3칸 · 2줄, 칸 사이 `video-gap` 56 → 격자 935.2×604.8 화면 가운데 (x 492.4 · y 237.6) · 칸마다 badge-approved × 2.8 = 302.4×89.6 칸 가운데 | `cam-pull` 끝 (× 1) → `flip-wave` (`flip-turn` · `stagger`) 끝 → `hold-s` 첫 프레임. 뒤: 격자 `scale-from` 나감 → `transition` | `src/parts/badge-approved.html` × 6 (뒤집히기 전 `src/parts/brand-icon.html`은 이 컷에 안 보임) |
| 02a | `video-bg-soft` | 없음 | brand-icon × 2.8 = 274.4 화면 가운데 | `cam-release` 끝 (`cut-scale` → × 1) → `icon-spin` (`spin` + 고리, 고리는 투명도 0으로 끝남) → `hold-s` 첫 프레임 | `src/parts/brand-icon.html` |
| 02b | `video-bg-soft` (5장 skill-card 규칙) | 부품 안 글자만 (최소 caption 33.6px) | skill-card-1 × 2.8 = 980×246.4 화면 가운데 | `cam-pan` 오른쪽 끝 → `hold-m` 첫 프레임 | `src/parts/skill-card-1.html` |
| 03a | `video-bg-soft` | 부품 안 "제출하기" (label 39px) | button-submit × 2.8 = 980×123.2 화면 가운데 | ① `cam-pan` 끝 → `button-press` 앞 `hold-m` 첫 프레임 | `src/parts/button-submit.html?state=submit` |
| 03b | `video-bg-soft` | 부품 안 글자만 (최소 caption 33.6px) | mission-card × 2.8 = 980×708.4 화면 가운데 | ② `cam-pan` → 진행 바 · 글자 `emphasis` (`mission-in` 뒷부분) 끝 (`--progress` 1) → `hold-m` 첫 프레임 | `src/parts/mission-card.html` (`--progress` 1 · 진행 글자는 아래 "이름 없이 넣은 값") |
| 03c | `video-bg-soft` | 부품 안 "승인 완료" (33.6px) | badge-approved × 2.8 = 302.4×89.6 화면 가운데 | ③ `cam-pan` → `badge-pulse` (`scale-from` → 1) 끝 → `hold-s` 첫 프레임 | `src/parts/badge-approved.html` |
| 03d | `video-bg-soft` (5장 stat-card 규칙) | 부품 안 글자만 (최소 label 39px) | stat-card × 2.8 = 980×282.8 화면 가운데 | ④ `cam-pan` → `count-up` 끝 (`data-final` "29,700") → `hold-s` 첫 프레임 | `src/parts/stat-card.html` |
| 03e | `video-bg` (`pan-bg-shift` 끝, video.md 5장 예외 · asset-card 규칙) | 부품 안 글자만 (최소 eyebrow "파일" 11 × 2.8 = 30.8 → 31px) | asset-card × 2.8 = 980×207.2 화면 가운데 | ⑤ `cam-pan` + `pan-bg-shift` (`video-bg-soft` → `video-bg` · `dur-l` · `ease-linear`) 끝 → `hold-m` 첫 프레임 | `src/parts/asset-card.html?state=selling` |
| 04a | `video-bg-soft` | 부품 안 글자만 (× 1이라 모두 31px 이상) | 가운데 brand-icon × 2.8 · 둘레 5개 × 2.8, 화면 가장자리에 반쯤 잘림 (자리는 아래 "이름 없이 넣은 값") · asset-card 뺌 (5장) | `cam-release` 끝 → 둘레 `part-in` · `stagger` 끝 → `hold-l` 첫 프레임 (× 1, `cam-dolly-out` 시작 프레임) | `src/parts/brand-icon.html` · `skill-card-1.html` · `stat-card.html` · `badge-approved.html` · `button-submit.html?state=submit` · `mission-card.html` (`--progress` 1) |
| 04b | `video-bg-soft` | 부품 글자 31px 미만 (video.md 1장 예외: `cam-dolly-out`으로 × 1 아래) | 04a와 같은 자리 · 카메라 × `dolly-scale` 0.5 (화면 가운데 기준) → 그물 전체 화면 안 | `hold-l` 끝 = `cam-dolly-out` 끝. 뒤: 그물만 `scene-out` → 절반에서 `match-cut` | 04a와 같음 |
| 05a | `video-bg-end` (`video-bg-dark` + `video-glow` + `video-grain`) | 없음 | brand-icon × 2.8 화면 가운데 (`match-cut` 뒤 원래 크기) | `icon-spin` 끝 → `hold-s` 첫 프레임 · `cam-hold`. 뒤: brand-icon `exit` → `end-reveal` | `src/parts/brand-icon.html` |
| 05b | `video-bg-end` | 슬로건 "오늘도 하나씩, 내 실력으로" `video-title` · `video-text-on-dark` · 가운데 한 줄 (엔드 카드 예외) | logo logotype-white `logo-hero` × 6 = 894×114 · `video-gap-end` 48 · 슬로건 행간 90 → 묶음 252 높이 화면 가운데 (logo y 414–528 · 슬로건 y 576–666) · logo 색 규칙 (`*-white`) | `end-reveal` (`logo-reveal` 글자 `enter` · `stagger` → `dur-l` → 슬로건) 끝 → `hold-end` 첫 프레임 · `cam-hold` | `src/parts/logo.html?state=logotype-white` · 폰트 `src/assets/fonts/Pretendard-SemiBold.otf` |

## 쓴 이름

- video.md: 1장 `video-scale` · `video-text-min` (+ `cam-dolly-out` 예외) / 2장 `video-bg` · `video-bg-soft` · `video-bg-dark` · `video-bg-end` · `video-glow` · `video-grain` / 3장 `video-title` · `video-text-on-dark` · `video-gap` · `video-gap-end` / 5장 `logo-hero` · 배율 × 2.8 · 바탕 규칙 (stat · skill → soft, asset → bg) · `pan-bg-shift` 예외
- motion.md: 1장 `dolly-scale` (04b에서 값으로 씀) · 컷 상태로만 보이는 `cut-scale` · `scale-from` · `flip-turn` · `spin` · `dur-l` · `ease-linear` / 2장 `stagger` · `emphasis` · `transition` · `exit` / 3장 `flip-wave` · `icon-spin` · `button-press` · `mission-in` · `badge-pulse` · `count-up` · `part-in` · `scene-out` · `match-cut` · `end-reveal` · `logo-reveal` / 4장 `hold-s` · `hold-m` · `hold-l` · `hold-end` / 5장 `cam-pull` · `cam-release` · `cam-pan` · `cam-dolly-out` · `cam-hold`
- design.md: 1장 (부품 안 색, 부품 원본 그대로) · 3장 A 로컬 폰트 로드 (Pretendard 600)

## 이름 없이 넣은 값 (숨기지 않음)

| 컷 | 값 | 왜 |
|---|---|---|
| 01 | 격자 left 492.4 · top 237.6 | (1920 − 935.2) / 2 · (1080 − 604.8) / 2, 화면 가운데 계산 |
| 03b · 04 | 진행 글자 "100% · 4/4 단계 완료" | `emphasis` 최종값. 부품에는 최종 글자가 없어 `src/screens/04-approved.png` 속 같은 카드 문구를 그대로 씀 (iframe 안 `#mission-card-progress-text` textContent만 바꿈, 부품 파일은 그대로). 부품 주석은 `--progress`만 말함 → 판단 필요 |
| 04a · 04b | 둘레 부품 가운데 점: skill-card-1 (400, 0) · stat-card (1520, 0) · badge-approved (1920, 540) · button-submit (960, 1080) · mission-card (0, 540) | 장면표 "× 1에서 가장자리에 반쯤 잘리고 `dolly-scale`에서 전부 화면 안"을 만족하도록 고른 배치. 가운데 점을 화면 가장자리 위에 둠 (위 두 장은 서로 · brand-icon과 겹치지 않게 x를 나눔). docs에 이름 있는 값 아님 |
| 05a · 05b | `video-glow` 표기 `rgba(55, 89, 222, 0.45 → 0)` | `#3759de`에 2장 불투명도를 거는 표기 |

## 판단이 필요한 곳

1. 03b · 04 mission-card 진행 글자 최종값 (위 표).
2. 04 그물 배치는 docs 값이 아닌 구도 선택. 둘레 순서(시계 방향 skill → stat → badge → button → mission)는 `part-in` · `stagger` 순서로 영상에서 그대로 쓸 예정.
3. 01 컷은 머묾 상태라 brand-icon(뒤집히기 전)이 안 보임. flip 중간은 영상에서 확인.
4. 새 후보 0 · src 고친 것 0 · docs 고친 것 0 · 화면에 없는 UI 0.
