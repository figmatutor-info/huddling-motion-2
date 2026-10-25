# used — snapboard · launch-d (안 a · 10장면 · 24.00초)

결과: `work/launch-d/snapboard.html` (1920×1080 컷 10장, 장면 순서대로) · `work/launch-d/snap/01.png`–`10.png` · `work/launch-d/snapboard.png` (4열 × 3줄, 칸마다 `번호 · 시작–끝 · 장면 이름`).
캡처: playwright-core 1.63 + Chrome for Testing (chromium-1248, headless), `--allow-file-access-from-files`, `document.fonts.ready` (본문 + iframe 전부) · 이미지 decode 뒤 `section.cut`마다 요소 캡처. 그리드도 같은 Chrome으로 캡처.
대표 컷 = 그 장면 첫 hold의 첫 프레임. 예외 장면3: 구도 칸의 주인공(03-mission 가운데, 폰 3대 + 양 끝 반쯤)이 보이는 둘째 `hold-l` 첫 프레임 (첫 `hold-l`은 01-home 가운데).

## 장면별

| # | 배경 (video.md 2장) | 글자 (video.md 3장) | 크기 · 배치 (video.md 3 · 4 · 5장) | 머묾 상태 · 움직임 · 카메라 (motion.md) | 불러온 src |
|---|---|---|---|---|---|
| 1 | `video-bg-soft` | 부품 안 글자만 | 부품 6개 × 2.8, 네 귀퉁이 + 위 · 아래 가운데에 반쯤 잘림 (자리는 아래 "이름 없이 넣은 값") · 가운데 비움 | 부품 첫 프레임부터 놓임 → 첫 `hold-s` 첫 프레임 · `cam-hold` × 1. 뒤: `scene-out` → `flip-turn` → `cam-pull` → `logo-reveal` 뒷부분 → `hold-m` (이 컷에 안 보임) | `src/parts/skill-card-1.html` · `skill-card-2.html` · `skill-card-3.html` · `stat-card.html` · `button-submit.html?state=submit` · `badge-approved.html` |
| 2 | `video-bg-brand` | "스킬 라이브러리" `video-display` · `video-text-on-brand` · 화면 정가운데 | 한 줄 화면 가운데 | 첫 줄 `enter` 끝 → `hold-s` 첫 프레임 · `cam-hold` | 폰트 `src/assets/fonts/Pretendard-Bold.otf` |
| 3 | `video-bg-soft` | 0 (화면 이미지 속만, 4장 예외) | 폰 5대 `phone-size` · 사이 `video-gap` · 03-mission 화면 가운데 · 세로 가운데 (top 76) | `cam-pull` → `hold-l` → `cam-pan` 끝 → 둘째 `hold-l` 첫 프레임 (× 1) | `src/screens/01-home.png` · `02-skills.png` · `03-mission.png` · `04-approved.png` · `05-assets.png` |
| 4 | `video-bg-soft` | 0 | 장면3과 같은 줄 · 평면 가운데 = 03-mission | `plane-tilt` 끝 (`plane-angle` · 회전 중심 평면 가운데 · 카메라 `dolly-scale` 화면 가운데 기준) → `hold-l` 첫 프레임 (`cam-drift` 0) | 장면3과 같음 |
| 5 | `video-bg-soft` | "일에 바로 적용하는 AI" `video-display` · `video-text` · 왼쪽 정렬 | 제목 ↔ 폰 `video-gap` · 묶음 화면 가운데 (제목 x 375 · 폰 x 1101, top 76) · `phone-size` | `phone-rise-tilt` + `headline-in` (`stagger`) 끝 → 첫 `hold-l` 첫 프레임 · `cam-hold` | `src/screens/02-skills.png` · 폰트 Bold |
| 6 | `video-bg` | "파일과 적용 사례를 함께 제출해주세요." `video-heading` · `video-text` · 버튼 아래 가운데 | button-submit × 2.8 = 980×123.2 · `video-gap` · 글 한 줄 → 묶음 화면 가운데 | 글자 `enter` · `stagger` 끝 → `button-press` 앞 `hold-m` 첫 프레임 | `src/parts/button-submit.html?state=submit` · 폰트 SemiBold |
| 7 | `video-bg-dark` | "미션을 완성했어요!" `video-display` · `video-text-on-dark` · 정가운데 | 한 줄 화면 가운데 | `dark-cut` `enter` 끝 → `hold-s` 첫 프레임 (`cam-drift` 0) | 폰트 Bold |
| 8 | `video-bg-soft` | 부품 안 글자만 | `card-rail` + `rail-tilt` (`rail-angle`, 회전 중심 화면 가운데 줄 선) · 튕김 1번 뒤: stat-card 가운데 (960, 540) · mission-card 가운데 x −76 (거리 980 + `video-gap`) · badge-approved는 mission-card 아래 `video-gap-s`, 왼쪽 맞춤 → 화면 밖 | `mission-done` → 튕김 (`dur-2xl` · `ease-out`) → `count-up` 끝 (`data-final` "29,700") → `hold-m` 첫 프레임 · `cam-hold` | `src/parts/mission-card.html` (`--progress` 1) · `stat-card.html` · `badge-approved.html` |
| 9 | `video-bg` (asset-card 규칙, 5장) | 부품 안 글자만 (최소 eyebrow 31px) | asset-card × 2.8 = 980×207.2 화면 가운데 | asset-card 등장 (`cut-scale` → 1) 끝 → `hold-l` 첫 프레임 (× 1, `cam-push` 시작 프레임) | `src/parts/asset-card.html?state=selling` |
| 10 | `video-bg-end` (`video-bg-dark` + `video-glow` + `video-grain`) | "오늘도 하나씩, 내 실력으로" `video-title` · `video-text-on-dark` · 가운데 한 줄 | logo `logo-hero` 894×114 · `video-gap-end` · 슬로건 → 묶음 화면 가운데 · logo 색 `*-white` | `end-reveal` 끝 → `hold-end` 첫 프레임 · `cam-hold` | `src/parts/logo.html?state=logotype-white` · 폰트 SemiBold |

