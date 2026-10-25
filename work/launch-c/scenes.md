합침: 비트1+2+3 · 비트4+5+6 · 비트8+9 · 비트10+11 (BRIEF 길이 = 움직임+hold 합계 18.52초 기준 1.5초 미만 비트 1 · 2 · 3 · 4 · 5 · 6 · 8 · 10. 비트6(1.43초)은 비트4+5와 합침 — 비트5→6이 같은 바탕 위 `cam-pan`으로 끊김 없이 이어지고, 비트4+5만으로는 장면1에 있던 brand-icon 말고 새 화면 · 메시지가 없어서 (motion.md 0장). 구도 · 카메라는 우리 부품으로 만들 수 있는 쪽 비트 — 1+2+3은 비트2 구도 + 비트1 카메라, 4+5+6은 비트4 · 6 구도 + 비트4 → 6 카메라, 8+9는 비트9 구도 + 비트8 → 9 카메라, 10+11은 비트11 · 전환은 마지막 비트의 전환)
한 줄 요약: 안 a — 뼈대 그대로 "하나가 여럿으로, 다시 하나로". brand-icon 격자가 승인으로 뒤집힌 뒤, 컷 너머 주인공 아이콘이 돌고 오른쪽 첫 스킬 카드로 이어지며, 카메라가 아래로 제출 → 미션 → 승인 → 수익 → 에셋 부품을 한 장씩 보고, 다시 주인공에서 전부 한 그물로 물러났다 로고로 모인다. 영상 글자는 엔드 슬로건뿐.
비트 구성: `5비트 · 전체>컷>가까이>cam-pan>가까이>컷>멀리>match-cut>전체`

