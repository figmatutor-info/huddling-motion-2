# video.md

런칭 영상의 룩. 16:9 · 1920×1080 · 30fps. 배경: 밝은 · 헤드라인: 단정하게 · 폰 프레임: 씀
규칙: 색 · 폰트는 docs/design.md 값만 쓴다. 영상 글자 크기 = Figma 값 × 2.8 (`video-scale`), 소수점은 반올림.
움직임은 docs/motion.md. 장면 순서 · 흐름 · 구성은 이 문서에서 정하지 않는다 (레퍼런스가 정함).

---

## 1. 텍스트 최소 크기

| 토큰 | 값 | 출처 |
|---|---|---|
| `video-scale` | 2.8 | 요청 (Figma 값 × 2.8) |
| `video-text-min` | 31px | design.md `Text/eyebrow` 11 × 2.8 = 30.8 → 31 (가장 작은 스타일) |

- 영상 위에 올리는 모든 글자(parts 안 글자 포함)는 31px 이상.
- 예외: 폰 프레임 **안의 화면 이미지** 글자. 화면 배율이 작아 31px보다 작다(4장). 읽혀야 하는 정보는 화면 이미지가 아니라 parts(5장)나 영상 글자(3장)로 보여준다.

---

## 2. 배경

| 토큰 | hex | design.md | 쓰는 곳 |
|---|---|---|---|
| `video-bg` | `#ffffff` | `color-bg` | 기본 배경 |
| `video-bg-soft` | `#f7f7f8` | `color-surface` | 흰 카드(parts)를 올릴 때 구분이 필요하면 |
| `video-bg-brand` | `#3759de` | `color-primary` | 브랜드 한 장 (글자는 `video-text-on-brand`) |
| `video-bg-character` | `#e3f2fd` | `color-character-bg` | 펭귄 일러스트가 주인공일 때 |
| `video-bg-dark` | `#18191b` | `color-text` | 검정 배경 · `dark-cut` 전환 면 (motion.md 3장) |

- 단색만 쓴다. 그라디언트 · 패턴 · 사진 배경 없음 (design.md에 없는 값이 생기므로). 예외: `video-bg-end` 하나.

**`video-bg-end`** (엔드 카드 배경 — 세 겹)

| 겹 | 값 | design.md |
|---|---|---|
| 바탕 | `video-bg-dark` | `color-text` |
| `video-glow` | `#3759de` 원형 그라데이션 · 화면 가운데 · 지름 1200px · 불투명도 가운데 0.45 → 가장자리 0, 반지름을 따라 일직선으로 줄어듦 · 블러 160px | `color-primary` |
| `video-grain` | `#ffffff` 노이즈 · 알갱이 1px · 알갱이마다 알파 0–255 고르게 · seed 1 · 겹 전체 불투명도 0.06 · 고정 (프레임마다 바뀌지 않음) · 난수 생성기 mulberry32 (요청 2026-10-24) | `color-bg` |

---

## 3. 글자

폰트: `Pretendard` 400 · 600 · 700만. 로컬 파일 `src/assets/fonts/Pretendard-*.otf` (design.md 3장 A). 자간 0% · 행간 px.
첫 프레임 전에 `document.fonts.ready`를 기다린다 (design.md 3장).

| 토큰 | Figma 스타일 | 굵기 | 크기(px) | 행간(px) |
|---|---|---|---|---|
| `video-display` | `Text/display` 28 / 34 | 700 | 78 | 95 |
| `video-title` | `Text/title` 24 / 32 | 600 | 67 | 90 |
| `video-compact-title` | `Text/compact-title` 22 / 28 | 700 | 62 | 78 |
| `video-section` | `Text/section` 20 / 28 | 700 | 56 | 78 |
| `video-heading` | `Text/heading` 18 / 28 | 600 | 50 | 78 |
| `video-body` | `Text/body` 15 / 24 | 400 | 42 | 67 |
| `video-list-title` | `Text/list-title` 15 / 22 | 600 | 42 | 62 |
| `video-label` | `Text/label` 14 / 20 | 600 | 39 | 56 |
| `video-caption` | `Text/caption` 12 / 16 | 400 | 34 | 45 |
| `video-eyebrow` | `Text/eyebrow` 11 / 16 | 600 | 31 | 45 |

- 헤드라인은 `video-display`(78px)가 가장 크다. 더 키우지 않는다 (헤드라인: 단정하게).

| 토큰 | hex | design.md | 쓰는 곳 |
|---|---|---|---|
| `video-text` | `#18191b` | `color-text` | 기본 글자 |
| `video-text-muted` | `#75777c` | `color-text-muted` | 보조 문장 |
| `video-text-accent` | `#3759de` | `color-primary` | 강조 단어 · eyebrow |
| `video-text-on-brand` | `#ffffff` | `color-on-primary` | `video-bg-brand` 위 글자 |
| `video-text-on-dark` | `#ffffff` | `color-bg` | `video-bg-dark` · `video-bg-end` 위 글자 |

- 한국어 줄바꿈은 단어 단위 (`word-break: keep-all`).
- 덩어리(글자 · 부품) 안 글자는 왼쪽 정렬. 예외: 화면 가운데 한 줄만 있는 장면(훅 · `dark-cut` · 엔드 카드)과 `slot-roll` 두 줄(윗줄 · 아랫줄 모두)은 가운데. (요청 2026-10-24)

간격 (영상 화면 위 덩어리 사이 — design.md 4장 Scale의 `space-*` · `radius-*`는 부품 안에서만 쓰고, 영상 화면 간격에는 아래 토큰만 쓴다)

