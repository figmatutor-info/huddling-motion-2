# used — snapboard · launch-30s (새 판 · 10장면 · 21.7초)

결과: `work/launch-30s/snapboard.html` (컷 1920×1080 · 장면 순서대로) · `work/launch-30s/snap/` 17장:
`01` · `02a` · `02b` · `02c` · `03` · `03b` · `03c` (장면1–3, 손대지 않음) · `04` · `04b` · `05` · `05b` · `06` · `07` · `08` · `09` · `10` · `10b` (이번 회차 새로 캡처).
캡처: playwright-core + Chromium 1248 (headless), `--allow-file-access-from-files`, `document.fonts.ready` (본문 + iframe 전부) 뒤 장면별 요소 캡처.

## 이번 회차 (2026-10-24, scenes.md 10장면 승인본 반영)

### 파일 정리 (지운 것 — 지우기 전에 확인)

옛 번호 PNG 5개를 지우고 새 번호로 다시 캡처했다. 지운 파일 (md5 · 그때 담긴 장면):

| 지운 파일 | md5 | 옛 내용 | 새 자리 |
|---|---|---|---|
| `snap/04.png` | 230f9d4f8cb0c877de67730b482a7302 | 옛 장면4 button-submit submit `part-in` → `hold-m` | 새 `05.png` (같은 그림, 다시 캡처) |
| `snap/05.png` | 1e6b04155e4216b2e58736f921f4a8e8 | 옛 장면5 `dark-cut` 끝 | 새 `07.png` |
| `snap/06.png` | b295886823b7c50cb8b55261cd935148 | 옛 장면6 stat-card `count-up` 끝 | 새 `08.png` |
| `snap/07.png` | d7bcea8e3bd30f5c4b45f00e66a8d640 | 옛 장면7 `asset-list` | 새 `09.png` |
| `snap/08.png` | 76ccd3ca7a89011bcbaf67d955a2299b | 옛 장면8 `end-reveal` 끝 | 새 `10.png` (와이드) |

- 지우기 전 사본 (PNG 12장 + 옛 snapboard.html · used-snapboard.md): `/private/tmp/claude-501/-Users-bibi-huddling-motion-2/4a91afb7-f4f3-48f8-9dd7-2dab84bad245/scratchpad/prev/`
- 번호만 바뀐 4장(새 07 · 08 · 09 · 10)을 옛 파일과 픽셀 비교: 07 · 08은 글자 안티앨리어스 ±2만 다름, 09는 부품 가장자리 ±21 (2만여 px, 카드 안 글자 · 아이콘 렌더 차), 10은 logo 가장자리 2601px만 >15 (나머지 glow ±1). 그림 차이 없음 — 렌더 잡음.
- 장면1–3 PNG(01 · 02a · 02b · 02c · 03 · 03b · 03c)는 파일 그대로 둠 (md5 같음). HTML 해당 부분도 그대로. 다시 캡처해 보니 02a · 02b · 02c는 픽셀 같고, 01 · 03은 글자 안티앨리어스 ±2 · ±11 차뿐이라 바꾸지 않음.
- snapboard.html 안 id도 새 번호로: 옛 `#s04`–`#s08` → `#s05` · `#s07` · `#s08` · `#s09` · `#s10`. 새 `#s04` · `#s04b` · `#s05b` · `#s06` · `#s10b`.

### 장면별 (새 · 바뀐 · 번호 바뀐 것)

