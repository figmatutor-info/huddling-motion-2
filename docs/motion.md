# motion.md

런칭 영상용 움직임 기준. 성격: **경쾌함** (2026-10-24 요청 · 분석 기본 제안은 "단정함") · 레퍼런스: inoue-aix (LoreOS 광고 40초, `references/ref-frames/inoue-aix/original.mp4`)
규칙: 이 문서에 있는 값만 쓴다. 장면에서는 Semantic(2장) 이름으로 부르고, Primitive(1장)를 직접 쓰지 않는다.
출처 표기: `레퍼런스 <장면>` = 위 영상에서 프레임으로 잰 값 · `성격: 경쾌함` = 성격에서 정한 값 · `요청` = 요청에서 정한 조건 · `기존` = 전 motion.md에서 유지.
프레임 수는 30fps 기준. 레퍼런스에서 가져오지 않는 것: 프레임 · 에셋 · 음악 · 로고 · 카피 문장 · 색값 (CLAUDE.md 4번 고정 · 참조 · 금지 참고).
규칙 표시: 0장도 [고정] · [기본 스타일]을 구분한다. 0~5장 규칙 끝의 [고정]은 늘 지킨다. [기본 스타일]은 첫 레퍼런스(inoue-aix)에서 온 스타일이라, beat-sheet.md에 다른 규칙이 있으면 그쪽을 따르고 decisions.md에 "기본 스타일 X 대신 비트 시트 Y"로 기록한다. 1장 숫자 · 4장 hold 숫자는 고정.
beat-sheet.md에 해당 규칙이 없으면 [기본 스타일]을 따른다.

---

## 0. 영상 전체 규칙

장면표를 쓰기 전에 먼저 본다. 1~5장보다 앞선다. 규칙 끝 괄호는 근거(날짜 · 반려 내용, work/launch-30s/log.md).

- 폰 프레임은 한 영상에서 한 장면에만 나온다. 나머지 장면은 폰 없이 부품을 화면 가운데에 둔다. 엔드 카드에도 폰을 두지 않는다. (2026-10-24 반려 2: 폰은 장면2만 · 나머지는 UI 확대 · 장면10 폰 뺌) [기본 스타일]
- 같은 종류의 부품을 이어서 보여주는 이웃 장면은 한 장면으로 합친다 (예: 카드 여러 장 → `skill-carousel`). (2026-10-24 반려 2: 장면3+4 합쳐 스킬 카드만) [고정]
- 부품 장면에는 그 부품만 둔다. 제목 · 부제 같은 영상 글자는 글자 장면에서만 쓴다. (2026-10-24 반려 2: 장면6 버튼만 · 스킬 카드만 · 2026-10-24 결정: stat-card 제목 · 부제 없음) [기본 스타일]
- 앞뒤 장면에 없던 화면이나 메시지를 더하지 않는 장면은 뺀다. (2026-10-24 반려 2: 장면5 · 8 삭제) [고정]
- 장면 길이가 그 장면의 움직임과 hold(4장)를 더한 것보다 길면, 빈 hold로 채우지 않는다. 대신 사람에게 BRIEF 길이를 줄이자고 묻는다. (2026-10-24 반려 2: 30초 → hold 규칙대로 약 20초) [고정]
- 카메라가 대상에 다가간 장면은 머묾 컷을 따로 두지 않는다. 그 대상의 동작(`button-press` · `shape-morph`)으로 다음 장면에 넘긴다. (2026-10-24 요청: 장면2 머묾 02 뺌 · 장면2→3 멈춤 해소 → button-press) [기본 스타일]

---

## 1. Primitives

### Duration (6단계)

| 토큰 | ms | 프레임 | 출처 |
|---|---|---|---|
| `dur-xs` | 67 | 2 | 레퍼런스 엔드 로고 (글자 하나씩 올라오는 간격) |
| `dur-s` | 100 | 3 | 레퍼런스 장면 끝 글줄 사라짐 · 입력창 타이핑 한 글자 |
| `dur-m` | 200 | 6 | 레퍼런스 글줄 등장 · 로고 글자 하나 · 폴더 한 줄 |
| `dur-l` | 400 | 12 | 레퍼런스 입력창 줌아웃 (확대 → 전체 화면) |
| `dur-xl` | 800 | 24 | 레퍼런스 "翌朝" 어두운 바탕 → 밝은 바탕 |
| `dur-2xl` | 1000 | 30 | 레퍼런스 아이콘 고리 연결선 그려짐 · 카메라 이동 상한 |

### Easing (넘치지 않는 곡선)

모든 곡선의 y값은 0–1 안에 있다. 목표값을 넘었다 돌아오는 곡선은 없다. (레퍼런스 전체 — 튀거나 넘치는 움직임 없음)