| # | 비트 시트 비트 | 비율(%) | 시작–끝(초) | 구도 | 카메라 | 화면 · 부품 (src 경로) | 영상 글자 (video.md 스타일 이름 · 글자 수 · 위치) | 들어옴 · 머묾 · 나감 | 다음 장면으로(전환) |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 1+2+3 하나에서 여럿 → 여럿이 확인됨 → 모여서 하나 | 10.6 (2.6+5.6+2.4) | 0.00–2.10 | 가까이 → 화면 전체 | `cam-pull` (비트1: `cam-in` 상태, 대상 = 격자 첫 줄 가운데 brand-icon → × 1 · 전체 가운데) → `cam-hold` (비트2) · 조립: `cam-pull` 대상 brand-icon 격자 (`screen-reveal` 밖, 주변 `enter` 없음) | 배경 `video-bg-soft` · 폰 없음 · `src/parts/brand-icon.html` × 6 (× 2.8, video.md 5장) 2줄 × 3칸 격자 · 칸 사이 `video-gap` · 격자 전체 화면 가운데 · 첫 프레임부터 놓여 있음 · 뒤집힌 앞면 `src/parts/badge-approved.html` × 6 (같은 칸 가운데) · 입력창 · 비밀 점 없음 (`grid-collapse` 쓰지 않음) | 0 | `cam-pull` → 멈춘 뒤 `flip-wave` (brand-icon → badge-approved, 왼쪽 위부터 대각선 `stagger`, 6개라 상한 안) → `hold-s` (배지) → 나감 조립: 격자 전체 × 1 → `scale-from` · `dur-s` · `ease-in` (langease 깊이 컷 나감) | 조립: 깊이 컷 = 위 나감 끝 프레임에 `transition` (컷) → 장면2 `cam-release`로 들어옴 · 대신: `cut-in-motion` |
| 2 | 4+5+6 주인공 등장 → 연결 → 첫 쓰임새 | 20.2 (4.8+7.7+7.7) | 2.10–5.00 | 가까이 (아이콘 하나 → 카드 한 장) | `cam-release` (`cut-scale` → × 1, 대상 brand-icon, 비트4) → `cam-pan` 오른쪽 (brand-icon → skill-card-1, 비트5→6) → `cam-hold` (비트6) · 대신: `한 장면에 카메라는 한 묶음` | 배경 `video-bg-soft` (skill-card 규칙, video.md 5장) · 폰 없음 · 한 바탕 위에 `src/parts/brand-icon.html` (× 2.8) 화면 가운데 · 오른쪽 화면 밖(한 화면 폭 너머)에 `src/parts/skill-card-1.html` (× 2.8) 이미 놓여 있음 → 카메라 멈춘 프레임에 카드가 화면 가운데 · 연결선 · 자물쇠 · 상대 아이콘 · 노드 아이콘 · 작은 항목 칩 없음 (`line-draw` 쓰지 않음, 연결은 `cam-pan`이 대신 · 0장 "부품 장면에는 그 부품만") · 다음 부품(button-submit)은 왼쪽 아래 화면 밖에 이미 놓여 있음 · 새 메시지 = 주인공에서 첫 쓰임새(스킬)로 이어짐 | 0 (부품 안 글자만 · 비트 시트 24자 라벨은 skillry 글자 배치 "앱 화면 · 부품 동안 영상 글자 0"으로 뺌) | 첫 프레임 brand-icon `cut-scale` 상태로 화면 가운데 (컷 너머 주인공 클로즈) → `cam-release` → 카메라 멈춘 뒤 `icon-spin` → `hold-s` (아이콘 하나) → `cam-pan` 오른쪽 (skill-card-1은 첫 프레임부터 놓여 있어 따로 `enter` 없음) → 멈춘 뒤 `hold-m` (카드 하나) | `cam-pan` 아래 (지그재그 왼쪽 아래, 장면3 첫 움직임) · 대신: `cut-in-motion` |
| 3 | 7 쓰임새 목록 (5개 지그재그) | 35.3 | 5.00–11.60 | 가까이 (항목마다 부품 한 개) | `cam-pan` 아래 · 항목마다 멈춤 (5번, 방향은 왼쪽 아래 · 오른쪽 아래 번갈아) | 배경 `video-bg-soft` → ⑤로 가는 이동 동안 `video-bg` (`pan-bg-shift`, video.md 5장 예외) · 폰 없음 · 한 바탕 위에 지그재그 세로 줄로 놓임, 항목 사이는 카메라가 멈춘 프레임에 부품 하나만 보이는 거리 · 차례: ① `src/parts/button-submit.html` (`data-state="submit"`) ② `src/parts/mission-card.html` (진행 `#mission-card-progress-fill` `--progress` 부품 기본값 → 1) ③ `src/parts/badge-approved.html` ④ `src/parts/stat-card.html` (금액 `#stat-card-amount` `data-final`까지) ⑤ `src/parts/asset-card.html` (`data-state="selling"`) · 모두 × 2.8 · 멈춘 프레임에 화면 가운데 · 연결선 · 노드 아이콘 없음 | 0 (부품 안 글자만 · 비트 시트 카드 라벨 19–33자 × 5는 skillry 글자 배치로 뺌) | ① `cam-pan` → `button-press` (앞 `hold-m` → 누름 → 뗌) → 조립: 떼는 끝 프레임에 `transition` 대신 바로 다음 `cam-pan` ② `cam-pan` → 멈춘 뒤 진행 바 · 글자 `emphasis` (`mission-in` 뒷부분) → `hold-m` ③ `cam-pan` → `badge-pulse` → `hold-s` ④ `cam-pan` → `count-up` (카드는 이미 놓여 있어 `part-in` 없음) → `hold-s` ⑤ `cam-pan` + `pan-bg-shift` (video.md 5장 예외: 이 이동 동안 바탕 `video-bg-soft` → `video-bg` · `dur-l` · `ease-linear`, stat-card와 asset-card가 한 프레임에 같이 머물지 않음) → 멈춘 뒤 `hold-m` (카드 하나) | `transition` (컷, 다음 첫 프레임은 주인공 brand-icon `cut-scale` 상태) · 대신: `cut-in-motion` |
| 4 | 8+9 다시 주인공 → 넓어짐 | 18.1 (6.6+11.5) | 11.60–14.85 | 가까이 → 멀리 | `cam-release` (`cut-scale` → × 1, 대상 brand-icon, 비트8) → `cam-dolly-out` (× 1 → `dolly-scale`, 화면 가운데 기준, `hold-l` 동안, 비트9) · 대신: `한 장면에 카메라는 한 묶음` · 대신: `hold 동안 카메라 정지` | 배경 `video-bg-soft` · 폰 없음 · 가운데 `src/parts/brand-icon.html` (× 2.8, 화면 가운데) · 둘레 그물: `src/parts/skill-card-1.html` · `button-submit.html` (`submit`) · `mission-card.html` (진행 1) · `badge-approved.html` · `stat-card.html` (금액 최종값) 5개 (모두 × 2.8) · × 1에서는 화면 가장자리에 반쯤 잘리고 `dolly-scale`에서 전부 화면 안에 드는 자리 · `cam-dolly-out`으로 × 1 아래인 동안 부품 글자는 video.md 1장 예외 (× 1에서는 31px 이상) · asset-card는 뺌 (video.md 5장: `video-bg-soft` 위에서 사라짐) · 서비스 로고 없음 (`orbit-in` 쓰지 않음) | 0 | 첫 프레임 brand-icon만 `cut-scale` 상태로 화면 가운데 (컷 너머 주인공 클로즈) → `cam-release` → 멈춘 뒤 조립: 둘레 부품 5개 `part-in`, 부품 사이 `stagger` (비트8 "하나씩 붙음") → `hold-l` (그물 전체) 동안 `cam-dolly-out` → 조립: 그물 부품 5개만 `scene-out` (brand-icon은 남음) | `match-cut` (brand-icon 화면 가운데 그대로) · 조립: 그물 부품 `scene-out` 절반에서 `transition`, 장면5는 × 1이라 brand-icon 크기만 `dolly-scale` 상태 → × 2.8 원래 크기 (1password 시각 규칙 4 · 비트9→10 `orbit-collapse` 대신) |
| 5 | 10+11 하나로 모임 → 엔드 | 15.8 (3.6+12.2) | 14.85–18.52 | 화면 전체 (가운데 한 점 → 로고 묶음) | `cam-hold` | 배경 `video-bg-end` (`video-glow` · `video-grain`) · 폰 없음 · `src/parts/brand-icon.html` (× 2.8, 화면 가운데) → `src/parts/logo.html` (`data-state="logotype-white"`, `logo-hero`) · logo ↔ 슬로건 `video-gap-end` · 묶음 전체 화면 가운데 · 엔드 카드에 brand-icon 없음 (motion.md 3장 `logo-reveal`) · 안내 카드(QR) 없음 | 슬로건 "오늘도 하나씩, 내 실력으로" (01-home 화면 제목 문구 · 12자, 공백 빼고) `video-title` · `video-text-on-dark` · logo 아래 가운데 한 줄 | 조립: `icon-spin` → `hold-s` → brand-icon `exit` → `end-reveal` (logo 글자마다 `enter` · `stagger` → `dur-l` 뒤 슬로건) → `hold-end` (docs 값 그대로) → 마지막 hold 정지 (motion.md 4장 예외) | 끝 |