| 토큰 | 값 | 쓰는 곳 |
|---|---|---|
| `video-gap-line` | 0 (행간만) | 한 덩어리 안 줄 사이 (제목 ↔ 부제, 라벨 ↔ 숫자) |
| `video-gap-s` | 32px | 배지 ↔ 제목 |
| `video-gap` | 56px | 덩어리 사이 (글자 ↔ 부품, 폰 ↔ 글자) |
| `video-gap-end` | 48px | 엔드 카드 logo ↔ 슬로건 |

- 덩어리들을 간격으로 붙인 묶음 전체를 화면 가운데(가로 · 세로)에 둔다. 남는 공간을 나눠 벌리지 않는다.
- 예외: `match-cut`으로 이어지는 주인공(다음 장면으로든 장면 안 바탕 바뀜으로든, motion.md 3장)은 화면 가운데 가로줄에 두고, 나머지 덩어리는 그 위 · 아래에 간격으로 붙인다.

---

## 4. 폰 프레임

화면 이미지(src/screens, 780×1688 = 390×844 @2x)를 감싸는 프레임. 크기 · 모서리는 여기서 정한 값, 색은 design.md.

| 토큰 | 값 | 출처 |
|---|---|---|
| `phone-screen` | 416×900 (390×844 × 1.066) | 1080 높이 안에 들어가도록 정함 |
| `phone-bezel` | 14px | 정함 |
| `phone-size` | 444×928 (화면 + 베젤) | 위 두 값의 합 |
| `phone-radius` | 바깥 64px · 화면 50px | 정함 |
| `phone-color` | `#18191b` | design.md `color-text` |
| `phone-screen-bg` | `#ffffff` | design.md `color-bg` |

- 노치 · 다이내믹 아일랜드 없음. 화면 이미지에 상태 바(9:41)가 이미 있다.
- 그림자 없음 (피그마 카드 컴포넌트에 Effect 없음 — stat-card · skill-card · mission-card · asset-card 모두 `Shadow/*` 미적용, 2026-10-25 Figma MCP로 확인). 밝은 배경 위에서 `phone-color` 베젤만으로 구분된다.
- 화면 이미지는 자르거나 고치지 않는다. 배율만 바꾼다.
- 예외 (요청 2026-10-24): 화면 이미지 속 요소를 parts로 움직일 때(motion.md 3장 `button-press`), 그 자리에 parts를 화면 이미지와 같은 배율(`phone-screen` 배율 1.066)로 겹치고, 바로 아래에 같은 모서리의 덮개판을 깐다 (크기는 사방 1px 크게 — 확대 보간으로 번지는 원래 가장자리를 가리기 위해, 화면 이미지 @1x 기준). 덮개판 색은 그 요소가 놓인 카드 바탕 (`phone-screen-bg` = `color-bg`). 화면 이미지 파일은 그대로 둔다. 03-mission 제출하기 버튼 자리: 화면 이미지 @1x 기준 x 20 · y 753 · 350×44 (2026-10-25 새 PNG에서 잼, 전 PNG는 y 705).

---

## 5. parts

src/parts의 HTML 부품을 `video-scale`(× 2.8)로 키워 쓴다. 그러면 부품 안 글자가 3장 크기와 같아진다.

| 부품 | Figma 크기 | 영상 크기 (× 2.8) |
|---|---|---|
| mission-card | 350×253 | 980×708 |
| stat-card | 350×101 | 980×283 |
| asset-card | 350×74 | 980×207 |
| skill-card-1 · 2 · 3 | 350×88 | 980×246 |
| button-submit | 350×44 | 980×123 |
| badge-approved | 108×32 | 302×90 |
| brand-icon | 98×98 | 274×274 |
| logo (logotype-*) | 149×19 | 417×53 |
| logo (symbol-*) | 100×100 | 280×280 |

- 부품 원본은 고치지 않는다. 상태는 각 부품의 `data-state` · CSS 변수로만 바꾼다 (부품 주석대로).
- 배율은 부품 전체에 한 번만 건다. 글자만 따로 키우거나 줄이지 않는다.
- stat-card · skill-card는 흰 바탕에 모서리 12(`radius-card`)와 안쪽 여백 20(`space-page`)이 있는 카드다. `video-bg`(흰색) 위에서는 모서리와 여백이 안 보여 카드 모양이 사라지므로 `video-bg-soft` 위에 놓는다. mission-card는 테두리 1px이 있어 `video-bg` 위에 놓아도 된다.
- stat-card와 asset-card가 한 장면에 나오면 부품으로 따로 놓지 않고 05-assets 화면(폰 프레임) 안에서 보여준다 (둘이 원하는 바탕이 달라서).
- asset-card는 바탕이 `color-surface`(#f7f7f8)라 `video-bg-soft` 위에서는 사라진다. `video-bg` 위에만 놓는다.
- logo 색: `video-bg` · `video-bg-soft` · `video-bg-character` 위에는 `*-black`, `video-bg-brand` · `video-bg-dark` · `video-bg-end` 위에는 `*-white`.

배율 예외 (× 2.8이 아닌 것, 이 두 개뿐)

| 토큰 | 부품 | 크기 | 쓰는 곳 |
|---|---|---|---|
| `logo-hero` | logo (logotype-*) | × 6 = 894×114 | 엔드 카드 주인공 |
| `icon-inline` | brand-icon | 높이 95px (`video-display` 행간) | `word-swap`으로 글줄 안 단어 자리에 들어갈 때 |