| 토큰 | 값 | 쓰는 곳 | 출처 |
|---|---|---|---|
| `ease-out` | `cubic-bezier(0.16, 1, 0.3, 1)` | 들어오기 · 상태 바뀜 | 레퍼런스 글줄 등장 (6프레임 중 3프레임에 거의 도착) |
| `ease-in` | `cubic-bezier(0.5, 0, 0.75, 0)` | 나가기 · 모이기 | 레퍼런스 아이콘 고리가 로고로 모임 (점점 빨라짐) |
| `ease-inout` | `cubic-bezier(0.65, 0, 0.35, 1)` | 카메라 줌 | 레퍼런스 입력창 줌아웃 |
| `ease-linear` | `linear` | 타이핑 따라가는 카메라 · 바탕 바뀜 | 레퍼런스 입력창 타이핑 · "翌朝" 바탕 |

### Distance · Scale · 기타

| 토큰 | 값 | 출처 |
|---|---|---|
| `mask-rise` | 100% (글줄 높이, 마스크 아래에서 위로) | 레퍼런스 글줄 · 로고 글자 등장 (줄 밖은 잘려 안 보임) |
| `dist-s` | 8px | 레퍼런스 폴더 줄 · 파일 칩 (옆에서 살짝) |
| `dist-m` | 24px | 레퍼런스 "翌朝" 결과 카드 (위에서 차례로 쌓임) |
| `dist-l` | 70px | 요청 (2026-10-24, snapcn phone-frame `rise` · `cam-crane` 시작 위치) |
| `press-scale` | 0.96 | 요청 (2026-10-24, 버튼 누름) |
| `scale-from` | 0 | 레퍼런스 엔드 로고 L 아이콘 · "1ヶ月無料" 배지 (점에서 커짐) |
| `tilt` | 15deg → 0 | 레퍼런스 엔드 로고 L 아이콘 (기운 채 커지며 바로 섬) |
| `cam-in` | × 2.4 | 레퍼런스 입력창 (화면 폭을 입력창 하나가 채움) |
| `dim` | 투명도 0.4 | 레퍼런스 "探さない。まとめない。" (지운 줄이 흐려짐) |
| `type-step` | 100ms (3프레임) = `dur-s` | 레퍼런스 입력창 타이핑 (한 글자 간격) |
| `cut-scale` | × 1.7 (컷 너머 클로즈 크기) | 요청 (2026-10-24, snapcn wordmark-cut 1.71배) |
| `crane-angle` | rotateX 12° · rotateY -18° (왼쪽 아래에서 올려다봄) · perspective 2400px · 회전 중심 폰 가운데 | 요청 (2026-10-24, snapcn phone-frame `showcase`) |
| `flip-turn` | rotateY 180° (세로축 뒤집힘 반 바퀴) · perspective 2400px (`crane-angle`과 같음) · 회전 중심 부품 가운데 | 요청 (2026-10-25, launch-c 후보 승인 · 1password 격자 뒤집힘 · langease 카드 뒤집힘) |
| `spin` | rotateZ 360° (제자리 한 바퀴) · 회전 중심 부품 가운데 | 요청 (2026-10-25, launch-c 후보 승인 · 1password 아이콘 회전 측정 약 6f) |
| `dolly-scale` | × 0.5 (× 1보다 멀리) | 요청 (2026-10-25, launch-c 후보 승인 · 1password 그물 줌아웃 측정 끝 배율 약 × 0.5) |
| `ring-count` | 4 (둘레에 놓는 같은 요소 수) | 요청 (2026-10-25, launch-c 후보 승인 · langease 폰 터널 4대 · 흩어진 카드 4장) |
| `plane-angle` | rotateX 55° · rotateZ -20° (흐름도 평면이 뒤로 눕고 비스듬히 돎) · perspective 2400px (`crane-angle`과 같음) · 회전 중심 평면 가운데 | 요청 (2026-10-25, launch-d 후보 승인 · skillry lnkiai 비트 6 측정 그대로) |
| `rail-angle` | rotateX 20° (카드 줄 바닥만 뒤로 얕게 눕힘, rotateY · rotateZ 0) · perspective 2400px · 회전 중심 줄 가운데 | 요청 (2026-10-25, launch-d 후보 승인 · snapcn card-rail 아래 폭 약 1.2배) |

---

## 2. Semantic

5개뿐이다. 변형은 만들지 않고, 3장 Pattern에서 "Semantic + 차이"로 적는다.

