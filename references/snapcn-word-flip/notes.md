# notes — snapcn-word-flip

근거: `source.md`(prop 기본값) · `poster.webp`(640×360 한 장). 원본 영상 없음 → 프레임 추출 안 함.
용도: 구도 · 전환 · 패턴 참고만. 색(gradient) · 폰트 · 글자 · 화면 배치는 가져오지 않는다 (motion.md 머리말).
박자: 별도 레퍼런스 없음 → motion.md 4장 hold 이름으로 대신.
"측정" = source.md 값을 30fps 프레임으로 바꾸거나 포스터에서 잰 값. 쓰지 않고 기록만 한다. 쓸 값은 docs 이름.

---

## 1. 구도 · 전환 · 패턴

### 구도

| 항목 | 레퍼런스 (측정) | 가장 가까운 이름 |
|---|---|---|
| 헤드라인 한 줄이 화면 가운데 | 포스터: 줄 세로 중심 ≈ 180/360 (50%), 줄 폭 ≈ 487/640 (76%) | video.md 3장 "묶음 전체를 화면 가운데" (움직임 아님) |
| 한 단어만 강조 | 포스터: "Modern" 한 단어만 다른 색 | 움직임 아님 — motion.md 3장 아래 "강조 색 글자는 움직임이 아니다" · 색은 video.md 3장 `video-text-accent` |
| 단어 슬롯 폭 고정 (가장 긴 단어 기준, 줄 재배치 없음) | source.md | 없음 → decisions.md `word-flip` 후보에 포함 |
| 카메라 | 정지 (포스터 · source.md에 카메라 없음) | `cam-hold` (5장) |

### 전환 · 패턴 (시간 순)

| 순서 | 무슨 일 | 측정 (30fps) | 가장 가까운 이름 |
|---|---|---|---|
| 1 | 첫 키 입력 전 빈 틈 | `typeStart` 4f | 없음 (우리는 빈 바탕 프레임 없음 — `transition` (2장)으로 들어오자마자 시작) |
| 2 | 헤드라인 타이핑 + 커서 깜빡임 | `cps` 9 → 글자당 ≈ 3.3f · `jitter` 0.18 | `text-type` (3장) · 간격 `type-step` (1장) |
| 2a | 글자마다 페이드 인 | `charFade` 6f | 없음 — `text-type`은 "그냥 나타남 (움직임 없음)" → decisions.md `type-fade` 후보 |
| 3 | 타이핑 끝 → 첫 flip 전 머묾 | `pause` 6f | 4장 `hold-m` (제목 한 줄, 15자 넘으면 `hold-l`) |
| 4 | 단어 나감: anticipation dip → 위로 던짐 · 90° 회전 · 0.98 축소 · 모션 블러 | `exitDuration` 9f · `exitY` -1.29em · `rotate` 90° · `blur` 0.085em | `exit` (2장)이 가장 가까움 (다름: 우리는 제자리 투명도 · `dur-s`) → decisions.md `word-flip` 후보 · 흐림은 기존 후보 `whip-blur` |
| 5 | 새 단어 들어옴: 아래에서 회전해 안착, 나가는 단어와 겹쳐 먼저 시작 | `enterDuration` 9f · `overlap` 3f · `enterY` 0.135em · `perspective` 6.5em | `enter` (2장)가 가장 가까움 (다름: 마스크 대신 3D 회전 · 겹침) → decisions.md `word-flip` 후보 |
| 6 | 다음 flip까지 간격 (반복) | `cycle` 35f | 4장 `hold-l` (36f)이 가장 가까운 이름 |

- 레퍼런스 안 장면 경계(다른 장면으로 넘어감)는 없음 → `screen-change` · `match-cut` · `cut-in-motion` (3장)에 대응할 것 없음.

---

## 2. 대응 표

| 레퍼런스 요소 | 우리 쪽 |
|---|---|
| 헤드라인 줄 (Looking For A … Portfolio) | 영상 글자 — video.md 3장 `video-display` · 폰트 `src/assets/fonts/Pretendard-*.otf` (src/parts에 부품 없음). 문구는 가져오지 않음 |
| 바뀌는 단어 슬롯 | 영상 글자 + video.md 3장 `video-text-accent` (색만). 단어 대신 아이콘이 들어가면 `src/parts/brand-icon.html` (video.md 5장 `icon-inline`, 기존 후보 `word-swap`) |
| 타이핑 커서 | 없음 (src에 커서 부품 없음, `text-type`의 커서는 영상에서 그림) |
| 그라디언트 글자 색 · fontSize 72 · fontWeight 600 | 가져오지 않음 (video.md 2장 단색만 · 3장 굵기/크기) |
| 배경 (밝은 회색) | 색은 가져오지 않음 → video.md 2장 `video-bg` |
| 폰 · 화면 | 없음 (이 레퍼런스에 없음) |

---

## 3. 새 후보

motion.md에 없는 움직임은 `work/launch-30s/decisions.md` "## 새 Pattern 후보"에 적었다 (`word-flip` · `type-fade`, 기존 후보와 겹침: `whip-blur` · `word-swap` 참고).