| # | 배경 (video.md 2장) | 글자 스타일 · 색 (video.md 3장) | 간격 · 배치 (video.md 3 · 5장) | 머묾 상태 · 움직임 (motion.md) | 불러온 src |
|---|---|---|---|---|---|
| 4 · 04 | `video-bg-soft` | 윗줄 "일에 바로 적용하는 AI" `video-display` · `video-text` / 아랫줄 "리서치" `video-display` · `video-text-accent` · 두 줄 모두 가운데 (3장 정렬 줄 `slot-roll` 예외) | 줄 사이 `video-gap-line` (0, 행간만) · 묶음 화면 가운데 → 윗줄 y 445–540 (글자 x 625–1295) · 아랫줄 y 540–635 (x 859–1061) | `slot-roll` 첫 단어 상태 = `headline-in`(줄마다 `enter`, 사이 `stagger`) 끝 → `hold-m` · `cam-hold` (3 · 4 · 5장) | 폰트만 `src/assets/fonts/Pretendard-Bold.otf` |
| 4 · 04b | 같음 | 아랫줄 "업무 자동화" (같은 스타일 · 색 · 가운데) | 윗줄 그대로 · 아랫줄 x 782–1138 · y 540–635 | `slot-roll` 마지막 단어 뒤 `hold-m` (장면4 머묾) | 같음 |
| 5 · 05 | `video-bg-soft` | 부품 안 글자만 ("제출하기") | 화면 가운데 · × 2.8 = 980×123.2 (x 470–1450 · y 478.4–601.6) | `part-in` → `hold-m` · `cam-hold` | `src/parts/button-submit.html?state=submit` |
| 5 · 05b | 같음 | 없음 (글자 `exit` 끝) | 원 지름 44 × 2.8 = 123.2 · 원 x 898.4–1021.6 · y 478.4–601.6 (가운데 960 · 540) | `shape-morph` 중간 = 글자 `exit`(`dur-s` · `ease-in`) 끝 → 가로 폭이 높이와 같아져 원이 된 순간 (`dur-m` · `ease-in` 끝). 다음: 원 → `scale-from`(0) 점 → `transition` | 같음 (같은 부품, 움직임 상태만 장면 스크립트로) |
| 6 · 06 | `video-bg-soft` | 부품 안 글자만 ("승인 완료") | 화면 가운데 (장면5 점 자리) · × 2.8 = 302.4×89.6 (x 808.8–1111.2 · y 495.2–584.8) | `shape-morph` 뒷부분 `scale-from` → 1 (`dur-m` · `ease-out`, `badge-pulse`와 같은 움직임) 끝 → `hold-s` · `cam-hold` | `src/parts/badge-approved.html` (상태 없음) |
| 7 · 07 (옛 05) | `video-bg-soft` (`dark-cut` 바탕 바뀐 뒤; 시작 `video-bg-dark` · `video-text-on-dark`) | `video-display` · `video-text` · 가운데 | 화면 가운데 (y 492.5–587.5) | `dark-cut` 끝 → `hold-m` | 폰트만 |
| 8 · 08 (옛 06) | `video-bg-soft` | 부품 안 글자만 | 화면 가운데 (x 470–1450 · y 426.6–653.4) | `part-in` → `count-up` 끝 (`data-final` "29,700" = 원본 글자) → `hold-s` · 상태 없음 · counts 줄 보임 | `src/parts/stat-card.html` |
| 9 · 09 (옛 07) | `video-bg` (asset-card 규칙, 5장) | 부품 안 글자만 | 세로 한 줄 · 카드 사이 `video-gap` · 묶음 가운데 (y 41.6–1038.4) | `asset-list` → `hold-l` | `src/parts/asset-card.html?state=private-image` · `review` · `selling` · `private-file` |
| 10 · 10 (옛 08) | `video-bg-end` = `video-bg-dark` + `video-glow` + `video-grain` (2장) | 슬로건 `video-title` · `video-text-on-dark` · 가운데 | `logo-hero` × 6 = 894×114 (5장) · logo ↔ 슬로건 `video-gap-end` · 묶음 가운데 (logo x 513–1407 · y 414–528 · 슬로건 y 576–666) | 와이드 = `end-reveal`(`logo-reveal` → `dur-l` 뒤 슬로건) 끝 → `hold-s` (`punch-cut` 컷 직전) | `src/parts/logo.html?state=logotype-white` |
| 10 · 10b | 같음 (`video-bg-end` 그대로, grain은 같은 seed 1 한 장) | 없음 — 클로즈에는 logo만 (`punch-cut` 정의) | 같은 `logo-hero`에 `cut-scale` × 1.7 (1장) → 1519.8×193.8 · 프레이밍 = logotype 안 심볼을 화면 가운데 (심볼 가운데 960 · 540) → logo 상자 x 886.1–2405.9 · y 443.2–637.0 (오른쪽 글자는 컷 밖) | `punch-cut`: `transition` 컷 → 클로즈, 컷 뒤 움직임 없음 → `hold-end` 마지막 정지 (4장 예외) | 같음 |