## 장면 길이 (움직임 + hold 합 = 시작–끝, 빈 시간 0)

BRIEF 길이 = 장면 움직임 + hold 합계 = 18.52초 (BRIEF "약 17초"보다 약 1.4초 김 — 장면2에 비트4 `icon-spin` · 장면4에 비트8 `cam-release`를 비트 시트대로 넣어서. 빈 hold는 없음). 비율 = 장면 길이 ÷ 18.52.

| # | 움직임 + hold (motion.md 1장 · 4장 이름 값) | 장면 길이 | 합계 기준 비율 | 비트 시트 비율 | 차이 (±5%p 안?) |
|---|---|---|---|---|---|
| 1 | `cam-pull` 0.4 + `flip-wave` 1.2 (6개 `stagger` + 마지막 `dur-m`) + `hold-s` 0.4 + 나감 `dur-s` 0.1 | 2.10 | 11.3 | 10.6 | +0.7 안 |
| 2 | `cam-release` 1.0 + `icon-spin` 0.4 + `hold-s` 0.4 + `cam-pan` 0.4 + `hold-m` 0.7 | 2.90 | 15.7 | 20.2 | −4.5 안 |
| 3 | 아래 표 | 6.60 | 35.6 | 35.3 | +0.3 안 |
| 4 | `cam-release` 1.0 + `part-in` · `stagger` 1.0 (5개) + `hold-l` 1.2 (`cam-dolly-out` 같이) + `scene-out` 절반 0.05 | 3.25 | 17.5 | 18.1 | −0.6 안 |
| 5 | `icon-spin` 0.4 + `hold-s` 0.4 + `exit` 0.1 + logo 글자 `enter` · `stagger` 약 0.47 (글자 5개 기준) + `dur-l` 0.4 + 슬로건 0.4 + `hold-end` 1.5 | 약 3.67 | 19.8 | 15.8 | +4.0 안 |
| 합 | | 18.52 | 100 | 100 | 5/5 안 |

