합침: 비트1+2 · 비트4+5 · 비트10+11 (24초 × 비율이 1.5초 미만인 비트 2 · 4 · 10. 1+2는 이어짐이라 1과, 4+5는 같은 흐름도라 5와, 10+11은 결과 이야기라 11과. 구도 · 카메라는 1+2 → 비트2 · 4+5 → 비트5 (비트4 카메라 이동 포함) · 10+11 → 비트11, 전환은 마지막 비트의 전환)
한 줄 요약: 안 a — BRIEF 순서대로 "스킬에서 승인까지". 흩어진 부품이 사라지고 brand-icon이 돌아 로고 글자가 되고, 화면 제목 3개 컷 뒤 폰 5대 흐름도를 훑다 기운 평면으로 눕히고, 02-skills 폰이 `phone-rise-tilt`로 올라와 03-mission으로 바뀐 뒤, 제출 버튼을 누르고, 어두운 한 줄 "미션을 완성했어요!"를 지나 카드 줄이 mission-card(승인 배지) → stat-card(숫자 올라감)로 튕기고, 판매 중인 asset-card가 크게 내려앉은 뒤 엔드.
비트 구성: `10비트 · 전체>컷>가까이>컷>전체(폰 줄)>plane-tilt>멀리(평면)>컷>전체(폰)>컷>전체>컷>가까이>dark-cut>전체>cut-in-motion>가까이>screen-dissolve>전체`