### 이번 회차 이름 없이 넣은 값 (숨기지 않음)

| 장면 | 값 | 왜 |
|---|---|---|
| 5 · 05b | `#button-submit` 인라인 `width: 44px` · `height: 44px` · `border-radius: 22px` · `.label` `opacity: 0` (iframe 안, 장면 스크립트) | `shape-morph` 정의 "가로 폭이 높이와 같아질 때까지 줄어 원" · 글자 `exit` 끝을 옮긴 값. 44 = 부품 높이(padding 12 × 2 + `Text/label` 행간 20), 22 = 그 절반(원). 높이 44 고정은 좁은 폭에서 글자가 줄바꿈돼 버튼이 104px로 늘어나는 것을 막으려고 — 원래 높이를 지키는 것. 부품 파일은 그대로, 상태 바꿈이 `data-state` · CSS 변수가 아닌 인라인 스타일이라는 점은 적어 둠 (video.md 5장 "상태는 data-state · CSS 변수로만"과 비교해 critic 판단 필요 — 움직임 중간 상태로 봄. 영상 `count-up`도 iframe 안 글자를 스크립트로 바꿈) |
| 5 · 05b | 부품 상자 `translateX(428.4px)` = (350 − 44) / 2 × 2.8 | 부품 안 버튼이 왼쪽에 붙어 있어 폭이 줄면 왼쪽으로 몰림. 장면표 "점 자리 = 화면 가운데"를 지키려고 가운데로 옮긴 계산 값. 정의에 "줄어드는 기준점"은 없음 → 가운데 기준으로 읽음 |
| 10 · 10b | logotype 안 심볼 상자 = svg 앞 5개 path, x 0–14.4871 · y 2.0016–16.9796 (149×19 좌표, `getBBox` 잰 값) → 심볼 가운데 (7.2436, 9.4906) | `punch-cut` "심볼을 화면 가운데"의 기준점. 이미지에서 잰 값 (docs 이름 아님). "심볼 = 6번째 path(x 20.7부터 글자 H) 앞의 꽃 모양 5개"로 나눔 |
| 10 · 10b | `transform-origin: 43.4614px 56.9436px` · left 916.5386 · top 483.0564 | 위 잰 점 × 6 (`logo-hero`)을 화면 가운데에 놓는 계산. 새 값 아님 |
| 10 · 10 · 10b | `video-glow` 색 표기 `rgba(55, 89, 222, 0.45 → 0)` | `#3759de`에 docs 불투명도를 거는 표기 (이전과 같음) |

### 판단해 둔 것

- 장면4 · 5 · 10은 요청대로 두 컷씩: 04(첫 단어) · 04b(마지막 단어 = 장면 머묾), 05(`hold-m`) · 05b(원), 10(와이드) · 10b(클로즈 = 마지막 머묾). 05는 요청 "button-submit submit + 원이 된 순간"을 두 컷으로 읽음 — 한 컷만이면 05b만 남기면 됨.
- 모든 컷 원래 크기 (보드에서 작게 둔 것은 이전처럼 03b · 03c만).
- `video-glow` · `video-grain`은 10b에도 그대로 (장면10 배경이 `video-bg-end`, 컷에서 빠지는 것은 슬로건뿐 — `punch-cut` 정의).
- 05b의 원은 버튼 채움 `color-primary` 그대로 (부품 CSS).

## 이전 회차 기록 (8장면 판, 장면 번호는 옛 번호)