장면3 (비트7) 항목별:

| 항목 | `cam-pan` | 동작 | hold | 합 |
|---|---|---|---|---|
| ① button-submit | 0.4 | `button-press` 누름 0.1 + 뗌 0.2 | 앞 `hold-m` 0.7 | 1.4 |
| ② mission-card | 0.4 | `emphasis` 0.2 | `hold-m` 0.7 | 1.3 |
| ③ badge-approved | 0.4 | `badge-pulse` 0.2 | `hold-s` 0.4 | 1.0 |
| ④ stat-card | 0.4 | `count-up` 1.0 | `hold-s` 0.4 | 1.8 |
| ⑤ asset-card | 0.4 (`pan-bg-shift` 같이) | 없음 | `hold-m` 0.7 | 1.1 |
| 합 | 2.0 | 1.7 | 2.9 | 6.6 |

0장 확인:
- 앞뒤에 없던 화면 · 메시지: 장면2는 skill-card-1(첫 쓰임새)을 처음 보여준다. brand-icon `icon-spin`은 비트4 · 비트10 둘 다 비트 시트에 있는 동작이라 장면2 · 장면5에 한 번씩 둔다.
- 부품 장면에는 그 부품만: 장면2 · 3은 멈춘 프레임마다 부품 하나만 화면에 있다. 같은 종류 부품이 이웃하지 않음 (skill · button · mission · badge · stat · asset).
- 다가간 장면은 동작으로 넘기기: 다가가는(`cam-in` 쪽) 장면 없음. 장면3 ①은 뗌 끝에서 hold 없이 바로 `cam-pan`. ⑤만 동작 없이 hold로 끝난다 (asset-card 상태를 바꾸면 다른 자산 문구가 되어 `emphasis`를 쓰지 않음).
- 빈 hold로 채우지 않기: 시작–끝 = 움직임 + hold 합, 빈 시간 0. 장면5 `hold-end`는 docs 값 그대로.

## 비트 시트 반영률 (1password, 합친 뒤 5비트)

비트 수 1/1 + 비율 5/5 (위 표, 모두 ±5%p 안) + 구도 5/5 + 카메라 5/5 + 전환 4/5 (비트9→10 `orbit-collapse` 빨려 들어감 → 그물 `scene-out` + 같은 자리 brand-icon `match-cut`으로 바꿈, 크기는 이어지지 않음) = 20/21 = 95%.
langease (카메라 · 전환): 깊이 컷 (장면1→2) · `cam-release` 클로즈 시작 (장면2 · 4) · 주인공 한 점 이어받기 (장면4→5). skillry (구도 · 글자 배치): 주인공 덩어리 하나를 가로 가운데 축 · 부품 동안 영상 글자 0 · 글자는 엔드 가운데만.

- 새 후보 0개 (`pan-bg-shift`는 video.md 5장 예외로 승인됨).
- 조립은 `work/launch-c/decisions.md` "장면표 detail — 안 a" · "장면표 detail — 안 a 다시" 줄.
