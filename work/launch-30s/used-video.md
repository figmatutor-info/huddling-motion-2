# used — video · launch-30s (10장면 · 21.7초 · 651프레임)

이번 회차 (2026-10-24, 승인 2 스냅보드 기준): 장면표 10장면에 맞춰 HyperFrames 프로젝트를 고침. mp4 렌더는 하지 않음 (`out.mp4`는 이전 8장면 렌더가 남아 있는 것, 이번 프로젝트와 다름).
경계 0 / 2.7 / 4.7 / 7.7 / 10.3 / 11.7 / 12.4 / 14.6 / 16.3 / 18.4 / 21.7 (index.html `data-start` · `data-duration`, 루트 21.7).

- 장면 1–3: 그림 · 시간 그대로. 3장만 구현 한 줄 바뀜 (아래 "구현 메모").
- 장면 4 (새) `compositions/s4.html`: slot-roll
- 장면 5 (바뀜, 옛 4장 파일에서) `compositions/s5.html`: button-submit `part-in` → `hold-m` → `shape-morph` 앞부분
- 장면 6 (새) `compositions/s6.html`: badge-approved `shape-morph` 뒷부분
- 장면 7–9 = 옛 5–7장 (dark-cut · stat-card · asset-card). 내용 그대로, 파일 이름 · id만 s5→s7 · s6→s8 · s7→s9, 시작 시각만 밀림
- 장면 10 = 옛 8장 + `punch-cut` · `compositions/s10.html`