| 토큰 | 구성 | 출처 |
|---|---|---|
| `enter` | `dur-m` · `ease-out` · 마스크 안에서 아래 `mask-rise` → 0 (투명도는 바꾸지 않음, 마스크가 가림) | 레퍼런스 글줄 등장 |
| `exit` | `dur-s` · `ease-in` · 제자리에서 투명도 1 → 0 | 레퍼런스 장면 끝 (거의 컷처럼 짧게) |
| `emphasis` | 상태 한 번 바뀜 (값 · 테두리 · 채움 시작 → 최종) · `dur-m` · `ease-out` · 크기 변화 없음 | 레퍼런스 폴더 파일 칩 하이라이트 |
| `transition` | 0ms 컷 (길이 · 곡선 [고정]). 다음 장면 첫 프레임에 이미 `enter` 중 | 레퍼런스 장면 경계 (전부 컷, 밀기 · 페이드 없음) [기본 스타일] |
| `stagger` | 항목 · 줄 사이 `dur-m`, 글자 사이 `dur-xs`. 6개를 넘으면 7번째부터 같이 | 레퍼런스 폴더 줄 · 엔드 로고 글자 · 6개 상한은 기존 |

---

## 3. Pattern

src/parts · src/screens에 있는 것만. Semantic 이름으로 적고, 다른 점만 `+`로 붙인다 (차이도 1장 토큰 이름으로).