| # | 비트 시트 비트 | 비율(%) | 시작–끝(초) | 구도 | 카메라 | 화면 · 부품 (src 경로) | 영상 글자 (video.md 스타일 이름 · 글자 수 · 위치) | 들어옴 · 머묾 · 나감 | 다음 장면으로(전환) |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 1+2 흩어짐 → 하나로 | 10.0 (6.8+3.2) → 9.4 | 0.00–2.27 | 화면 전체 (부품이 가장자리까지 흩어짐 → 가운데 한 덩어리) | `cam-hold` → 부품이 다 사라진 빈 프레임에 `cam-in` 상태로 둠 → `cam-pull` (대상 brand-icon → × 1 · 묶음 자리) → `cam-hold` (비트2 물러남 → 정지) · 조립: `cam-pull` 대상 brand-icon (`screen-reveal` 밖) | 배경 `video-bg-soft` (비트1 어두운 바탕 대신 — skill-card · stat-card 바탕 규칙, video.md 5장) · 폰 없음 · 흩어진 부품 6개 `src/parts/skill-card-1.html` · `skill-card-2.html` · `skill-card-3.html` · `stat-card.html` · `button-submit.html` (`data-state="submit"`) · `badge-approved.html` (모두 × 2.8, video.md 5장) — 화면 네 귀퉁이와 위 · 아래 가장자리 가운데에 반쯤 잘린 채, 가운데는 비움 · asset-card 뺌 (`video-bg`에만) · mission-card 뺌 (가운데를 덮음) · 그다음 `src/parts/brand-icon.html` (× 2.8) + 아래 `video-gap` + `src/parts/logo.html` (`data-state="logotype-black"`, × 2.8) · 묶음 전체 화면 가운데 · `parts-fly` 없음 | 0 (logo · 부품 안 글자만) | 부품 6개 첫 프레임부터 놓여 있음 → `hold-s` → 부품 6개 `scene-out` → 조립: brand-icon `flip-turn` (180° → 0, 뒷면은 안 보임 · `dur-m` · `ease-out` — `logo-reveal`의 `scale-from` · `tilt` 대신 비트2 "세로축으로 돌며 앞면") → `cam-pull` → 멈춘 뒤 logo 글자마다 `enter` · `stagger` 글자 사이 `dur-xs` (`logo-reveal` 뒷부분) → `hold-m` | `transition` (컷, 이어지는 요소 없음 · 비트2) · 대신: `cut-in-motion` |
| 2 | 3 한 단어씩 | 6.8 → 7.5 | 2.27–4.07 | 가까이 (글자 한 줄 · 화면 정가운데) | `cam-hold` | 바탕이 컷마다 바뀜 `video-bg-brand` → `video-bg` → `video-bg-brand` · 폰 없음 · 부품 없음 · 모양 판 없음 (`word-blob` 뺌) · 폰트 `src/assets/fonts/Pretendard-Bold.otf` | 화면 제목 3개 × 1줄, src 문구 그대로: "스킬 라이브러리" (02-skills 제목, 8자) → "이번 달 미션" (03-mission 제목, 6자) → "내 자산" (05-assets 제목, 4자) · `video-display` · `video-text-on-brand` / `video-text` / `video-text-on-brand` · 화면 정가운데 (가운데 정렬, video.md 3장 예외) · 대신: 뼈대 비트3 "동사 6개 · 5–7자 · 마침표" (src에 맞는 동사 문구 없음 → 화면 제목 3개, 마침표 없음) | 조립: 글자 컷 — 줄마다 `enter` → `hold-s` → `transition` (컷, 바탕 · 글자 같이 바뀜) | `transition` (컷 · 비트3, `whip-blur` 뺌 → 흐림 없는 컷) · 다음 첫 프레임은 01-home 화면 속 미션 카드 클로즈 · 대신: `cut-in-motion` |
| 3 | 4+5 흐름 보기 → 가운데 폰 | 13.0 (5.6+7.4) → 13.3 | 4.07–7.27 | 가까이 → 화면 전체 (폰 3대 + 양 끝 반쯤 · 가운데 03-mission이 주인공) | `cam-pull` (`cam-in` 상태, 대상 01-home 화면 속 미션 카드 → × 1 · 01-home 폰 가운데, 비트4) → `cam-pan` 오른쪽 (01-home → 03-mission, 거리 = 폰 두 대 간격, 비트4 끝) → `cam-hold` (비트5) · 조립: `cam-pull` 폰 줄 (`screen-reveal` 밖, 주변 `enter` 없음) · 대신: `한 장면에 카메라는 한 묶음` | 배경 `video-bg-soft` · 폰 프레임 5대 (video.md 4장 `phone-size`) 가로 한 줄 · 폰 사이 `video-gap` (장면4 `plane-tilt`와 같은 줄) · 화면 차례 `src/screens/01-home.png` · `02-skills.png` · `03-mission.png` · `04-approved.png` · `05-assets.png` · 첫 프레임부터 놓여 있음 · 화살표 · 점 격자 · 폰 이름표 없음 (`line-draw` 뺌 · 이름표는 `video-text-min` 아래) · 빈 화면에 부품이 떨어지는 것 없음 (`screen-build` 뺌) · 대신: `폰 한 장면` | 0 (화면 이미지 속 글자만) | 첫 프레임 `cam-in` 클로즈 (컷 너머) → `cam-pull` → `hold-l` (화면 한 장) → `cam-pan` → `hold-l` (폰 3대) | 이어짐 (컷 없음) → `plane-tilt` (비트5) · 대신: `cut-in-motion` |
| 4 | 6 한눈에 | 10.3 → 10.8 | 7.27–9.87 | 멀리 (폰 5대 기운 평면) | `plane-tilt`의 카메라 × 1 → `dolly-scale` → `cam-drift` (`dolly-scale` 상태 그대로 가로 `dist-m`, `hold-l` 동안) → `cam-push` (대상 02-skills 폰 · `dolly-scale` 상태에서 `cut-scale`만큼 더 다가감 · `dur-2xl` · `ease-in`, 멈추지 않음) · 조립: `cam-push` 시작 배율 · 대신: `한 장면에 카메라는 한 묶음` · 대신: `hold 동안 카메라 정지` · 대신: `경계는 scene-out` | 배경 `video-bg-soft` · 장면3과 같은 폰 5대 줄 (01–05) · 평면 가운데 = 03-mission · 평면 위 작은 부품 없음 (`plane-tilt`는 폰만) · 대신: `폰 한 장면` | 0 (폰 화면 글자는 평면과 같이 눕음) | `plane-tilt` (평면 각도 0 → `plane-angle` + 카메라 × 1 → `dolly-scale` · `dur-l` · `ease-inout`) → `hold-l` (그동안 `cam-drift`) → `cam-push` | `transition` (`cam-push` 끝 프레임에서 컷 · 비트6) · 대신: `cut-in-motion` |
| 5 | 7 폰 한 대 · 화면이 바뀜 | 11.6 → 11.7 | 9.87–12.67 | 화면 전체 (2단: 왼쪽 글 · 오른쪽 폰, 묶음 가운데) | `cam-hold` (remotion-device-rise: 카메라는 그대로, 폰이 움직임) | 배경 `video-bg-soft` → 화면 바뀌는 컷에 `video-bg` (비트7 바탕 컷) · 폰 프레임 1대 (video.md 4장 `phone-size`) + `src/screens/02-skills.png` → `src/screens/03-mission.png` · 왼쪽 글 ↔ 폰 `video-gap` · 묶음 전체 화면 가운데 · 양옆 도는 폰 없음 (`phone-trio` 뺌) · 알림 카드(skill-list) 없음 (× 2.8 카드가 폰과 글 칸을 덮음) · 대신: `폰 한 장면` | 제목 1줄, src 문구 그대로: "일에 바로 적용하는 AI" (02-skills 제목, 12자 공백 포함) · `video-display` · `video-text` · 폰 왼쪽 · 왼쪽 정렬 · 화면이 바뀌어도 그대로 · 대신: 뼈대 비트7 "제목 2줄 (윗줄 12자 · 아랫줄 9자)" (아랫줄에 맞는 src 문구 없음 → 1줄) | 폰 `phone-rise-tilt` + 제목 `headline-in` (폰 → 제목 `stagger`, 한 덩어리 · 같은 장면에 `screen-reveal` 없음 [고정]) → `hold-l` (화면 한 장) → 조립: `screen-change` 02 → 03 + 같은 컷에 바탕 `video-bg-soft` → `video-bg` (제목은 그대로) → `hold-l` (화면 한 장) | `transition` (컷 · 비트7) · 대신: `cut-in-motion` |
| 6 | 8 누르는 부품 | 6.8 → 6.4 | 12.67–14.20 | 화면 전체 (가운데 부품 하나 + 아래 한 줄) | `cam-hold` | 배경 `video-bg` · 폰 없음 · `src/parts/button-submit.html` (`data-state="submit"`, × 2.8) · 아래 `video-gap` 글 한 줄 · 묶음 전체 화면 가운데 · 첫 프레임부터 놓여 있음 · 옆에서 날아와 붙는 부품 없음 (`snap-row` 뺌) | 1줄, src 문구 그대로: "파일과 적용 사례를 함께 제출해주세요." (03-mission 안내 문구, 21자 공백 · 마침표 포함) · `video-heading` · `video-text` · 버튼 아래 가운데 · 대신: `부품 장면에는 그 부품만` | 글자마다 `enter` · `stagger` 글자 사이 `dur-xs` (7번째부터 같이) → `button-press` (앞 `hold-m` → 누름 → 뗌) | `transition` (컷, `button-press` 떼는 끝 프레임 · 비트8) |
| 7 | 9 한 줄 선언 | 6.8 → 5.8 | 14.20–15.60 | 가까이 (글자 한 줄 · 화면 정가운데) | `cam-drift` (`hold-s` 동안, 비트9) · 대신: `hold 동안 카메라 정지` | 배경 `video-bg-dark` → `video-bg-soft` (`dark-cut`, 영상 1곳) · 폰 없음 · 부품 없음 · 글자 벽 없음 · 폰트 `src/assets/fonts/Pretendard-Bold.otf` | 1줄, src 문구 그대로: "미션을 완성했어요!" (04-approved 제목, 10자 공백 포함) · `video-display` · `video-text-on-dark` → 바탕 바뀌며 `video-text` · 화면 정가운데 (가운데 정렬) · 대신: 뼈대 비트9 "앞 3자 고정 · 뒤 단어 바뀜" (뒤 단어 바뀜은 길이 때문에 뺌) | `dark-cut` (`transition`으로 들어와 `enter` → `hold-s` (`cam-drift`) → 글자는 두고 바탕만 `video-bg-soft`로 `dur-xl` · `ease-linear`) | `transition` (컷, 바탕이 다 바뀐 끝 프레임 · 비트9 "어둡게 → 밝게") · 대신: `cut-in-motion` |
| 8 | 10+11 승인 → 숫자 | 13.1 (5.6+7.5) → 13.2 | 15.60–18.77 | 화면 전체 (가운데 카드 한 장 + 오른쪽 다음 카드 반쯤 · 카드 줄 기운 평면) | `cam-hold` (카드 줄이 움직임) | 배경 `video-bg-soft` (asset-card는 줄에 없음 → 바탕 바뀜 없음) · 폰 없음 · `card-rail` + `rail-tilt` (`rail-angle`) 카드 2장 차례 `src/parts/mission-card.html` (`--progress` 기본값에서 시작) → `src/parts/stat-card.html` (금액 `#stat-card-amount` 0에서 시작, `data-final`까지) · 모두 × 2.8 · 첫 프레임 mission-card가 화면 가운데, 왼쪽은 빈 바탕 · 카드 세로 가운데 = 줄 가운데 선 · `src/parts/badge-approved.html` (× 2.8)은 줄에 세우지 않고 mission-card 아래 `video-gap-s`, mission-card와 같이 튕김 · brand-icon · 색종이 없음 | 0 (부품 안 글자만 · card-rail 위 제목은 전환 역할 밖이라 뺌) | 컷 너머 첫 프레임부터 `mission-done` (진행 바 · 글자 `emphasis` → `badge-pulse`) → 바로 튕김 1번 (`dur-2xl` · `ease-out`, 카드 사이 hold 없음) → 조립: 튕김이 멈춘 끝에 `count-up` (튕김 도착 = `part-in` 자리) → `hold-m` (card-rail 마지막 카드, `count-up`의 `hold-s`를 덮음) → `scene-out` | `cut-in-motion` (`scene-out` 절반에서 `transition` · 다음 장면 asset-card는 바탕이 달라 이어지는 요소 없음 · 비트11 "이어짐"은 못 따름) |
| 9 | 12 크게 내려앉음 | 9.9 → 10.0 | 18.77–21.17 | 가까이 (카드 한 장 · `cam-push`로 더 가까이) | `cam-hold` → `cam-push` (대상 asset-card · `dur-2xl` · `ease-in`, 멈추지 않음) · 대신: `경계는 scene-out` | 배경 `video-bg` (asset-card 규칙, video.md 5장) · 폰 없음 · `src/parts/asset-card.html` (`data-state="selling"` — "업무 자동화 체크리스트" · "멤버 공개 · 판매 중 · ₩9,900", × 2.8) 하나 · 화면 가운데 · 고리 · 이름표 · 색종이 없음 · 새 메시지 = 내 자산이 판매 중 (BRIEF 흐름 마지막 "에셋") | 0 (부품 안 글자만) · 대신: 뼈대 비트12 "위 숫자 + 큰 글자 2자 + 아래 이름표 15자" (영상 글자 0, 부품 하나) | 조립: asset-card `enter` + 마스크 대신 `cut-scale` → 1 · 투명도 0 → 1 · `dur-m` · `ease-out` (컷 너머 첫 프레임부터) → `hold-l` (카드 하나 · 읽을 글자 15자 넘음) → `cam-push` | 조립: `screen-dissolve`를 `cam-push` 마지막 `dur-m` 동안 (push는 멈추지 않고 dissolve 안에서 끝남 · 비트12 "밀고 들어가며 밝아짐") · 대신: `cut-in-motion` |
| 10 | 13 엔드 | 11.7 → 11.8 | 21.17–24.00 | 화면 전체 (가운데 세로 한 덩어리) | `cam-hold` | 배경 `video-bg-end` (`video-glow` · `video-grain`) · 폰 없음 · `src/parts/logo.html` (`data-state="logotype-white"`, `logo-hero`) · logo ↔ 슬로건 `video-gap-end` · 묶음 전체 화면 가운데 · brand-icon 없음 · 칩 · 주소 · 떠 있는 부품 없음 | 슬로건, src 문구 그대로: "오늘도 하나씩, 내 실력으로" (01-home 제목, 14자 공백 포함) · `video-title` · `video-text-on-dark` · logo 아래 가운데 한 줄 | `screen-dissolve`가 끝난 프레임부터 `end-reveal` (logo 글자마다 `enter` · `stagger` → `dur-l` 뒤 슬로건 투명도 0 → 1 · `dur-l`) → `hold-end` → 마지막 정지 (motion.md 4장 예외) | 끝 |

