# decisions — launch-b

## 새 후보 (2026-10-25, 1단계)
- `screen-dissolve` → docs에 넣음 (motion.md 3장, `dur-m` · `ease-inout`). 쓰는 장면은 "기본 스타일 컷 대신 비트 시트 겹침"으로 기록.
- `hold-zoom` → 뺌 (대신 `cam-hold`)
- `token-fly` → 뺌 (부품 없음)
- `keypad-entry` → 뺌 (대신 `count-up`)
- `swipe-confirm` → 뺌 (대신 `button-press` → `shape-morph`)

## 장면표 3안 (2026-10-25, director)

새 후보: 3안 모두 0.

### 3안 공통 (a · b · c)
- 비트1 · 2 · 4 · 5 · 7의 짧은 hold (`hold-s` · hold 없이 다음 전환): 비트 시트 시각 규칙 5 (앞 약 30%는 1초 안팎의 짧은 비트) · 규칙 4 (빈 바탕 거의 없음)를 따름. 길이 · hold 이름은 docs 그대로.
- 비트2 → 3: 기본 스타일 `cut-in-motion` (`scene-out` 절반에서 컷) 대신 비트 시트 겹침 (글자가 흐려지는 동안 화면이 올라옴). 조립: 글자 `scene-out` + 폰 `phone-rise-tilt`가 같은 프레임에 시작.
- 비트3 카메라: 비트 시트 `cam-pan` 대신 remotion-device-rise `cam-hold` (사람 지시: 폰이 처음 나오는 비트의 카메라 · 전환은 remotion). 같은 장면에 `screen-reveal` 없음 (motion.md 3장 [고정]).
- 비트5 → 6 · 비트6 → 7: 기본 스타일 `transition` (컷) 대신 비트 시트 `screen-dissolve` (겹침). 비트6은 `button-press`의 "떼는 끝 프레임에 컷"도 `screen-dissolve`로 바꿈 (비트 시트 6 → 7 "button-press → 화면이 흐려지며 다음 화면 겹침").
- 비트5 → 6 전환은 비트 시트 `match-cut`(screen-reveal 뒷부분)과 다름: 앞 장면 주인공(부품)과 다음 장면(폰 화면)이 같은 크기로 이어지지 않아 `match-cut` 조건이 안 됨 → `screen-dissolve`. 반영률에서 뺌.
- 비트6 · 7 구도 "아래 잘림": 새 숫자 없이 화면 속 대상을 화면 가운데에 두는 프레이밍으로 만듦 (`cam-pan`은 × 1 세로 이동).
- 비트8: `button-press` → `shape-morph` (1단계 결정, `swipe-confirm` 대신). 기본 스타일 `button-press` 끝 컷 대신 같은 장면에서 `shape-morph`로 이어짐.
- 비트9 구도: 비트 시트 "가까이 (폰 화면 한 장)" 대신 부품 하나 (`shape-morph` 끝 주인공은 부품이어야 함). 반영률에서 뺌.
- 비트9 → 10 · 비트10: `cam-push` (비트 시트 10에 있음). 기본 스타일 "hold 동안 카메라 정지 · 경계는 `scene-out`" 대신 비트 시트 `cam-push` → 멈추지 않고 `icon-expand` → `transition` (motion.md 5장 [고정] 규칙대로 기록).
- 비트10 → 11 바탕: 비트 시트 "검은 바탕" 대신 `icon-expand`로 커진 부품 바탕색 (stat-card → `video-bg`, asset-card → `video-bg-soft`). 검은 바탕 부품(`video-bg-dark`와 같은 색)이 src에 없음.
- 비트12: `end-reveal` 대신 `logo-reveal`만 (슬로건 · 주소 줄 없음). 슬로건을 넣으면 비트12가 비율 +5%p를 넘음.
- 비트 시트 시각 규칙 3 (앱 화면이 보이는 동안 영상 글자 0): 3안 모두 따름 (비트4 입력 글자도 0).
- 조립 (3안 공통):
  - 비트1 단어 등장 — `enter` + 마스크 대신 `scale-from` → 1, 단어 사이 `stagger` (항목 간격), 구절 갈아끼우기 `transition`.
  - 비트2 brand-icon 등장 — `enter` + 마스크 대신 `scale-from` → 1 (`logo-reveal` 앞부분에서 `tilt`를 뺀 것 = `badge-pulse`와 같은 구성), 글자 `enter`와 `stagger`.
  - 비트2 → 3 — `scene-out` + `phone-rise-tilt` 겹침 (위).
- (2026-10-25 critic 불합격 수정) 장면1 → 2 (비트1 → 2): 기본 스타일 `cut-in-motion` (motion.md 3장 · `scene-out` 절반에서 컷) · 4장 "경계는 `scene-out`으로 넘긴다" 대신 비트 시트 비트1 전환 `transition` (컷, 다음 구절이 같은 자리). `hold-s` 뒤 `scene-out` 없이 순수 컷 (비트 시트 시각 규칙 4: 순수 컷은 글자 갈아끼우기에).
- (2026-10-25 critic 불합격 수정) 장면1 안 구절1 → 구절2: 기본 스타일 4장 "경계는 `scene-out`으로 넘긴다" 대신 비트 시트 비트1 "두 구절이 컷으로 갈아끼워짐" · 전환 `transition` (컷, 다음 구절이 같은 자리). `hold-s` 뒤 `scene-out` 없이 순수 컷.
- (2026-10-25 critic 불합격 수정) 장면7 → 8 (비트7 → 8): 기본 스타일 `cut-in-motion` (motion.md 3장) · 4장 "경계는 `scene-out`으로 넘긴다" 대신 비트 시트 비트7 전환 `transition` (컷). `hold-l` 뒤 `scene-out` 없이 순수 컷 (비트 시트 시각 규칙 4: 순수 컷은 버튼 등장에 — 장면8은 button-submit `part-in`).