| 패턴 | 대상 | 움직임 (Semantic + 차이) | 출처 |
|---|---|---|---|
| `headline-in` | 화면 제목 · 부제 (01–05) | 줄마다 `enter`, 줄 사이 `stagger` | 레퍼런스 "9つのサービスと / 連携。" |
| `text-type` | 훅 제목 한 줄 | 글자가 `type-step`마다 하나씩 그냥 나타남 (움직임 없음) · 끝 글자 뒤 커서 (폭 6px · 끝 글자와 6px 띄움 · 높이는 그 글자 스타일 행간, video.md 3장). 카메라 `cam-follow`와 같이 | 레퍼런스 입력창 타이핑 · 요청 (2026-10-24, 커서 치수) |
| `word-strike` | 앞서 보인 제목 줄 | 다음 줄 `enter`와 같이 시작: 취소선이 왼쪽 → 오른쪽 `dur-m` · `ease-out` + 그 줄 투명도 → `dim` | 레퍼런스 "探さない。まとめない。" |
| `logo-reveal` | brand-icon → logo | brand-icon `enter` + 마스크 대신 `scale-from` → 1 · `tilt` → 0 → logo(logotype) 글자마다 `enter`, 글자 사이 `stagger`. 엔드 카드에서는 brand-icon 없이 logo 글자 `enter`만 (logotype 안에 심볼이 있음) | 레퍼런스 엔드 로고 "L LoreOS" · 요청 (2026-10-24, 엔드 아이콘 뺌) |
| `end-reveal` | 엔드 카드 logo + 슬로건 | `logo-reveal` → `dur-l` 뒤 슬로건 `enter` + 마스크 대신 투명도 0 → 1 · `dur-l` | 레퍼런스 엔드 "loreos.jp" |
| `chip-row` | 카테고리 칩 (01 · 02 · 05) | 칩마다 `enter` + 마스크 대신 왼쪽 `dist-s` · 투명도 0 → 1, `stagger` | 레퍼런스 폴더 줄 |
| `skill-list` | skill-card-1 · 2 · 3 (02 화면에 보이는 3장 · 01은 skill-card-1 한 장뿐이라 `part-in`) | 카드마다 `enter` + 마스크 대신 위 `dist-m` · 투명도 0 → 1, `stagger` | 레퍼런스 "翌朝" 결과 카드 |
| `skill-carousel` | skill-card-1 · 2 · 3 (폰 없이) | 카드 3장 가로 한 줄 → 한 장씩 왼쪽으로, 거리 = 카드 폭 + `video-gap` (video.md 3장) · `dur-l` · `ease-inout`, 카드마다 `hold-m` | 요청 (2026-10-24, 스킬 카드 캐러셀) |
| `count-up` | stat-card 금액 | 카드 `part-in` 바로 뒤 (사이 hold 없음) 0 → 최종값 · `dur-2xl` · `ease-out` · 정수 단위, 끝나면 `hold-s` | 요청 (2026-10-24, 새 후보에서 승인) |
| `button-press` | button-submit (화면 이미지 속 같은 버튼 자리에 겹쳐도 됨 — 겹침 · 덮개판은 video.md 4장 · 03-mission 제출하기 자리는 video.md 4장) | 앞 hold는 `hold-m` (글자 수와 관계없이, 누를 대상을 보는 시간) → 누름 1 → `press-scale` (중심: 버튼 가운데) · `dur-s` · `ease-in` → 뗌 `press-scale` → 1 · `dur-m` · `ease-out` → 떼는 끝 프레임에 다음 장면으로 `transition` (컷, `scene-out` 없음) | 요청 (2026-10-24, 씬2 → 씬3 멈춤 해소 · 새 후보에서 승인) |
| `asset-list` | asset-card (05 화면에 보이는 3장) | `skill-list`와 같음 | 레퍼런스 "翌朝" 결과 카드 |
| `part-in` | 부품 하나 (mission-card · stat-card · button-submit) | `enter` + 마스크 대신 위 `dist-m` · 투명도 0 → 1 | 레퍼런스 "翌朝" 결과 카드 |
| `mission-in` | mission-card (01 · 03) | `part-in` → 진행 바 · 진행 글자 `emphasis` (값 시작 → 최종) | 레퍼런스 결과 카드 · 파일 칩 하이라이트 |
| `mission-done` | mission-card 진행 100% (03 → 04) | 진행 바 · 글자 `emphasis` → `badge-pulse` | 레퍼런스 파일 칩 하이라이트 · 배지 |
| `badge-pulse` | badge-approved (04) | `enter` + 마스크 대신 `scale-from` → 1 | 레퍼런스 "1ヶ月無料" 배지 |
| `screen-reveal` | 폰 화면 (01–05) 한 부분(01 mission-card · 02 첫 skill-card · 03 mission-card · 04 badge-approved · 05 stat-card) → 전체 | `cam-in` 상태로 시작 → `cam-pull` → 멈춘 뒤 주변 요소 `enter` + 마스크 대신 투명도 0 → 1, `stagger`. 폰은 첫 프레임부터 제자리에 있고 `cam-pull` 동안 화면 안으로 들어온다 (폰에 따로 `enter` 없음, 빈 바탕 프레임 없음) | 레퍼런스 입력창 → 채팅 화면 (주변 UI는 줌아웃하며 이미 있음) · 요청 (2026-10-24, 폰 전환 어색) |
| `screen-change` | 01 → 02 → 03 → 04 → 05 | `transition` | 레퍼런스 장면 경계 |
| `dark-cut` | 강조 전환 (한 영상에 1곳) | `transition`으로 `video-bg-dark`에 들어와 제목 `enter` → `hold-s` → 글자는 두고 바탕만 다음 밝은 바탕으로 `dur-xl` · `ease-linear` (글자 색은 video.md 규칙대로 같이 바뀜) | 레퍼런스 "翌朝。" |
| `scene-out` | 장면 끝 요소 전체 | 한꺼번에 `exit` (stagger 없음) | 레퍼런스 장면 끝 |
| `match-cut` | 장면 경계 (같은 요소가 양쪽에 있을 때) | `transition`. 이어지는 요소(brand-icon · logo · 숫자)는 다음 장면 첫 프레임에 같은 자리 · 같은 크기. 바탕 · 주변만 바뀜 | 레퍼런스 L 아이콘 (로고 → 고리 가운데 → 폴더 맨 위) |
| `shape-morph` | 장면 경계 (button-submit → 다음 장면 주인공 부품) | 버튼 글자 `exit` → 버튼 가로 폭이 높이와 같아질 때까지 줄어 원이 됨 · `dur-m` · `ease-in` → 원이 `scale-from`까지 줄어듦 · `dur-m` · `ease-in` → 그 점 자리에서 `transition`, 다음 장면 주인공이 같은 자리에서 `scale-from` → 1 · `dur-m` · `ease-out` (사이 hold 없음, 빈 바탕 프레임 없음) | 요청 (2026-10-24, skillry saadpastadev 검색창 → 점 → 차트 · 측정 9f · 7f · 5f · 6f) |
| `slot-roll` | 영상 글자 두 줄 (윗줄 고정 · 아랫줄 단어만 바뀜) | 아랫줄: 나가는 단어와 다음 단어가 세로로 붙은 한 덩어리로 마스크 안에서 같이 위로 `mask-rise`만큼 · `dur-s` · `ease-out` (같은 거리 · 같은 곡선이라 두 단어는 겹치지 않는다). 단어 간격은 `dur-l`로 시작해 한 번마다 짧아져 마지막 간격 `dur-m` (점점 빨라짐). 단어는 최대 6개, 각 단어는 줄 가운데 정렬 (윗줄은 움직이지 않음). 마지막 단어 뒤 `hold-m` | 요청 (2026-10-24, skillry saadpastadev "Buy + 회사명" · 측정 구름 3–4f · 간격 10f → 7f · 끝 25f) |
| `punch-cut` | 엔드 카드 logo (와이드 → 클로즈) | `logo-reveal` → `hold-s` → `transition` (컷) → 다음 프레임에 같은 logo가 `cut-scale`, 프레이밍 기준은 logotype 안 심볼 (심볼을 화면 가운데). 클로즈 샷에는 logo만 둔다 (와이드에 있던 슬로건 등은 컷에서 빠짐). 컷 뒤 움직임 없음 → `hold-end` | 요청 (2026-10-24, snapcn wordmark-cut 와이드 → 클로즈 하드컷 · 뒤 push · 오버슈트는 빼기로) |
| `cut-in-motion` | 장면 경계 (이어지는 요소가 없을 때) | `scene-out`이 절반 진행된 프레임에서 `transition` (빈 바탕 프레임 없음) | 레퍼런스 "あとは毎日" → 엔드 |
| `phone-rise-tilt` | 폰 프레임 등장 | 아래 `dist-l` · `crane-angle`에서 위치 0 · 각도 0으로 · `dur-l` · `ease-out` | 기존 이름 · 2026-10-25 토큰 조립 |
| `phone-tip` | 장면 경계 (폰이 나갈 때) | 각도 0 → `crane-angle` + `exit` · `dur-l` · `ease-in` → 끝 프레임에 `transition` | 기존 이름 · 2026-10-25 토큰 조립 |
| `screen-dissolve` | 장면 경계 (앞 화면 → 다음 화면, 이어지는 요소가 없을 때) | 앞 화면 투명도 1 → 0과 다음 화면 투명도 0 → 1이 같은 시간에 · `dur-m` · `ease-inout`. 다음 화면은 제자리에서 나타나고 위치 · 크기는 바뀌지 않음. 끝난 프레임부터 다음 장면의 `enter` 시작 (빈 바탕 프레임 없음) | 2026-10-25 요청 (skillry saadpastadev 화면 겹침 · 측정 4f · 10f · 12f → `dur-m`) |
| `zoom-through` | 장면 경계 (부품 안으로 들어가며) | 대상 부품 쪽으로 × 1 → `cam-in` · `dur-l` · `ease-in` → 끝 프레임에 `transition`. 다음 장면 첫 프레임은 그 부품 자리에서 이어짐 (`match-cut`처럼) | 기존 이름 · 2026-10-25 토큰 조립 |
| `icon-expand` | 장면 경계 (부품이 커져 다음 바탕이 됨) | 부품 글자 `exit` → 부품이 화면을 덮을 때까지 커짐 · `dur-m` · `ease-in` → `transition`, 다음 장면 바탕이 그 색 | 기존 이름 · 2026-10-25 토큰 조립 |
| `word-swap` | 영상 글자 한 단어 자리 → brand-icon (video.md `icon-inline`) | 단어 `exit` → 같은 자리에 brand-icon `enter` + 마스크 대신 `scale-from` → 1 | 기존 이름 · 2026-10-25 토큰 조립 (`word-close`를 합침) |
| `flip-wave` | 같은 부품 여러 개 격자 (brand-icon → badge-approved, 또는 asset-card · skill-card 같은 부품끼리) | 부품마다 `flip-turn` × 3 · `dur-m` · `ease-out`, 90°를 지나는 프레임에 앞면이 다음 상태로 바뀜 · 왼쪽 위부터 대각선 순서로 `stagger` (6개 상한 그대로, 7번째부터 같이) | 요청 (2026-10-25, launch-c 후보 승인 · 1password 비트 2, 측정 한 개 약 6f · 물결 약 1.2초) |
| `icon-spin` | brand-icon | `spin` · `dur-m` · `ease-out` + 같은 자리에 brand-icon 모양 고리 하나가 `color-primary`로 × 1 → `cut-scale` · 투명도 0.45 → 0 (`video-glow` 가운데 불투명도) · `dur-l` · `ease-out`. 블러 없음 | 요청 (2026-10-25, launch-c 후보 승인 · 1password 비트 4 · 10, 측정 회전 6f · 빛 12f) |
| `phone-ring` | 폰 프레임 `ring-count`대 (화면 이미지 01–05, video.md 4장 크기 그대로) · 가운데 영상 글자 한 줄 | 폰이 화면 위 · 아래 · 왼쪽 · 오른쪽 가장자리 가운데에 반쯤 잘린 채 놓임, 각 폰은 `crane-angle`을 가운데 쪽으로 돌린 각도 (반대편은 부호 반대). 들어옴: 화면 밖 → 자리 · `crane-angle` 각도 그대로 · `dur-xl` · `ease-out`, 폰 사이 `stagger`. 머묾: 둘레 전체 rotateZ 0 → `tilt` · hold 길이 동안 · `ease-linear`. 나감: `phone-tip` 묶음으로. 0장 "폰 한 장면" [기본 스타일] 대신이므로 비트 시트에 있을 때만 · `대신:` 기록 | 요청 (2026-10-25, launch-c 후보 승인 · langease 비트 6–7, 측정 들어옴 약 22f · 머묾 약 70f) |
| `bar-stretch` | button-submit → mission-card 진행 바 | 버튼 글자 `exit` → 버튼 폭이 mission-card 진행 바 폭으로 · 높이가 진행 바 높이로 (design.md 4장 mission-card 치수 × `video-scale`) · 오른쪽으로 늘어남 · `dur-l` · `ease-inout` · 카메라는 `cam-pan`으로 늘어나는 끝을 따라감 → 끝 프레임에 `match-cut`으로 mission-card의 진행 바 자리 (`mission-in` 진행 `emphasis`가 이어짐) | 요청 (2026-10-25, launch-c 후보 승인 · langease 비트 8, 측정 약 30f · 카메라 회전은 뺌) |
| `focus-lift` | 화면 · 목록 속 부품 하나 (skill-card · asset-card) | 대상 부품 위 `dist-m` · `dur-l` · `ease-out` + 같은 시간에 주변 요소 전부 `exit` (투명도 1 → 0, 길이는 `dur-l`로). 블러 없음 · 크기 변화 없음 | 요청 (2026-10-25, launch-c 후보 승인 · langease 비트 13, 측정 약 11f · 심도 흐림은 뺌) |
| `card-flip-scatter` | 카드 한 장 (skill-card · asset-card) → 같은 카드 `ring-count`장 | 카드 `flip-turn` · `dur-m` · `ease-in` → 뒤집힌 끝 프레임에 같은 카드 `ring-count`장으로 나뉘어 화면 네 귀퉁이(반쯤 잘림)로 · 각 카드 `crane-angle`을 가운데 쪽으로 · `dur-l` · `ease-out`. 다음 글자 장면 둘레로 남고, 머무는 동안 `cam-drift` 쓸 수 있음 (비트 시트에 있을 때) | 요청 (2026-10-25, launch-c 후보 승인 · langease 비트 13–14, 측정 뒤집힘 약 7f · 흩어짐 약 10f) |
| `icon-flight` | brand-icon (통째, 조각 아님) | 화면 오른쪽 밖 → 영상 글자 줄 끝 자리 · 위로 볼록한 곡선 (높이 `dist-l`) · `dur-l` · `ease-out`. 꼬리 없음. 글자가 붙는 동안 줄 끝을 따라 `video-gap` 띄워 붙어 감 (`stagger`와 같은 박자). 끝: 글자 `exit` → `match-cut`으로 logo 심볼 자리 | 요청 (2026-10-25, launch-c 후보 승인 · langease 비트 18–19, 측정 나감 약 4f · 들어옴 약 10f · 꼬리 · 별 조각은 뺌) |
| `card-rail` | 서로 다른 카드 부품 가로 한 줄 (폰 없이, 흐름 순서: skill-card → mission-card → stat-card → asset-card) | `skill-carousel`처럼 한 장씩 왼쪽으로 튕김 · `dur-2xl` · `ease-out` · 카드 사이 hold 없음, 마지막 카드 뒤 `hold-m`. 거리 = 두 카드 가운데 사이 (카드 폭이 같으면 카드 폭 + `video-gap`). 세로: 모든 카드의 세로 가운데를 줄 가운데 선에 맞춤. 바탕: `video-bg-soft`, asset-card로 넘어가는 튕김 동안 `video-bg`로 · `dur-2xl` · `ease-linear` (video.md 5장 예외). badge-approved는 줄에 세우지 않고 mission-card가 가운데 멈췄을 때 `mission-done`으로 보여줌 (그 동안 다음 튕김 대기) | 요청 (2026-10-25, launch-d 후보 승인 · snapcn card-rail 비트 1–3, 측정 튕김 30f 간격) |
| `plane-tilt` | 폰 프레임 5대 (화면 01 → 05, video.md 4장 `phone-size` 그대로) 가로 한 줄 흐름도 · 폰 사이 `video-gap` | 평면 전체가 각도 0 → `plane-angle` + 같은 시간에 카메라 × 1 → `dolly-scale` · `dur-l` · `ease-inout`, 이후 그 각도로 머묾. 폰 화면 글자는 평면과 같이 눕는다 (영상 글자는 두지 않음). 0장 "폰 한 장면" [기본 스타일] 대신이므로 비트 시트에 있을 때만 · `대신:` 기록 | 요청 (2026-10-25, launch-d 후보 승인 · skillry lnkiai 비트 6, 측정 약 11f · 폰 높이 63% → 25%) |
| `rail-tilt` | `card-rail` · `skill-carousel`의 카드 줄 | 카드 줄 평면을 `rail-angle`로 눕힌 채 처음부터 놓음 (눕는 움직임 없음). 위 고정 영상 글자는 눕히지 않음. 튕김은 눕힌 평면 위에서 그대로 | 요청 (2026-10-25, launch-d 후보 승인 · snapcn card-rail 기운 평면) |