## 장면 길이 (움직임 + hold 합 = 시작–끝, 빈 hold 0)

24초 × 비트 비율로 잡고, 0장 [고정] "빈 hold로 채우지 않음"에 맞춰 각 장면을 움직임 + hold 합으로 맞췄다 (차이는 모두 ±1.0%p 안, 합계 720f = 24.00초).

| # | 움직임 + hold (motion.md 이름, 프레임) | 장면 | 비트 비율 → 쓴 비율 | 차이 |
|---|---|---|---|---|
| 1 | `hold-s` 12 + `scene-out` 3 + `flip-turn` `dur-m` 6 + `cam-pull` 12 + logo 글자 약 14 (launch-c와 같은 나눔) + `hold-m` 21 | 68f · 2.27초 | 10.0 → 9.4 | −0.6 |
| 2 | (`enter` 6 + `hold-s` 12) × 3 | 54f · 1.80초 | 6.8 → 7.5 | +0.7 |
| 3 | `cam-pull` 12 + `hold-l` 36 + `cam-pan` 12 + `hold-l` 36 | 96f · 3.20초 | 13.0 → 13.3 | +0.3 |
| 4 | `plane-tilt` 12 + `hold-l` 36 + `cam-push` 30 | 78f · 2.60초 | 10.3 → 10.8 | +0.5 |
| 5 | 폰 · 제목 `stagger` 12 + `hold-l` 36 + `hold-l` 36 | 84f · 2.80초 | 11.6 → 11.7 | +0.1 |
| 6 | 글자 `stagger` 16 + `hold-m` 21 + 누름 3 + 뗌 6 | 46f · 1.53초 | 6.8 → 6.4 | −0.4 |
| 7 | `enter` 6 + `hold-s` 12 + 바탕 `dur-xl` 24 | 42f · 1.40초 | 6.8 → 5.8 | −1.0 |
| 8 | `emphasis` 6 + `badge-pulse` 6 + 튕김 30 + `count-up` 30 + `hold-m` 21 + `scene-out` 절반 2 | 95f · 3.17초 | 13.1 → 13.2 | +0.1 |
| 9 | asset-card 등장 6 + `hold-l` 36 + `cam-push` 30 (마지막 6f에 `screen-dissolve`) | 72f · 2.40초 | 9.9 → 10.0 | +0.1 |
| 10 | logo 글자 약 14 + `dur-l` 12 + 슬로건 12 + `hold-end` 45 + 마지막 정지 2 | 85f · 2.83초 | 11.7 → 11.8 | +0.1 |
| 합 | | 720f · 24.00초 | 100 | 10/10 ±1.0 안 |