결과: `work/launch-30s/snapboard.html` (컷 1920×1080 · 장면 순서대로, 2장은 02a · 02b · 02c 세 컷 원래 크기, 3장만 2 · 3장째 컷을 반 크기로 한 줄 더) · `work/launch-30s/snap/01.png` · `02a.png` · `02b.png` · `02c.png` · `03.png` … `08.png` + `03b.png` · `03c.png` (`02.png` 없음)
장면2 갱신 2 (2026-10-24, docs 바뀜: video.md 4장 마지막 예외 줄 덮개판 · motion.md 3장 `button-press` 누름 중심 버튼 가운데): 02a · 02b · 02c 모두 버튼 자리에 `phone-screen-bg` 덮개판 + `button-submit[apply-case]` 겹침 (덮개판 고정, 부품만 누름). 02a는 장면표 "첫 프레임부터 놓여 있음"이라 같은 겹침을 넣음. 세 컷 다시 캡처.

장면2 갱신 3 (2026-10-24, docs 바뀜: video.md 4장 덮개판 줄 "사방 1px 크게 (화면 이미지 @1x 기준)"): `.overlay-cover`만 사방 1px@1x = 1 × 1.066667 (`phone-screen` 배율, video.md 4장) = 1.0667px 키움 → 폰 안 left 52.4 · top 531.1797 · 341.3333×49.0667, 모서리는 같은 8.5333px. 부품 · 위치 그대로. 02a · 02b · 02c 다시 캡처.
장면2 갱신 (2026-10-24, 장면표 "button-press" 반영): 02b에 `src/parts/button-submit.html?state=apply-case`를 01-home 화면 이미지 속 버튼 자리에 겹쳐 다시 캡처. 새 컷 `#s02c` · `snap/02c.png` = `button-press` 누름 끝(`press-scale` 0.96). (그때 02a는 손대지 않음 — 갱신 2에서 해결)
장면2 이전 갱신 (2026-10-24, 장면표 "crane만 · cam-pull 생략" 반영): 머묾 컷 `#s02` · `snap/02.png` 지움. 숨겨 두었던 옆 묶음(부제 · mission-card iframe) 아예 뺌 → 폰이 화면 가운데로 옮겨져 `02a` · `02b` 다시 캡처. 장면2 머묾 컷 = `02b`.
이전 판 PNG(01–11)는 모두 지우고 새로 캡처함 (09 · 10 · 11 없음).
캡처: playwright-core + Chromium (headless), `--allow-file-access-from-files`, `document.fonts.ready` (본문 + iframe 전부) 뒤 장면별 요소 캡처.
각 컷 = 장면표의 "머묾"(마지막 hold) 상태. 3장은 skill-carousel 카드 1 · 2 · 3 각 `hold-m` 상태.

## 공통 (모든 회차)

- 폰트: Pretendard 400 · 600 · 700, `src/assets/fonts/Pretendard-*.otf` 로컬 로드 (design.md 3장 A · video.md 3장)
- 줄바꿈 `word-break: keep-all` (video.md 3장)
- 부품 배율 `video-scale` × 2.8, iframe 전체에 한 번 (video.md 5장). 부품 원본 그대로, 상태는 `?state=`로만
- 정렬 (video.md 3장 정렬 줄): 화면 가운데 한 줄 장면(1 훅 · 7 dark-cut · 10 엔드)과 4 `slot-roll` 두 줄은 가운데, 나머지 덩어리 안 글자는 부품뿐 (새 번호)
- 묶음 전체 화면 가운데 (가로 · 세로) (video.md 3장)
- 카메라: 2장 빼고 모든 머묾 컷 × 1 (`cam-hold`, 1장은 `cam-pull` 끝난 상태) (motion.md 5장). 2장 02a는 `cam-crane` 시작 컷, 02b는 `cam-crane` 끝 = `cam-in` × 2.4 상태 머묾 (`cam-pull` 생략)

## 장면별 — 장면1–3 (옛 표, 장면4 이후 줄은 옛 번호)