- 장면 경계는 `match-cut`을 먼저, 이어지는 요소가 없으면 `cut-in-motion`. button-submit에서 나갈 때는 `shape-morph`를 쓸 수 있다. 주인공 요소는 같은 자리에 둬서 경계에서 눈이 움직이지 않게 한다. (레퍼런스 L 아이콘) [기본 스타일]
- 강조 색 글자(둘째 줄 색 바꿈)는 움직임이 아니다. 색은 video.md에서만. [고정]
- `phone-rise-tilt`와 `screen-reveal`은 한 장면에 같이 쓰지 않는다 (폰 등장은 둘 중 하나). [고정]

### 새 후보 (승인 전엔 쓰지 않음)

docs에 없는 숫자가 필요하거나, 대상 부품 · 화면이 없는 것. 쓰려면 먼저 묻는다.

| 후보 | 무엇 | 왜 후보인가 |
|---|---|---|
| `orbit-collapse` | 서비스 아이콘 고리가 `dur-l` · `ease-in`으로 가운데 로고에 빨려 들어감 | 레퍼런스 "連携。" · 서비스 아이콘 부품 없음 |
| `line-draw` | 아이콘 사이 연결선이 `dur-2xl`로 그려짐 | 레퍼런스 "連携。" · 연결선 부품 없음 |
| `modal-dismiss` | 등록 후 창이 줄며 빠지고 위에 알림이 내려옴 | 레퍼런스 "登録する" · 모달 부품 없음 |
| `whip-blur` | 전환 중 흐림 | 흐림 값이 docs에 없음 |
| `grid-collapse` (승인 2026-10-25 · 부품 대기) | 격자가 한 줄로 모여 입력창이 되고 점이 하나씩 채워짐 | 입력창 · 비밀 점 부품이 src에 없음. 부품이 들어오면 Pattern으로 (1password 비트 3) |
| `orbit-in` (승인 2026-10-25 · 부품 대기) | brand-icon 둘레에 서비스 로고가 하나씩 `scale-from`으로 붙음 | 서비스 로고 부품이 src에 없음 (다른 회사 로고는 CLAUDE.md 4번 금지) · 6개 넘는 stagger (1password 비트 8) |
| `confetti` (승인 2026-10-25 · 부품 대기) | 완료 순간 색종이가 터져 흩날림 | 색종이 부품이 src에 없음 (langease 비트 10) |
| `cursor-tap` (승인 2026-10-25 · 부품 대기) | 손 커서가 대상을 가리키고 누름 | 커서 부품이 src에 없음. 그동안은 커서 없이 `button-press` (langease 비트 12 · 15–17) |