장면8 (요약 숙제): 처음 짠 것(제목 `headline-in` + `hold-m` · 배지 뒤 `hold-s` · `count-up` 뒤 `hold-s`와 `hold-m`) = 120f(4.0초)라 넘어서, 제목을 빼고 · 배지 뒤 hold를 빼고 (card-rail "카드 사이 hold 없음") · 끝 hold를 `hold-m` 하나로 → 93f + `scene-out` 절반 2f = 95f(3.17초, 비율 +0.1%p). 카드는 2장 (튕김 1번).

## 요약과 달라진 것

- 영상 글자는 전부 src/screens 문구를 글자 하나 바꾸지 않고 씀 (장면2 · 5 · 6 · 7 · 10). 맞는 문구가 없는 칸은 줄이고 `대신:`에 적음 (장면2 동사 → 화면 제목 · 장면5 2줄 → 1줄 · 장면7 단어 바뀜 없음 · 장면9 글자 0).
- 장면5: skill-list(알림 카드 3장) 뺌 — × 2.8 카드(980 폭)가 폰(444 폭)과 왼쪽 제목 칸을 덮음. 대신 비트7 "바탕 · 화면 컷"을 `screen-change` 02 → 03 한 번으로.
- 장면7: `slot-roll`(뒤 단어 바뀜) 뺌 — 넣으면 약 72f(장면 49f 자리). `dark-cut`만.
- 장면8: 위 제목 한 줄 뺌 · 배지 뒤 hold 뺌 (위 숙제) · 끝 전환 `match-cut` → `cut-in-motion`.
- 장면9: stat-card + 크게 내려앉는 badge-approved → asset-card (`selling`) 하나가 크게 내려앉음 (장면8과 같은 부품 반복 · 새 메시지 없음을 고침).
- 장면1: 바탕 `video-bg-soft` (비트1 어두운 바탕은 stat-card · skill-card 바탕 규칙과 맞지 않음).

