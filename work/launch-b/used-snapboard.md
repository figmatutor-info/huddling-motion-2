# used — snapboard · launch-b (안 a · 12장면 · 20.0초)

결과: `work/launch-b/snapboard.html` (컷 1920×1080 · 장면 순서대로 12컷) · `work/launch-b/snap/01.png` – `12.png` (장면당 한 컷).
캡처: playwright-core 1.48 + Chrome for Testing (chromium-1248, headless), `--allow-file-access-from-files`, `document.fonts.ready` (본문 + iframe 전부) · 이미지 decode 뒤 `section.cut`마다 요소 캡처.
기준 파일 (2026-10-25 피그마 반영본을 지금 읽음): video.md 4장 (03-mission 제출하기 자리 @1x x 20 · y 753 · 350×44 · 그림자 없음) · 5장 표 (stat-card 980×283 · button-submit 980×123 · mission-card 980×708 · brand-icon 274×274 · logotype 417×53, `logo-hero` 894×114) · 126줄 바탕 규칙 (stat-card → `video-bg-soft`). 부품 실제 크기는 렌더해서 확인: stat-card 350×101 · mission-card 350×253 · brand-icon 98×98 · button-submit 350×44 (apply-case 318×44) · logo 149×19.

## 장면별

| # · 컷 | 배경 (video.md 2장) | 글자 스타일 · 색 (video.md 3장) | 크기 · 배치 (video.md 3 · 4 · 5장) | 머묾 상태 · 움직임 · 카메라 (motion.md) | 불러온 src |
|---|---|---|---|---|---|
| 1 · 01 | `video-bg` | 구절2 "내 실력으로" `video-display` · `video-text` · 화면 가운데 한 줄 (가운데 정렬 예외: 훅) | 글자 y 492.5–587.5 | 구절2 조립 (`enter` + 마스크 대신 `scale-from` → 1, 단어 사이 `stagger`) 끝 → `hold-s` · `cam-hold` (구절1 → 2는 `transition` 컷) | 폰트 `src/assets/fonts/Pretendard-Bold.otf` |
| 2 · 02 | `video-bg` | "바로 써먹는 스킬" `video-display` · `video-text-accent` · 가운데 한 줄 | brand-icon × 2.8 (`video-scale`) = 274.4×274.4 · 아이콘 ↔ 글자 `video-gap` 56 · 묶음 화면 가운데 (아이콘 y 327.3–601.7 · 글자 y 657.7–752.7) | brand-icon `enter` + 마스크 대신 `scale-from` → 1, 글자 `enter` (`stagger`) 끝 → `hold-s` · `cam-hold` | `src/parts/brand-icon.html` · 폰트 Bold |
| 3 · 03 | `video-bg-soft` | 없음 (화면 이미지 속 글자만) | 폰 프레임 `phone-size` 444×928 · `phone-screen` 416×900 · `phone-bezel` 14 · `phone-radius` 64 / 50 · `phone-color` · `phone-screen-bg` · 그림자 없음 (4장) · 폰 화면 가운데 (x 738–1182 · y 76–1004) | `phone-rise-tilt` 끝 (위치 0 · 각도 0) → `hold-l` · `cam-hold` | `src/screens/01-home.png` |
| 4 · 04 | `video-bg-soft` | 부품 안 "적용 사례 정리하기 →"만 (`Text/label` 14 × 2.8 = 39px ≥ `video-text-min`) | button-submit apply-case × 2.8 = 890.4×123.2 (부품 폭 318) · 화면 가운데 (x 514.8–1405.2 · y 478.4–601.6) | `zoom-through` 이어짐 (첫 프레임부터 놓임) → `hold-m` · `cam-hold` | `src/parts/button-submit.html?state=apply-case` |
| 5 · 05 | `video-bg-soft` | 부품 안 글자만 (최소 `Text/caption` 12 × 2.8 = 33.6px) | mission-card × 2.8 = 980×708.4 · 점 자리 = 화면 가운데 (x 470–1450 · y 185.8–894.2) | 머묾 없음 → 대표 = `shape-morph` 끝 (mission-card `scale-from` → 1 끝, 바로 `screen-dissolve`로 감) · `cam-hold` | `src/parts/mission-card.html` (상태 없음 · 진행 바 원본 0.5) |
| 6 · 06 | `video-bg-soft` | 없음 | 폰 프레임 (4장 값 전부, 3장과 같음) · × 1 · 첫 hold(`screen-dissolve` 직후 `hold-m`) 첫 프레임 = 미션 카드 가운데가 화면 가운데 (폰 y 310.06–1238.06, 폰 아래가 화면 밖 · 2026-10-25 다시 뽑음, 전 컷은 `cam-pan` 끝 top −300.42) · button-submit submit을 화면 이미지 속 자리(4장 @1x x 20 · y 753 · 350×44)에 화면 이미지 배율로 겹침 + 덮개판 (사방 1px @1x · 모서리 `radius-button` 8 × 배율 · 색 `phone-screen-bg`) | `screen-dissolve`로 들어옴 → `hold-m` 첫 프레임 (대표 컷) | `src/screens/03-mission.png` · `src/parts/button-submit.html?state=submit` |
| 7 · 07 | `video-bg-soft` | 없음 | 폰 프레임 (4장) · 화면 속 미션 카드(100%) · "승인 완료" · "미션을 완성했어요!" 묶음을 화면 가운데 (폰 y 265.3–1193.3, 아래 화면 밖) · 부품 겹침 없음 | `screen-dissolve` 끝 → `hold-l` · `cam-hold` | `src/screens/04-approved.png` |
| 8 · 08 | `video-bg-soft` | 부품 안 "내 자산에서 보기"만 (39px) | button-submit view-assets × 2.8 = 980×123.2 · 화면 가운데 (x 470–1450 · y 478.4–601.6) | `part-in` 끝 → `button-press` 앞 `hold-m` · `cam-hold` | `src/parts/button-submit.html?state=view-assets` |
| 9 · 09 | `video-bg-soft` (5장 126줄: stat-card는 `video-bg-soft` 위) | 부품 안 "이번 달 수익 ₩29,700" · counts 줄 (최소 `Text/label` 39px) | stat-card × 2.8 = 980×282.8 · 화면 가운데 (x 470–1450 · y 398.6–681.4) | `shape-morph` 끝 (`scale-from` → 1) → `count-up` 끝 (`data-final` "29,700" = 원본 글자) → `hold-s` · `cam-hold` | `src/parts/stat-card.html` |
| 10 · 10 | `video-bg-soft` | 부품 안 글자만 | 같은 stat-card × 2.8에 카메라 × `cut-scale` 1.7 → 화면에서 1666×480.8 (x 118.3–1784.3 · y 373.4–854.2) · 대상 금액이 화면 가운데 | 머묾 없음 → 대표 = `cam-push` 끝 (× 1 → `cut-scale`, 대상 stat-card 금액) · 다음 `icon-expand` 직전 | `src/parts/stat-card.html` |
| 11 · 11 | `video-bg` | 윗줄 "배움이 쌓여," `video-display` · `video-text` / 아랫줄 첫 단어 "회의록 자동 정리 템플릿" `video-display` · `video-text-accent` · 두 줄 모두 가운데 (3장 `slot-roll` 예외) | 줄 사이 `video-gap-line` (0, 행간만) · 묶음 화면 가운데 (윗줄 y 445–540 · 아랫줄 y 540–635) | `headline-in` 끝 → `hold-l` (글자 15자 넘음 → 한 단계 위, 4장) · `cam-hold` · 이 뒤 `slot-roll` | 폰트 Bold |
| 12 · 12 | `video-bg-end` = `video-bg-dark` + `video-glow` + `video-grain` | 없음 (logo만) | logo logotype-white `logo-hero` × 6 = 894×114 · 화면 가운데 (x 513–1407 · y 483–597) · logo 색 규칙 (5장: `video-bg-end` 위 `*-white`) | `logo-reveal` (엔드 카드: 글자마다 `enter`, `stagger`) 끝 → `hold-end` 마지막 정지 · `cam-hold` | `src/parts/logo.html?state=logotype-white` |

