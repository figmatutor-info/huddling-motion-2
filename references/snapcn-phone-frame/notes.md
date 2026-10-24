# notes — snapcn-phone-frame

근거: `source.md`(변형 · 등장 설정) · `poster.webp`(640×360 한 장). 원본 영상 없음 → 프레임 추출 안 함.
용도: 구도 · 전환 · 패턴 참고만. 기기 모양 · 색 · 크기 · 모서리는 video.md 4장을 따른다. 화면 속 내용 · 배치는 가져오지 않는다 (motion.md 머리말).
박자: 별도 레퍼런스 없음 → motion.md 4장 hold 이름으로 대신.
"측정" = source.md 값을 30fps 프레임으로 바꾸거나 포스터에서 잰 값. 쓰지 않고 기록만 한다. 쓸 값은 docs 이름.

---

## 1. 구도 · 전환 · 패턴

### 구도

| 항목 | 레퍼런스 (측정) | 가장 가까운 이름 |
|---|---|---|
| 폰 하나가 화면 가운데, 정면 (`flat`) | source.md 기본 · 기본 크기 320×656 · radius 53 | video.md 4장 폰 프레임 (`phone-size` · `phone-radius`) + 5장 `cam-hold` |
| 포스터: 폰이 크게 잘려 보임 (아래쪽 화면 밖) | 포스터: 폰 폭 ≈ 325/640 (51%), 위 끝 y ≈ 30/360, 아래는 잘림 → `showcase` 줌인 도중으로 보임 | 5장 `cam-in` 상태가 가장 가까움 (확대 상한 × 2.4 안) |
| 정적 기울기 (`tilt`) | rotateY -12° | 없음 → 기존 후보 `phone-rise-tilt` · `phone-tip` (3장 새 후보) |
| 배경 투명 · 회색 베젤 · 그림자 | 포스터 | 가져오지 않음 — video.md 4장 (`phone-color`, 그림자 없음) · 2장 `video-bg` |

### 전환 · 패턴

| 항목 | 무슨 일 | 측정 (30fps) | 가장 가까운 이름 |
|---|---|---|---|
| 등장 `rise` (기본) | 아래에서 70px 오르며 페이드 · 빠른 ease-out | 70px | `part-in` (3장) 모양이 가장 가까움 (다름: 거리 `dist-m`보다 큼). 단 `screen-reveal` (3장)은 "폰에 따로 `enter` 없음" → 기존 후보 `phone-rise-tilt` |
| 등장 `rotate-in` | 오르며 -8° 평면 회전 · scale 0.94 → 1 | -8° · 0.94 | `tilt` (1장) 쓰는 `logo-reveal` (3장)이 가장 가까움 (대상 다름) → 기존 후보 `phone-rise-tilt` |
| 등장 `float` | 이동 없이 페이드 + 0.96 → 1 커짐 | 0.96 | 없음 (`badge-pulse` (3장)은 `scale-from` 0에서 · 폰에 `enter` 없음 규칙) → decisions.md `phone-fade-in` 후보 |
| float 루프 | 등장 뒤 위아래로 계속 흔들림 | 주기 4.5s = 135f · 진폭 6px | 없음 — 4장 "hold 동안 멈춰 있다"와 반대 → decisions.md `float-loop` 후보 |
| `showcase` 크레인 무브 | 왼쪽 아래 낮은 각도에서 시작 → 위로 쓸며 줌인 → 정면으로 당겨 빠짐 (컴포지션 길이에 맞춰 정규화) | 데모 8.0s = 240f (구간별 길이 없음) | 마지막 "정면으로 당겨 빠짐"만 `cam-pull` (5장). 쓸기 · 줌인은 기존 후보 `cam-pan` · `cam-push` (5장 끝). 낮은 각도 → 정면(3D 각도)은 없음 → decisions.md `cam-crane` 후보 |
| 장면 경계 | 데모는 한 컷 (경계 없음) | — | 대응 없음. 우리 화면 01 → 05는 `screen-change` · `match-cut` (3장) 그대로 |

- 머무는 시간: 레퍼런스는 데모 8s 동안 계속 움직임(float · showcase). 우리는 움직임 끝난 뒤 4장 `hold-l` (화면 한 장 전체)로 멈춘다.

---

## 2. 대응 표

| 레퍼런스 요소 | 우리 쪽 |
|---|---|
| iPhone 프레임 (320×656 · radius 53 · screenRadius radius-12) | video.md 4장 폰 프레임 (`phone-size` 444×928 · `phone-radius` · `phone-bezel` · `phone-color`) — src에 프레임 파일 없음, video.md 값으로 그림. 레퍼런스 크기 · 모서리는 가져오지 않음 |
| 폰 안 화면 (데모: 자연 영상) | `src/screens/01-home.png` · `02-skills.png` · `03-mission.png` · `04-approved.png` · `05-assets.png` (정지 이미지, 자르지 않음 — video.md 4장) |
| 다이내믹 아일랜드 · 노치 | 없음 (video.md 4장 노치 없음) |
| 그림자 · 회색 베젤 · 투명 배경 | 가져오지 않음 → video.md 2장 `video-bg` · 4장 그림자 없음 |
| 폰 옆 글자 · 부품 | 없음 (이 레퍼런스에 없음). 우리는 video.md 3장 간격 `video-gap` · 5장 `src/parts/*` |

---

## 3. 새 후보

motion.md에 없는 움직임은 `work/launch-30s/decisions.md` "## 새 Pattern 후보"에 적었다 (`float-loop` · `phone-fade-in` · `cam-crane`, 기존 후보와 겹침: `phone-rise-tilt` · `phone-tip` · `cam-pan` · `cam-push`).