## 0장 확인

- 폰 한 장면 [기본 스타일]: 장면3 · 4 · 5에 폰 — 칸마다 `대신: 폰 한 장면` (비트4 · 5 · 6 · 7 폰). 엔드에 폰 없음.
- 같은 종류 부품 이웃 장면 합치기 [고정]: 이웃 장면끼리 같은 부품이 이어지지 않음 (장면8 mission-card · stat-card → 장면9 asset-card).
- 부품 장면엔 부품만 [기본 스타일]: 장면6만 글자 한 줄 (`대신:`), 장면8 · 9는 부품만.
- 새 화면 · 메시지 없는 장면 [고정]: 없음 — 1 브랜드 · 2 스킬 → 미션 → 자산 · 3–4 흐름 전체 · 5 스킬 → 미션 화면 · 6 제출 · 7 완성 선언 · 8 승인 → 수익 · 9 판매 중인 자산 · 10 엔드.
- 빈 hold [고정]: 위 표, 빈 hold 0 (장면10 마지막 2f는 4장 예외 마지막 정지).
- 다가간 장면 [기본 스타일]: 장면4 · 9 `cam-push`는 머묾 없이 바로 전환.

## 비트 시트 반영률 (skillry-lnkiai 뼈대, 합친 뒤 10비트)

비트 수 1/1 + 비율 10/10 (±1.0%p 안) + 구도 10/10 + 카메라 10/10 (비트4 `cam-drift` · 비트12 고리는 뺌) + 전환 8/10 (비트9 → 10 원본은 글자 사라진 뒤 바탕 바뀜, 우리는 `dark-cut`대로 글자를 둠 · 비트11 → 12 "이어짐"을 `cut-in-motion`으로) = 39/41 = 95.1% — 80% 넘음: "레퍼런스와 비슷할 수 있음" 경고.
다른 역할: remotion-device-rise(카메라) 장면5 `phone-rise-tilt` · `cam-hold` · snapcn-card-rail(전환) 장면8 튕김 `dur-2xl` · `ease-out` · 카드 사이 hold 없음 · snapcn-phone-frame(구도) 장면3 클로즈 `cam-in` → 폰 전체 정면 · 장면5 폰 한 대 `phone-size`.

- 새 후보 0개 (`?새 후보` 칸 없음).
- 조립은 `work/launch-d/decisions.md` "장면표 detail — 안 a (조립)" · "장면표 detail — 안 a 다시 (조립)".