### 안 a
- 비트4 · 5: button-submit `apply-case` → `shape-morph` → mission-card. 비트5 주인공 `scale-from` → 1 뒤 hold 없이 `screen-dissolve` — 기본 스타일 "다음 움직임은 앞 hold가 끝난 뒤" 대신 비트 시트 이어받기 (비트 5 → 6 사이 머묾 없음).
- 조립: 비트9 stat-card — `shape-morph` 끝 (`scale-from` → 1)이 `count-up`의 `part-in` 자리를 대신함 → 바로 `count-up` → `hold-s`.
- 비트7 `count-up` 없음: 04-approved 화면 이미지 위에 부품을 겹치지 않음 (video.md 4장 겹침은 `button-press`용). `count-up`은 비트9 stat-card에서.
- (2026-10-25 critic 불합격 수정) 장면3 → 4 (비트3 → 4): 기본 스타일 `match-cut` → `cut-in-motion` (motion.md 3장) · 4장 "경계는 `scene-out`으로 넘긴다" 대신 비트 시트 비트3 전환 "화면 속 입력창 하나로 확대 → 가장 가까운 `zoom-through`". `hold-l` 뒤 `scene-out` 없이 `zoom-through` (대상: 01-home "적용 사례 정리하기 →" 버튼 자리) → 끝 프레임 `transition`, 장면4 button-submit이 그 자리에서 이어짐.

### 안 b
- 비트4 · 5: button-submit `submit` → `shape-morph` → badge-approved. 비트5 주인공 `scale-from` → 1 뒤 hold 없이 `screen-dissolve` — 기본 스타일 "다음 움직임은 앞 hold가 끝난 뒤" 대신 비트 시트 이어받기.
- 비트7 `count-up` 없음 (05-assets 화면 이미지 위에 부품 겹치지 않음). 수익 숫자는 비트11 `slot-roll` 영상 글자로 ("₩9,900" → "₩29,700").
- 비트12가 비율 +3.2%p (마지막 hold 정지로 채움, motion.md 4장 예외).
- (2026-10-25 critic 불합격 수정) 장면3 → 4 (비트3 → 4): 기본 스타일 `match-cut` → `cut-in-motion` (motion.md 3장) · 4장 "경계는 `scene-out`으로 넘긴다" 대신 비트 시트 비트3 전환 "화면 속 입력창 하나로 확대 → 가장 가까운 `zoom-through`". `hold-l` 뒤 `scene-out` 없이 `zoom-through` (대상: 03-mission "제출하기" 버튼 자리) → 끝 프레임 `transition`, 장면4 button-submit이 그 자리에서 이어짐.

### 안 c
- 비트4 → 5: 비트 시트 `shape-morph` 대신 `cut-in-motion` (skill-card는 `shape-morph` 대상이 아님 — motion.md 3장 대상 button-submit). 반영률에서 뺌.
- 비트5: mission-card `mission-in` → `hold-s` → `screen-dissolve` (기본 스타일 컷 대신 비트 시트 겹침, 공통과 같음).
- 비트11 아랫줄은 여러 자산의 상태 문구(05-assets 칩 · asset-card 상태 줄)를 차례로 보여줌. 윗줄은 특정 자산 이름이 아니라 "내 자산"으로 둬서 한 자산의 실제 상태처럼 보이지 않게 함.
- (2026-10-25 critic 불합격 수정) 장면3 → 4 (비트3 → 4): 기본 스타일 `match-cut` → `cut-in-motion` (motion.md 3장) · 4장 "경계는 `scene-out`으로 넘긴다" 대신 비트 시트 비트3 전환 "화면 속 입력창 하나로 확대 → 가장 가까운 `zoom-through`". `hold-l` 뒤 `scene-out` 없이 `zoom-through` (대상: 02-skills 목록 첫 줄 "회의록을 실행 목록으로" 자리) → 끝 프레임 `transition`, 장면4 skill-card-1이 그 자리에서 이어짐.

## 고른 안 (2026-10-25, 승인 1)
- 안 a "미션을 해내는 과정" — 사람이 고름. scenes-a.md → scenes.md.
- 판정: 2회째 critic (a · b · c 한 번에) 통과 · 반영 92% · 반복 없음. 기록 누락 7줄은 director가 보충함 (규칙 변경 전). 규칙 변경(기록 누락 = 불합격 아님) 뒤 남은 사유(없는 값 · 없는 UI · 반영률 · 반복)는 그 판정에서 이미 0 · 0 · 92% · 없음.

## 스냅보드 승인 (2026-10-25, 승인 2)
- critic(snapboard) 통과 → 사람 승인. snapboard.png(4열 그리드) 추가.
- 열린 문제 (영상 전에 정할 것):
  - 장면 3 → 4 `zoom-through`: 01-home 속 버튼은 `cam-in` ×2.4 끝에서 폭 약 814px, 장면 4 button-submit ×2.8은 약 890px → 컷에서 약 9% 커짐. 맞추려면 docs에 없는 배율이 필요.
  - 장면 6 대표 컷: `cam-pan` 끝(제출하기가 화면 가운데)이라 폰 아래쪽 약 450px가 빈 바탕. 장면표 "아래 잘림"은 시작 프레이밍에만 맞음.