## 쓴 이름 (중복 없이 43개)

- video.md (20): 1장 `video-scale` · `video-text-min` / 2장 `video-bg` · `video-bg-soft` · `video-bg-dark` · `video-bg-end` · `video-glow` · `video-grain` / 3장 `video-display` · `video-text` · `video-text-accent` · `video-gap` · `video-gap-line` / 4장 `phone-screen` · `phone-bezel` · `phone-size` · `phone-radius` · `phone-color` · `phone-screen-bg` / 5장 `logo-hero`
- motion.md (21): 1장 `scale-from` · `cut-scale` / 2장 `enter` · `stagger` · `transition` / 3장 `headline-in` · `logo-reveal` · `part-in` · `count-up` · `button-press` · `shape-morph` · `screen-dissolve` · `zoom-through` · `phone-rise-tilt` · `slot-roll` / 4장 `hold-s` · `hold-m` · `hold-l` · `hold-end` / 5장 `cam-hold` · `cam-pan` · `cam-push`
  - 장면 흐름에만 나오고 컷에는 상태가 안 보이는 것 (참고, 위 개수에 안 넣음): `scene-out` (2 · 11 끝) · `icon-expand` (10 끝) · `exit`
- design.md (2): 3장 A 로컬 폰트 로드 (Pretendard 700) · 4장 `radius-button` (덮개판 모서리 = 부품 모서리 8)