| # | 배경 (video.md 2장) | 글자 스타일 · 색 (video.md 3장) | 간격 · 배치 (video.md 3 · 4 · 5장) | 머묾 상태 (motion.md) | 불러온 src |
|---|---|---|---|---|---|
| 1 | `video-bg-soft` | `video-display` · `video-text`, "실력" `video-text-accent` · 가운데 | 화면 가운데 (x 546–1374 · y 492.5–587.5) | `text-type` 끝 + 커서 (폭 6 · 띄움 6 · 높이 = `video-display` 행간 95, 3장) · `cam-follow` → `cam-pull` 끝 · `hold-m` (3 · 4 · 5장) | `src/assets/fonts/Pretendard-Bold.otf` (폰트만) |
| 2 · 02a | `video-bg-soft` | 없음 (화면 이미지 속 글자만) | 폰 `phone-size` 444×928 · `phone-screen` 416×900 · `phone-bezel` · `phone-radius` · `phone-color` · `phone-screen-bg` (video.md 4장) · 폰 하나 화면 가운데 (video.md 3장 · 장면표) → 각도 0 · 위치 0이면 폰 x 738–1182 · y 76–1004. `cam-crane` 시작 = 폰이 그 자리보다 아래 `dist-l` 70px (motion.md 5장 · 1장) · × 1 · `crane-angle` rotateX 12° · rotateY -18° · perspective 2400px · 회전 중심 폰 가운데 (motion.md 1장) → CSS `transform-origin: 50% 50%; transform: translateY(70px) perspective(2400px) rotateX(12deg) rotateY(-18deg)` · 결과 폰 테두리 상자 x 746–1187 · y 148–1084 (아래 약 4px은 컷 밖으로 잘림) | `cam-crane` 시작 상태 (motion.md 5장). 버튼 겹침은 02b와 같은 폰 안 위치 · 덮개판 + 부품 (video.md 4장 예외 줄) · 폰과 같이 기울어짐 → 컷 상자 부품 x 801.49–1127.56 · y 667.35–732.10 · 덮개판 x 800.49–1128.66 · y 666.21–733.20 · 파랑 실측 x 802–1125 · y 662–730 | `src/screens/01-home.png` · `src/parts/button-submit.html?state=apply-case` |
| 2 · 02b | `video-bg-soft` | 없음 (화면 이미지 · 부품 안 글자만 · 미션 카드는 화면 이미지 속 카드) | 각도 0 · 위치 0 · `cam-in` × 2.4 (motion.md 1장) · 대상 = 01-home 미션 카드 영역 가운데 → 카메라 층 `translate(-1344px, -752.16px) scale(2.4)` (원점 0 0; 960 − 960 × 2.4 · 540 − 538.40 × 2.4, 대상 점 컷 좌표 = 화면 x 752 + 416 × 390/780 = 960 · y 90 + 900 × 841/1688 = 538.40) | `cam-crane` 끝 → `cam-pull` 생략 → `cam-in` 상태로 `button-press` 앞 `hold-m` (motion.md 5장 · 3장 `button-press` · 4장). 버튼 겹침 (video.md 4장 예외 줄): 부품 배율 = `phone-screen` 배율 1.066 (= 416/390, 계산에는 1.066667) · 부품 폰 안 위치 left 53.4667 · top 532.2464 (아래 잰 값) → 컷 좌표 x 555.49–1369.54 · y 707.60–820.22 (814.05×112.64). 바로 아래 덮개판 = 사방 1px@1x 크게 (video.md 4장) = 1 × 1.066667 = 1.0667px → 341.3333×49.0667 · 폰 안 left 52.4 · top 531.1797 · 같은 모서리 (부품 `border-radius` 8px × 1.066667 = 8.5333px) · 색 `phone-screen-bg` (= design.md `color-bg` #ffffff) → 컷 좌표 x 552.94–1372.13 · y 705.05–822.80 | `src/screens/01-home.png` · `src/parts/button-submit.html?state=apply-case` |
| 2 · 02c | 같음 | 같음 | 02b와 같음 + 부품만 `transform: scale(0.96)` · 중심 버튼 가운데 (motion.md 3장 `button-press`) → 컷 좌표 x 571.77–1353.26 · y 709.86–817.96. 덮개판은 고정 (x 552.94–1372.13 · y 705.05–822.80) | `button-press` 누름 끝 = 1 → `press-scale` 0.96 (`dur-s` · `ease-in` 끝, motion.md 1장 · 3장). 다음: 뗌 0.96 → 1 `dur-m` · `ease-out` → 떼는 끝 프레임에 `transition` (컷) | 같음 |
| 3 · 03 | `video-bg-soft` | 부품 안 글자만 | 카드 가로 한 줄 · 카드 사이 `video-gap` · 보이는 카드 가운데 (x 470–1450 · y 472.8–607.2) | `skill-carousel` 카드 1 `hold-m` · `cam-hold` (3 · 4 · 5장) | `src/parts/skill-card-1.html` · `skill-card-2.html` · `skill-card-3.html` |
| 3 · 03b | 같음 | 같음 | 줄 왼쪽으로 한 장 = 카드 폭 980 + `video-gap` 56 = 1036 (motion.md 3장 `skill-carousel`) → 카드 2 가운데 | 카드 2 `hold-m` | 같음 |
| 3 · 03c | 같음 | 같음 | 왼쪽으로 두 장 (2072) → 카드 3 가운데 | 카드 3 `hold-m` | 같음 |
| 4 | `video-bg-soft` | 부품 안 글자만 ("제출하기") | 화면 가운데 (x 470–1450 · y 478.4–601.6) | `part-in` → `hold-m` | `src/parts/button-submit.html?state=submit` |
| 5 | `video-bg-soft` (`dark-cut` 바탕 바뀐 뒤; 시작은 `video-bg-dark` · `video-text-on-dark`) | `video-display` · `video-text` · 가운데 | 화면 가운데 | `dark-cut` 끝 → `hold-m` (3 · 4장) | 폰트만 |
| 6 | `video-bg-soft` | 부품 안 글자만 | 화면 가운데 (x 470–1450 · y 426.6–653.4) | `part-in` → `count-up` 끝 (최종값 `data-final` "29,700") → `hold-s` (3 · 4장). 상태 없음 · counts 줄 보임 (피그마 그대로) | `src/parts/stat-card.html` (원본 그대로, 금액 = 원본 textContent = data-final) |
| 7 | `video-bg` (asset-card 규칙, video.md 5장) | 부품 안 글자만 | 세로 한 줄 · 카드 사이 `video-gap` · 묶음 가운데 (y 41.6–1038.4) | `asset-list` → `hold-l` | `src/parts/asset-card.html?state=private-image` · `review` · `selling` · `private-file` |
| 8 | `video-bg-end` = `video-bg-dark` + `video-glow` (1200 · 0.45 → 0 일직선 · 블러 160) + `video-grain` (1px · 알파 0–255 · seed 1 · mulberry32 · 불투명도 0.06 · 고정) (2장) | `video-title` · `video-text-on-dark` · 가운데 | `logo-hero` × 6 = 894×114 (5장) · logo ↔ 슬로건 `video-gap-end` · 묶음 가운데 (logo y 414–528 · 슬로건 y 576–666) | `end-reveal` 끝 → `hold-end` 정지 (3 · 4장) | `src/parts/logo.html?state=logotype-white` |

## 이름 없이 넣은 값 (숨기지 않음)

| 장면 | 값 | 왜 |
|---|---|---|
| 2 · 02a · 02b · 02c | 화면 이미지 속 버튼 자리 = 01-home 이미지(780×1688) 안 x 74–709 · y 972–1059 (636×88, 가장자리 안티앨리어스 없음 · 부품 318×44 @2x와 맞음) | 이미지 픽셀에서 잰 값 (#3759de 픽셀 범위). docs 이름 아님 |
| 2 · 02a · 02b · 02c | 부품 위치 폰 안 left 14 + 74 × 416/780 = 53.4667px · top 14 + 972 × 900/1688 = 532.2464px · 부품 영역 339.2×46.9333 | 위 잰 값을 `phone-bezel` · `phone-screen`(video.md 4장)으로 옮긴 계산. 가로 · 세로 배율이 416/780 = 0.53333 · 900/1688 = 0.53318로 조금 달라 위치는 축마다 따로, 크기는 가로 배율 하나(× 416/390)로 씀 (세로 차 0.01px 미만). 덮개판은 이 상자에서 사방 1.0667px(= 1px@1x × 416/390, video.md 4장) 키운 것 — 키우는 양은 이제 docs 값, 기준 상자만 잰 값 |
| 2 · 02a · 02b · 02c | 덮개판 모서리 8.5333px (= 부품 8px × 1.066667) | docs는 "같은 모서리"까지. 숫자는 부품 CSS와 배율에서 계산 (새 값 아님) |
| 8 | `video-glow` 색을 `rgba(55, 89, 222, 0.45 → 0)`로 표기 | `#3759de`(`color-primary`)에 docs 불투명도를 거는 표기일 뿐, 새 색 아님 |
| 2 · 02b | `cam-in` 대상 점 = 01-home 이미지(780×1688) 안 390 · 841 (미션 카드 x 40–740 · y 588–1094의 가운데) | 이미지에서 잰 값. docs 이름 아님 (장면표 "01-home 미션 카드 영역"을 좌표로 옮긴 것, `video/compositions/s2.html`과 같은 이미지 안 점. 폰이 화면 가운데로 옮겨져 컷 좌표 · translate 값은 바뀜 — 영상 s2.html은 이번 snapboard 단계에서 손대지 않음) |
| 보드 | 3장 2 · 3장째 컷을 × 0.5 (960×540)로 두 장 나란히 · 컷 사이 간격 · 라벨 없음 | 보드 틀(영상 아님) 배치. 요청 "2 · 3장째 컷도 작게"의 "작게" 배율은 docs에 없어 정함. PNG `03b` · `03c`는 원래 크기 1920×1080 |

02a 재작업 (2026-10-24, 이전 회차 기록 — 그때는 숨긴 옆 묶음 때문에 폰 x 220–664, 사람 결정으로 motion.md 1장 `crane-angle` perspective · 회전 중심, 1장 `dist-l`, 5장 `cam-crane` 시작 위치 추가): 원근 · 회전 중심 · 시작 위치는 이제 docs 이름으로 씀. 02b · 02는 바뀌지 않음 (다시 캡처해 픽셀 같음 확인, 파일 그대로). 이번 회차(crane만)에서 02는 지우고 02a · 02b는 폰 가운데 배치로 다시 캡처.

이전 판에서 이름 없던 커서 폭 · 띄움 · 묶음 안 정렬(지금은 2장 옆 묶음이 없어 쓰는 곳 없음) · grain 생성기는 이제 docs 값 (motion.md 3장 `text-type` · video.md 3장 정렬 줄 · video.md 2장 `video-grain`)으로 씀.

(정리) `cam-crane` 사이 경로는 이제 motion.md 5장 "각도 · 위치 · 줌이 같은 시간에 같은 곡선으로" — 이름 없는 값 표에서 뺌.

## 덮개판 결과 (갱신 3 — 사방 1px@1x)

- 02c 덮개판 둘레 줄 (x 600–1319, 720px): y 707 이전 720px 모두 rgb(252,252,254) → 지금 비흰색 0 · y 819 이전 rgb(223,228,250) 720px → 0 · y 820 이전 rgb(196,206,245) 720px → 0 · y 705–708 · 818–822 모두 rgb(255,255,255).
- 둘레 영역 x 540–1385 · y 695–835 에서 부품 상자(+1px) 밖 비흰색 픽셀: 0. 파랑기(b−r ≥ 4) 픽셀 이전 1734 → 지금 76, 남은 76은 모두 x 570 · y 725–800 = 부품 자신의 왼쪽 가장자리 안티앨리어스 (부품 숨긴 덮개판만 캡처는 둘레 파랑기 0, 이전 1658).
- 02a · 02b: 바뀐 픽셀은 버튼 상자 가장자리뿐 (02a x 801–1127 · y 667–732, 02b x 555–1369 · y 707–820). 부품이 위에 있어 보이는 차이 없음.
- 이전 컷 · 덮개판만 캡처: `/private/tmp/claude-501/-Users-bibi-huddling-motion-2/260e1c43-ba8e-4368-9be0-034787a28d70/scratchpad/prev-cover2/`

## 덮개판 결과 (이전 회차 — 같은 크기, #3759de ±6 픽셀 범위, 버튼 줄 y 690–900만)

- 02b: x 555–1367 · y 708–818 = 813×111
- 02c: x 571–1351 · y 710–816 = 781×107 → 02b 대비 가로 0.961 · 세로 0.964 (계산 상자 781.49×108.11 = 0.96). 파란 범위가 실제로 줄었음. (이전 회차 02c: 813×112, 줄지 않았음)
- 부품을 숨기고 덮개판만 캡처: 버튼 줄에 #3759de 픽셀 0 → 이미지 속 버튼 채움은 다 가려짐.
- **남은 자국**: 덮개판 가장자리에 화면 이미지 버튼의 안티앨리어스 테두리가 1–2px 연하게 남음. 아래 가장자리 y 819 rgb(223,228,250) · y 820 rgb(196,206,245) 가로 약 790px, 위 y 707 rgb(252,252,254), 좌우 · 모서리 몇 px. 02c에서 줄어든 버튼 둘레에 원래 버튼 모양 연한 선으로 보임 (02b · 02a는 부품이 덮어 안 보임). 원인: 덮개판은 이미지 버튼 픽셀 범위(이미지 y 972–1059, 끝 1060 배타)와 정확히 같은 크기인데, 화면 이미지 확대(× 2.4 카메라) 보간이 가장자리 밖으로 약 반 픽셀 번짐. docs는 "같은 크기"라 덮개판을 키우지 않았음 → 키울지(얼마나)는 docs 결정 필요.

## 겹침 결과 (이전 회차, 02b · 02c, 화면 이미지만 캡처한 것과 픽셀 비교)

- 테두리 · 위치: 부품 파랑 x 555–1368 · y 707–819, 이미지 버튼 x 556–1368 · y 708–819 → 1px 안 (가장자리 서브픽셀 안티앨리어스 차). 모서리 시작점 같음 (위 줄 첫 파랑 x 571 둘 다).
- 색: 채움 둘 다 rgb(55, 89, 222) = `#3759de`. 차이 없음.
- 글자: 문구 같음 ("적용 사례 정리하기 →"), 글자 묶음 폭 같음(±1px) · 위치 왼쪽 약 2px · 위 1px 어긋남. **굵기가 다르게 보임** — 부품 글자 잉크량이 이미지보다 약 22% 많음 (컷에서 3550 vs 2912, 원본 @2x끼리 2212 vs 1778 · +24%). 부품(Pretendard SemiBold 600, 브라우저 렌더)이 화면 이미지 속 글자보다 굵고 선명함. 02b 확대 시 보이는 차이.
- 02c: 부품만 0.96으로 줄면 아래 화면 이미지 속 버튼(같은 색 · 원래 크기)이 그대로 보여, **버튼 테두리는 줄지 않고 글자만 줄어 보임** (02c 캡처 파랑 범위 x 556–1368 · y 708–819 = 02b와 같음). 화면 이미지는 고치지 않음(video.md 4장) · docs에 가리는 방법 없음 → 그대로 둠.

## 남은 것

- (해결) 02a에도 덮개판 + 부품 겹침 넣고 다시 캡처.
- (해결, 갱신 3) 덮개판 가장자리 1–2px 연한 파랑 자국 — docs "사방 1px@1x 크게"로 덮개판 키워 사라짐 (위 "덮개판 결과 (갱신 3)").
- 부품 글자가 이미지 속 글자보다 굵어 보이는 차 (이전 회차 기록) 그대로.
- 영상 `video/compositions/s2.html`은 이번 snapboard 단계에서 손대지 않음.

## 열기 주의

`snapboard.html`은 저장소 루트를 로컬 서버로 열거나 Chrome `--allow-file-access-from-files`로 연다. 이번 판은 05b(`shape-morph` 원)만 iframe 안을 스크립트로 바꾸므로, 플래그 없이 file://로 열면 05b가 원이 아닌 "제출하기" 버튼으로 보인다 (다른 컷은 같은 그림).