## 쓴 이름

- video.md: 1장 `video-scale` · `video-text-min` / 2장 `video-bg` · `video-bg-soft` · `video-bg-brand` · `video-bg-dark` · `video-bg-end` · `video-glow` · `video-grain` / 3장 `video-display` · `video-title` · `video-heading` · `video-text` · `video-text-on-brand` · `video-text-on-dark` · `video-gap` · `video-gap-s` · `video-gap-end` · 가운데 정렬 예외 · `keep-all` / 4장 `phone-size` · `phone-screen` · `phone-bezel` · `phone-radius` · `phone-color` · `phone-screen-bg` / 5장 × 2.8 · `logo-hero` · 바탕 규칙 (stat · skill → soft, asset → bg) · logo 색 규칙
- motion.md: 1장 `plane-angle` · `rail-angle` · `dolly-scale` · `cut-scale` (컷 상태로) / 2장 `enter` · `stagger` / 3장 `card-rail` · `rail-tilt` · `plane-tilt` · `phone-rise-tilt` · `headline-in` · `button-press` · `dark-cut` · `mission-done` · `count-up` · `end-reveal` · `logo-reveal` · `scene-out` / 4장 `hold-s` · `hold-m` · `hold-l` · `hold-end` / 5장 `cam-hold` · `cam-pull` · `cam-pan` · `cam-drift` · `cam-push`
- design.md: 1장 (부품 안 색, 부품 원본 그대로) · 3장 A 로컬 폰트 로드 (Pretendard 600 · 700)

## 이름 없이 넣은 값 (숨기지 않음)

| 컷 | 값 | 왜 |
|---|---|---|
| 1 | 부품 가운데 점: skill-card-1 (−76, 0) · badge-approved (960, 0) · skill-card-2 (1996, 0) · stat-card (−76, 1080) · button-submit (960, 1080) · skill-card-3 (1996, 1080) | 장면표 "네 귀퉁이와 위 · 아래 가장자리 가운데에 반쯤 잘린 채"를 만족하는 구도 선택. 귀퉁이 x는 가운데 부품(button 980폭)과 `video-gap` 56 띄움 = 960 ± (490 + 56 + 490). 어느 부품을 어느 자리에 둘지는 docs에 없음 |
| 3 · 4 | 폰 줄 top 76 · left −262 | (1080 − 928) / 2 · 960 − 2444 / 2, 화면 가운데 계산 |
| 4 | `plane-angle` 적용 순서 `perspective(2400px) rotateX(55deg) rotateZ(-20deg)` | docs 표기 순서대로 CSS에 씀 |
| 8 | 진행 글자 "100% · 4/4 단계 완료" | `mission-done` `emphasis` 최종값. 부품에 최종 글자가 없어 `src/screens/04-approved.png` 속 같은 카드 문구 그대로 (launch-c와 같은 처리, iframe 안 textContent만) |
| 8 | `rail-angle` 회전 중심 = 화면 가운데 (960, 540) | 줄이 튕기며 움직여도 소실점이 고정되게 평면을 화면에 고정, 카드만 줄 안에서 옮김 |
| 10 | `video-glow` 표기 `rgba(55, 89, 222, 0.45 → 0)` | `#3759de`에 2장 불투명도를 거는 표기 |

## 판단이 필요한 곳

1. 장면3 대표 컷을 둘째 hold로 잡음 (위).
2. 장면1 위 가운데 badge-approved는 반쯤 잘려 "승인 완료" 글자 아래쪽만 보임 (가운데 점이 화면 위 끝). 장면표 그대로지만 영상에서 확인 필요.
3. 장면8 badge-approved는 이 컷(튕김 뒤)에서 화면 밖. mission-done 동안에만 보임.
4. 새 후보 0 · src 고친 것 0 · docs 고친 것 0 · 화면에 없는 UI 0.