결과: 프로젝트 `work/launch-30s/video/` (미리보기 `npx hyperframes preview`, 띄워 둔 서버 http://localhost:3077/#project/video)
lint: 0 errors · 0 warnings. check: `ok: true`, error 0 (아래 경고 참고).
프레임: `work/launch-30s/video-frames/` — `npx hyperframes snapshot --at`(브라우저 캡처)으로 프레임 시각 n/30 그대로 뽑음. 이전 8장면 프레임은 지우고 다시 뽑음.

## 공통

- 폰트: Pretendard 400 · 600 · 700, 로컬 `src/assets/fonts/Pretendard-*.otf` `@font-face` (design.md 3장 A · video.md 3장). 장면마다 `document.fonts.ready` + 부품 iframe 안 `fonts.ready` · 이미지 decode 뒤 timeline 등록
- src 불러오기: `src/parts` · `src/assets` · `src/screens`를 `video/assets/src/`에 바이트 그대로 (`diff -rq` 같음, `_check/` · `.DS_Store`만 뺌). 부품은 iframe 원본 HTML, 상태는 `?state=`로만, `video-scale` × 2.8 (video.md 5장), logo는 `logo-hero` × 6 (video.md 5장)
- 줄바꿈 `word-break: keep-all` · 정렬 (video.md 3장)
- Easing `ease-out` · `ease-in` · `ease-inout` · `ease-linear` (motion.md 1장) 값 그대로 cubic-bezier
- Duration · hold 프레임 = motion.md 1장 · 4장 (30fps)
- 장면 경계: 2→3 `button-press` 뗌 끝 `transition` · 5→6 `shape-morph` (점 자리에서 `transition`) · 10 끝 · 나머지 `cut-in-motion` (motion.md 3장: `scene-out` 절반 = 장면 끝)

## 장면별

| # | 시간 (프레임) | 배경 · 글자 (video.md) | 움직임 · 카메라 (motion.md) | 불러온 src |
|---|---|---|---|---|
| 1 | 0.0–2.7 (0–81) | 그대로 — `video-bg-soft` (2장) · `video-display` · `video-text`, "실력" `video-text-accent` (3장) · 가운데 | 그대로 — `text-type` + `cam-in` 상태 `cam-follow` → `cam-pull` (3장 · 5장 · 1장) → `hold-m` → `scene-out` · `cut-in-motion` | `src/assets/fonts/Pretendard-Bold.otf` |
| 2 | 2.7–4.7 (81–141) | 그대로 — `video-bg-soft` · 폰 프레임 `phone-size` · `phone-screen` · `phone-bezel` · `phone-radius` · `phone-color` · `phone-screen-bg` (4장) · 덮개판 (4장 예외 줄) | 그대로 — `crane-angle` · `dist-l` (1장) → `cam-crane` (5장, `dur-2xl` · `ease-inout`, `cam-in`) → `hold-m` → `button-press` (`press-scale` · `dur-s` · `ease-in` / `dur-m` · `ease-out`) → `transition` | `src/screens/01-home.png` · `src/parts/button-submit.html?state=apply-case` |
| 3 | 4.7–7.7 (141–231) | 그대로 — `video-bg-soft` · `video-gap` (3장) | 그대로 — `cam-hold` · `skill-carousel` (3장: 거리 980 + 56, `dur-l` · `ease-inout`, 카드마다 `hold-m`) → `scene-out` · `cut-in-motion` | `src/parts/skill-card-1.html` · `skill-card-2.html` · `skill-card-3.html` |
| 4 (새) | 7.7–10.3 (231–309, 78f) | `video-bg-soft` (2장) · 윗줄 "일에 바로 적용하는 AI" `video-display` · `video-text` · 아랫줄 "리서치" → "콘텐츠" → "분석" → "업무 자동화" `video-display` · `video-text-accent` (3장) · 줄 사이 `video-gap-line` 0 (3장) · 두 줄 모두 가운데 (3장 `slot-roll` 예외) | `cam-hold` (5장) · `headline-in` (3장: 줄마다 `enter` = `dur-m` · `ease-out` · `mask-rise`, 줄 사이 `stagger` `dur-m`) 0–12f → `hold-m` 12–33f → `slot-roll` (3장, 2026-10-24 바뀐 정의: 나가는 단어와 다음 단어가 세로로 붙은 한 덩어리로 마스크 안에서 같이 위로 `mask-rise` · `dur-s` · `ease-out` — 나가는 단어 0 → −100%, 다음 단어 100% → 0; 바뀜 33 · 45 · 51f = 간격 `dur-l` 12f → `dur-m` 6f) → 54f 마지막 단어 → `hold-m` → `scene-out` 76.5f · `cut-in-motion` | 폰트만 `src/assets/fonts/Pretendard-Bold.otf` |
| 5 (바뀜) | 10.3–11.7 (309–351, 42f) | `video-bg-soft` · 부품 안 글자만 ("제출하기") · 화면 가운데 (3장) | `cam-hold` · `part-in` (3장: `enter` + 위 `dist-m` 24px · 투명도, `dur-m` · `ease-out`) 0–6f → `hold-m` 6–27f → `shape-morph` 앞부분 (3장): 글자 `exit` (`dur-s` · `ease-in` · 투명도 1 → 0) 27–30f → 가로 폭 350 → 44 (높이와 같음, 원) `dur-m` · `ease-in` 30–36f → 원 → `scale-from` 0 `dur-m` · `ease-in` 36–42f → 42f = 장면6 첫 프레임 `transition` (`scene-out` 없음) | `src/parts/button-submit.html?state=submit` |
| 6 (새) | 11.7–12.4 (351–372, 21f) | `video-bg-soft` · 부품 안 글자만 ("승인 완료") · 화면 가운데 = 장면5 점 자리 (960, 540) · badge-approved × 2.8 = 302.4×89.6 (5장) | `cam-hold` · `shape-morph` 뒷부분 = `badge-pulse`와 같은 움직임 (3장: `scale-from` 0 → 1 · `dur-m` · `ease-out`, 중심 배지 가운데) — `transition` (2장)대로 장면 첫 프레임에 이미 1f 들어간 상태 (진행 −1f–5f) → `hold-s` 5–18f → `scene-out` 19.5f · `cut-in-motion` | `src/parts/badge-approved.html` (상태 없음) |
| 7 | 12.4–14.6 (372–438) | 그대로 (옛 5장) — `video-bg-dark` → `video-bg-soft` · `video-display` · `video-text-on-dark` → `video-text` · 가운데 | 그대로 — `dark-cut` (3장: `transition` → 제목 `enter` → `hold-s` → 바탕 · 글자 색 `dur-xl` · `ease-linear`) → `hold-m` → `scene-out` · `cut-in-motion` | 폰트만 |
| 8 | 14.6–16.3 (438–489) | 그대로 (옛 6장) — `video-bg-soft` · 부품 안 글자만 | 그대로 — `cam-hold` · `part-in` → 바로 `count-up` (3장: 0 → `data-final` 29,700 · `dur-2xl` · `ease-out` · 정수) → `hold-s` → `scene-out` · `cut-in-motion` | `src/parts/stat-card.html` |
| 9 | 16.3–18.4 (489–552) | 그대로 (옛 7장) — `video-bg` (5장 asset-card 규칙) · `video-gap` | 그대로 — `cam-hold` · `asset-list` (= `skill-list`: 카드마다 `enter` + 위 `dist-m` · 투명도, `stagger` `dur-m`) → `hold-l` → `scene-out` · `cut-in-motion` | `src/parts/asset-card.html?state=private-image` · `review` · `selling` · `private-file` |
| 10 (바뀜) | 18.4–21.7 (552–651, 99f) | `video-bg-end` = `video-bg-dark` + `video-glow` + `video-grain` (2장) · `logo-hero` × 6 (5장) · 와이드: 슬로건 `video-title` · `video-text-on-dark` · 가운데 · `video-gap-end` (3장) · 클로즈: logo만 | `end-reveal` (3장: `logo-reveal` 엔드 카드 = logo 글자마다 `enter`, 글자 사이 `stagger` `dur-xs`, 7번째부터 같이 0–18f → `dur-l` 뒤 슬로건 투명도 0 → 1 · `dur-l` 30–42f) → `hold-s` 42–54f → `punch-cut` (3장: 54f `transition` 컷 → 같은 logo `cut-scale` × 1.7 (1장), logotype 안 심볼을 화면 가운데, 슬로건 빠짐, 컷 뒤 움직임 없음) → `hold-end` 54–99f → 마지막 hold 정지 (4장 예외) | `src/parts/logo.html?state=logotype-white` (와이드: 같은 iframe 13개 글자 칸 · 클로즈: 1개) |

## 프레임 (`work/launch-30s/video-frames/`, 루트 프레임 번호 · 30fps)

| 파일 | 프레임 | 무엇 |
|---|---|---|
| 01 | 72 | 1장 머묾 |
| 02a · 02b · 02c | 81 · 121 · 135 | 2장 cam-crane 시작 · cam-in hold-m · 누름 끝 |
| 03 · 03b · 03c | 153 · 186 · 219 | 3장 카드 1 · 2 · 3 hold-m |
| 04 | 251 | 4장 "리서치" hold-m (스냅 04) |
| 04-roll1 | 265 | slot-roll 첫 바뀜 1f 진행 (리서치 → 콘텐츠, 한 덩어리로 올라가는 중 · `ease-out`이라 거의 도착, 겹침 없음) |
| 04-roll2 | 277 | 둘째 바뀜 1f 진행 (콘텐츠 → 분석) |
| 04-roll3 | 283 | 셋째 바뀜 1f 진행 (분석 → 업무 자동화) |
| 04b | 296 | 4장 "업무 자동화" hold-m (스냅 04b) |
| 05 | 329 | 5장 button-submit hold-m (스냅 05) |
| 05-morph | 342 | 글자 exit 끝 · 폭이 줄어드는 중 (30f+3) |
| 05b | 345 | 원이 된 순간 (36f, 스냅 05b) |
| 05-dot | 350 | 장면5 마지막 프레임 = 점 (41f, scale ≈ 0.52) |
| 06-first | 351 | 장면6 첫 프레임 — 배지가 이미 `enter` 1f 진행 (scale ≈ 0.68, `ease-out` 1/6), 빈 바탕 없음 (critic 불합격 1회 뒤 고침) |
| 06-pop | 353 | 장면6 2f — enter 3f 진행 중 |
| 06 | 363 | 6장 hold-s (스냅 06) |
| 07 · 08 · 09 | 432 · 480 · 540 | 7 · 8 · 9장 머묾 |
| 10 | 602 | 10장 와이드 hold-s (스냅 10) |
| 10-cut-before | 605 | 컷 바로 앞 프레임 (와이드, 53f) |
| 10-cut-after | 606 | 컷 바로 뒤 프레임 (클로즈 cut-scale, 54f) |
| 10b | 642 | 클로즈 hold-end (스냅 10b) |
| 10-end | 650 | 영상 마지막 프레임 (정지) |

## 이름 없이 넣은 값 (숨기지 않음)

| 장면 | 값 | 왜 · 어디서 |
|---|---|---|
| 1 · 3 · 4 · 6–9 | `scene-out` 시작 = 장면 끝 − 1.5f → 마지막 hold가 docs 값보다 1.5f 김 | `cut-in-motion` 절반 컷으로 scenes.md 경계를 지키려고 (이전 회차와 같음) |
| 1 · 2 · 8 · 9 · 10 | 이전 회차 used-video.md "이름 없이 넣은 값" 그대로 (1장 cam-follow 초점 · 커서 안 깜빡임 · 2장 대상 점 · 겹침 자리 · 줌 보간 · 8장 천 단위 쉼표 · 9장 "위 dist-m" = y −24 → 0 · 10장 글자 칸 경계 13개 · 슬로건 투명도 `ease-out` · glow rgba 표기) | 내용 바뀌지 않음 |
| 4 | slot-roll 간격 2개 = `dur-l` 12f, `dur-m` 6f (바뀜 3번 → 간격 2개라 중간 단계 없음). "간격" = 바뀜 시작 ↔ 다음 바뀜 시작 | motion.md "dur-l로 시작해 한 번마다 짧아져 마지막 dur-m". 3번이면 시작 · 끝만 있음. scenes.md 2.6초와 프레임이 맞음 (12 + 21 + 12 + 6 + 3 + 21 + 3 = 78) |
| 4 | 아랫줄 마스크 = 폭 1920 · 높이 95 (`video-display` 행간), 단어마다 그 안에서 가운데 정렬 | 단어 폭이 다 달라 줄 상자를 화면 폭으로 두고 가운데 맞춤. 스냅 04 · 04b와 같은 자리 |
| 5 | 폭 줄어드는 동안 `border-radius` 8 → 22를 폭과 같은 진행값으로 일직선 | `shape-morph` 정의는 "원이 됨"까지만. 원 = 22 (높이 절반, 스냅 05b), 시작 = 부품 8. 사이 곡선은 docs에 없음 |
| 5 | 부품 상자 `translateX` = (350 − w) / 2 × 2.8 (폭과 같은 진행값) · 원 축소 중심 (960, 540) | 부품 안 버튼이 왼쪽에 붙어 있어 가운데 기준으로 줄이려고 (스냅 05b와 같은 계산). 정의에 줄어드는 기준점 없음 → 가운데로 읽음 |
| 5 | `#button-submit` 인라인 `height: 44px` · `width` · `border-radius` · `.label` `opacity` (iframe 안, 장면 스크립트) | 움직임 중간 상태. 부품 파일은 그대로. 스냅 05b와 같은 방식 (video.md 5장 "상태는 data-state로만"과 비교는 critic 판단 — 이전 회차에 적은 것과 같음) |
| 5 | 마지막 프레임 41f는 점 scale ≈ 0.52 (`ease-in` 5/6), scale 0은 42f = 장면6 첫 프레임 시각 | "점 자리에서 transition" 해석 |
| 6 | 배지 `scale-from` 진행을 1f 앞당김 (장면 시간 t + 1f) → 장면 첫 프레임 = 1f 들어간 상태, enter는 5f에 끝나 `hold-s`가 12f → 13f (+ 공통 1.5f) | critic 불합격 1회 (351f 빈 바탕). `transition` "다음 장면 첫 프레임에 이미 enter 중" · `shape-morph` "빈 바탕 프레임 없음"을 지키고 장면 길이 0.7초를 유지하려고. 1f는 docs에 이름 없는 값 |
| 10 | 클로즈 logo 자리 left 916.5386 · top 483.0564 · `transform-origin` 43.4614 56.9436 · scale 1.7 (심볼 상자 svg 앞 5개 path, 가운데 (7.2436, 9.4906) × 6) | 스냅 10b와 같은 잰 값 · 계산 |
| 10 | 클로즈 logo는 와이드의 글자 칸 13개가 아닌 logo.html iframe 하나 (같은 부품 · 같은 상태) | 컷 뒤 움직임이 없어 글자 나누기가 필요 없음. 그림은 같은 logo |
| 10 | 컷 = 54f에 와이드 묶음 투명도 1 → 0, 클로즈 묶음 0 → 1 (`tl.set`, 0ms). glow · grain은 그대로 둠 | `transition` 0ms 컷을 두 겹 교체로. 바탕은 스냅 10b대로 그대로 |

## 구현 메모 (그림 · 시간은 바뀌지 않음)

- 부품 iframe을 담은 상자를 GSAP `x` · `y` · `scale` · `yPercent`로 트윈하면, GSAP가 숨은 장면에서 transform을 읽으려고 상자를 잠깐 옮겨 iframe이 다시 로드됨 → check `request_failed`(ERR_ABORTED) 22건의 원인이었음 (이전 회차 check 메모의 22건). 그래서
  - 3 · 8 · 9 · 10장: 같은 이동을 CSS 변수(`--tx` · `--ty`)를 GSAP로 트윈하고 `transform: translate(var(--…))`로 걸게 바꿈 (값 · 이징 · 시간 그대로)
  - 5 · 6장: 상태 전부를 장면 시간 t 하나로 계산해 직접 씀 (8장 count-up과 같은 방식), iframe이 다시 로드되면 다시 그림
- 결과: check error 0, `ok: true`.

## check 경고 (그대로 둠)

- `line_unread` 3건: 1장 훅 (이전과 같음) · 4장 "분석" 0.26초 (`slot-roll` 간격 `dur-l` · `dur-m`이 docs 값) · 10장 슬로건 0.73초 (`punch-cut` 정의상 클로즈에서 슬로건이 빠짐). 모두 motion.md 값이라 바꾸지 않음
- `film_silent`: 장면표에 소리 없음
- info `container_overflow` (4장): 마스크 밖으로 밀려난 단어 (의도, 마스크가 가림). `content_overlap`은 slot-roll 정의 변경 뒤 없어짐. info (1장): 카메라 확대로 화면 밖 (의도)

## 확인 필요 (사람 · critic)

- 없음. 4장 slot-roll 겹침은 사람이 motion.md 정의를 바꿔 해결 (2026-10-24), 6장 첫 프레임 빈 바탕은 critic 불합격 1회 뒤 고침.