---

## 4. 머무는 시간

움직임이 **끝난 뒤** 화면이 멈춰 있는 시간. 읽을 수 있어야 다음으로 넘어간다.

| 토큰 | ms | 프레임 | 쓰는 곳 | 출처 |
|---|---|---|---|---|
| `hold-s` | 400 | 12 | 배지 · 숫자 하나 · `dark-cut` 첫 제목 | 레퍼런스 "翌朝。" (바탕 바뀌기 전 0.4초) |
| `hold-m` | 700 | 21 | 제목 한 줄 · 카드 하나 | 기존 15초 박자 (레퍼런스 40초판은 약 1000) |
| `hold-l` | 1200 | 36 | 화면 한 장 전체 (목록 포함) | 기존 15초 박자 (레퍼런스 40초판은 약 2000) |
| `hold-end` | 1500 | 45 | 엔드 카드 (`end-reveal` · `logo-reveal`) | 기존 15초 박자 (레퍼런스 40초판은 약 3000) |

- 읽을 글자가 15자를 넘으면 한 단계 위 hold를 쓴다. 올려도 `hold-l`까지 — `hold-end`는 엔드 카드 전용. (기존) [고정]
- 같은 장면에서 다음 움직임은 앞 움직임의 hold가 끝난 뒤 시작한다. stagger와 `word-strike`는 예외. (레퍼런스 줄마다 읽을 틈) [기본 스타일]
- 한 덩어리로 같이 들어오는 요소(제목 + 버튼 등)는 `stagger`로 같이 들어오고 hold는 한 번만. (기존) [고정]
- 예외: 영상 마지막 hold는 멈춰도 된다 (엔드 카드). (레퍼런스 엔드) [기본 스타일]
- hold 동안 카메라는 멈춰 있다. 경계는 `scene-out`으로 넘긴다. (레퍼런스 — 머무는 동안 카메라 정지) [기본 스타일]