## 이름 없이 넣은 값 (숨기지 않음)

| 장면 | 값 | 왜 |
|---|---|---|
| 3 · 6 · 7 | 폰 `left: 738px` | (1920 − `phone-size` 444) / 2, 가로 가운데 계산 |
| 3 | 폰 `top: 76px` | (1080 − 928) / 2, 세로 가운데 계산 |
| 6 | 03-mission 미션 카드 자리 @2x y 208–602 (가운데 405) | 화면 이미지에서 잰 값 (카드 테두리 픽셀). `cam-pan` 시작 프레이밍 계산용 → 시작 폰 top 310.06 (컷에는 안 나옴, 영상용) |
| 6 | 폰 `top: −300.42px` | `cam-pan` 끝 = "제출하기" 가운데(4장 y 753 + 22 = 775 @1x)를 화면 가운데: 540 − 14 − 775 × 900/844. "다음 대상까지" 이동을 "다음 대상을 앞 대상이 있던 자리(화면 가운데)로"로 읽음 |
| 6 | 겹침 부품 배율 `1.066667` (= 416/390) · 위치 left 35.3333 · top 816.9479 · 덮개판 left 34.2667 · top 815.8815 · 375.4667×49.0667 · 모서리 8.5333 | video.md 4장 "phone-screen 배율 1.066"을 416/390로 정확히 계산 · 4장 자리 (x 20 · y 753 · 350×44, 덮개판 사방 1px)를 폰 좌표로 옮긴 계산 값. 세로는 화면 이미지가 900/844로 놓이므로 y에 900/844 |
| 7 | 04-approved 묶음 자리 @2x y 208–770 (카드 위 테두리 ~ "미션을 완성했어요!" 글자 아래, 가운데 489) | 화면 이미지에서 잰 값. 폰 `top: 265.28px` = 540 − 14 − 489 × 900/1688 |
| 10 | 금액 `#stat-card-amount` 가운데 (부품 좌표) 176.836 · 35 | 렌더해서 잰 값 (span 상자 x 143.17–210.5 · y 23–47). ₩는 span 밖이라 대상에서 뺌 |
| 10 | 카메라 `translate(−680.7397px, −304.22px) scale(1.7)` | 위 점(화면 965.141 · 496.6)을 `cut-scale` 뒤 화면 가운데에 두는 계산. "대상 쪽으로"를 "끝에 대상이 화면 가운데"로 읽음 |
| 12 | `video-glow` 색 표기 `rgba(55, 89, 222, 0.45 → 0)` | `#3759de`에 2장 불투명도를 거는 표기 |

## 장면표대로 못 만든 곳 · 판단이 필요한 곳

1. 장면3 → 4 크기 이어짐: `zoom-through`는 "다음 장면 첫 프레임은 그 부품 자리에서 이어짐 (`match-cut`처럼)"인데, 01-home 속 "적용 사례 정리하기 →" 버튼은 `cam-in` × 2.4 끝에서 318 × (416/390) × 2.4 ≈ 814px 폭, 장면4 장면표 값 × 2.8은 890.4px. 스냅보드는 장면표대로 × 2.8로 만듦. 영상에서는 컷에서 약 9% 크기가 튐 → director · 사람 판단 필요 (× 2.8을 지키면 크기가 튀고, 맞추면 docs에 없는 배율).
2. 장면6 머묾 컷 구도: `cam-pan` 끝(제출하기를 화면 가운데)에서는 폰 아래 끝이 y 627.6이라 아래 약 450px가 빈 `video-bg-soft`. 장면표 구도 "아래 잘림"은 시작 프레이밍(미션 카드 가운데)에만 맞음. 장면표 · docs 범위 안의 결과지만 승인 때 봐 주기.
3. 머묾(hold)이 없는 장면 5 · 10은 대표 프레임으로 각각 `shape-morph` 끝 · `cam-push` 끝을 골랐음.
4. hold가 둘 이상인 장면은 한 컷만: 1 = 구절2 `hold-s` (구절1 "오늘도 하나씩," 컷 없음) · 6 = `button-press` 앞 `hold-m` (`cam-pan` 앞 `hold-m` 컷 없음) · 11 = `headline-in` 뒤 `hold-l` (마지막 단어 "나의 자산으로" 뒤 `hold-m` 컷 없음).
5. 새 후보 0 · src 고친 것 0 · docs 고친 것 0 · 화면에 없는 UI 0. `work/launch-30s/` 손대지 않음.