---

## 5. 카메라

화면(폰 프레임 · 부품)을 찍는 가상 카메라. 요소 움직임과 따로 둔다.

| 토큰 | 구성 | 쓰는 곳 | 출처 |
|---|---|---|---|
| `cam-hold` | × 1 정지 | 기본 (대부분의 장면) | 레퍼런스 제목 장면 전부 |
| `cam-follow` | `cam-in` 상태에서 가로 이동 · 글자가 늘어나는 속도 그대로 · `ease-linear` | `text-type` 동안 커서 쪽으로 | 레퍼런스 입력창 타이핑 |
| `cam-pull` | `cam-in` → × 1 · 대상에서 전체 화면 가운데로 · `dur-l` · `ease-inout` | `screen-reveal` | 레퍼런스 입력창 줌아웃 |
| `cam-crane` | `crane-angle` · × 1 · 폰이 머묾 자리보다 아래 `dist-l` → 각도 0 · 위치 0 · `cam-in`, 대상 쪽으로 올라오며 줌인 (각도 · 위치 · 줌이 같은 시간에 같은 곡선으로) · `dur-2xl` · `ease-inout`. 다음 `cam-pull`은 생략할 수 있다 — 생략하면 `cam-in` 상태로 hold 후 장면을 끝낸다 (한 묶음) | 폰이 처음 나오는 장면 (`screen-reveal` 앞) | 요청 (2026-10-24, snapcn phone-frame `showcase`) |
| `cam-focus` | × 1 → `cam-in` · 전체 가운데에서 대상으로 · `dur-l` · `ease-inout` (`cam-pull`의 반대) | 부품 하나를 가까이 볼 때 | 기존 이름 · 2026-10-25 토큰 조립 |
| `cam-release` | `cut-scale` → × 1 · `dur-2xl` · `ease-out`. 그동안 요소 `enter`가 같이 진행됨 | 장면을 천천히 열 때 (비트 시트에 그 카메라 · 전환이 있을 때만) | 기존 이름 · 2026-10-25 토큰 조립 |
| `cam-push` | × 1 → `cut-scale` · 대상 쪽으로 · `dur-2xl` · `ease-in` (점점 빨라짐, 멈추지 않고 다음은 `transition`) | 장면을 밀어붙이며 끝낼 때 (비트 시트에 그 카메라 · 전환이 있을 때만) | 기존 이름 · 2026-10-25 토큰 조립 |
| `cam-pan` | × 1 그대로 다음 대상까지 가로 · 세로 이동 (거리 = 두 대상 사이) · `dur-l` · `ease-inout` | 한 화면 안에서 대상을 옮겨 갈 때 | 기존 이름 · 2026-10-25 토큰 조립 |
| `cam-drift` | × 1 그대로 가로 `dist-m` · hold 길이 동안 · `ease-linear` | hold 중 화면을 살짝 살려 둘 때 (비트 시트에 그 카메라 · 전환이 있을 때만) | 기존 이름 · 2026-10-25 토큰 조립 |
| `cam-dolly-out` | × 1 → `dolly-scale` · 화면 가운데 기준 · hold 길이 동안 · `ease-linear` (`cam-drift`처럼 머묾과 같이 감) | 엔드 앞 전체를 한 번 넓게 볼 때 (비트 시트에 그 카메라가 있을 때만, 영상에 1곳) | 요청 (2026-10-25, launch-c 후보 승인 · 1password 비트 9, 측정 약 4.5초) |

- 확대는 `cam-in`(× 2.4)을 넘지 않고, 축소는 `dolly-scale`(× 0.5) 아래로 가지 않는다. [고정]
- 한 장면에 카메라는 한 묶음 (`cam-follow` → `cam-pull` 또는 `cam-crane` → `cam-pull`, `cam-crane`만, 또는 `cam-focus` · `cam-pan` · `cam-drift` · `cam-dolly-out` · `cam-release` · `cam-push` 중 하나). (레퍼런스) [기본 스타일]
- 카메라가 움직이는 동안 요소의 `enter` · `emphasis`를 시작하지 않는다. 멈추고 나서 시작한다 (예외: `cam-follow`는 `text-type`과 같이). (레퍼런스 줌아웃 뒤 주변 등장) [기본 스타일]
- `cam-drift` · `cam-dolly-out` · `cam-release` · `cam-push`는 비트 시트에 그 카메라 · 전환이 있을 때만 쓴다. 그때는 4장 "hold 동안 카메라 정지" · "경계는 `scene-out`", 5장 "카메라 움직이는 동안 요소 시작 안 함" 중 해당 [기본 스타일]을 대신하고 decisions.md에 기록한다. [고정]
