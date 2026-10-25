# decisions — launch-30s

## 새 Pattern 후보

승인 전엔 쓰지 않음 (motion.md 3장 "새 후보"와 같은 규칙). 숫자는 레퍼런스 측정값이며 우리 값이 아니다.

| 후보 | 무엇 | 왜 후보인가 | 출처 |
|---|---|---|---|
| `word-flip` | 헤드라인 한 단어 자리만 바뀜: 나가는 단어가 살짝 내려갔다(anticipation) 위로 던져지며 90° 넘어가고, 새 단어가 아래에서 넘어와 안착. 슬롯 폭은 가장 긴 단어로 고정, 줄 재배치 없음. 들어오는 단어가 겹쳐 먼저 시작 (측정: 나감 · 들어옴 각 9f, 겹침 3f, 간격 35f) | motion.md에 단어 → 단어 교체 없음 (`word-swap`은 단어 → brand-icon). 3D 회전 · anticipation(목표 반대로 먼저 움직임)은 1장 토큰에 없고, 1장 "넘치지 않는 곡선" 규칙과 맞는지 확인 필요 | snapcn-word-flip |
| `type-fade` | `text-type` + 글자마다 페이드 인 · 타이핑 간격 불균일 (측정: 글자 페이드 6f, jitter 0.18) | `text-type`은 "그냥 나타남 (움직임 없음)" · 고른 `type-step` | snapcn-word-flip |
| `float-loop` | 등장 뒤 폰이 위아래로 계속 천천히 흔들림 (측정: 주기 135f, 진폭 6px) | motion.md 4장 "hold 동안 멈춰 있다"와 반대 · 해당 토큰 없음 | snapcn-phone-frame |
| `phone-fade-in` | 폰이 이동 없이 투명도 0 → 1 + 살짝 작은 크기에서 1로 (측정: scale 0.96) | `screen-reveal`은 "폰에 따로 `enter` 없음" · `scale-from`은 0뿐 | snapcn-phone-frame |
| `cam-crane` (승인 2026-10-24 → motion.md 1장 `crane-angle` · 5장 `cam-crane`) | 카메라가 왼쪽 아래 낮은 각도에서 정면으로 각도를 바꾸며 올라옴 (3D 시점 변화) | 5장 카메라는 평면 확대 · 이동만 (`cam-in` · `cam-follow` · `cam-pull`). 쓸기 · 줌인 부분은 아래 기존 후보 | snapcn-phone-frame `showcase` |
| `word-build` (빼기로 2026-10-24) | 제목이 단어 하나씩 컷으로 붙고 줄이 다시 가운데 정렬, 첫 단어는 작게서 커짐 · 머무는 동안 구절이 천천히 커짐 (측정: 첫 단어 5f, 간격 8–9f) | 단어 단위 등장 · 재정렬 없음, hold 중 확대는 4장 "멈춤"과 반대 | skillry-saadpastadev |
| `shape-morph` (승인 2026-10-24 → motion.md 3장 `shape-morph`) | 검색창이 채워짐 → 점으로 수축 → 점에서 차트 선이 그려져 다음 화면 차트 자리로 (측정: 9f · 7f · 5f · 6f) | 앞 부품 형태를 다음 장면이 이어받는 전환 없음 (`match-cut`은 같은 자리 · 같은 크기) | skillry-saadpastadev |
| `screen-dissolve` (빼기로 2026-10-24) | 앞 장면이 흐려지는 동안 다음 화면이 제자리에 겹쳐 나타남 (측정: 겹침 4–12f) | `transition`은 컷뿐 | skillry-saadpastadev |
| `token-fly` (빼기로 2026-10-24) | 아이콘이 화면 밖에서 날아와 다음 화면 목록 줄 아이콘 자리로 줄어들며 하나씩 안착 | 요소가 장면을 건너 이동하는 움직임 없음 | skillry-saadpastadev |
| `value-tick` (빼기로 2026-10-24) | 머무는 동안 숫자가 3–8f마다 계속 바뀜 | 4장 "hold 동안 멈춤"과 반대 | skillry-saadpastadev |
| `keypad-entry` (빼기로 2026-10-24) | 키 누름 강조와 함께 금액 자리수가 하나씩 붙음 (측정: 간격 6–7f) | `count-up`은 값 보간 · 자리수 입력 없음 | skillry-saadpastadev |
| `swipe-confirm` (빼기로 2026-10-24) | 버튼이 옆에서 밀려 들어옴 → 손잡이가 끝까지 끌리며 뒤가 채워짐 → 버튼이 줄며 로딩으로 (측정: 15f · 15f) | 끌기 · 채움 움직임 없음, 스와이프 버튼 부품 src에 있는지 확인 필요 | skillry-saadpastadev |
| `slot-roll` (승인 2026-10-24 → motion.md 3장 `slot-roll`) | 윗줄 고정, 아랫줄 이름만 세로로 연속해 굴러 바뀜, 점점 빨라지다 마지막 문구에서 멈춤 (측정: 구름 3–4f, 간격 10f→7f, 끝 머묾 25f) | `word-flip`과 합칠지 사람 확인 · 가속 간격 토큰 없음 | skillry-saadpastadev |
| `punch-cut` (승인 2026-10-24 → motion.md 3장 `punch-cut`) | 같은 로고를 와이드에서 크게(측정 1.71배) 하드컷, 직전 움직임 방향이 컷 너머로 이어짐 | `match-cut`은 같은 자리 · 같은 크기 | snapcn-wordmark-cut |
| `settle-overshoot` (빼기로 2026-10-24) | 안착 때 목표를 넘었다 돌아옴 (측정: 8f, 5px@720) | 1장 "넘치지 않는 곡선" 규칙과 반대 | snapcn-wordmark-cut |
| `row-marquee` (빼기로 2026-10-24) | 카드 여러 줄이 멈추지 않고 가로로 흐름, 이웃 줄은 반대 방향 · 다른 이징 | 계속 흐르는 움직임 없음 (4장 "멈춤"과 반대) | snapcn-roster-grant |
| `cam-settle` (빼기로 2026-10-24) | 첫 프레임부터 살짝 확대된 카메라가 천천히 × 1로 물러나고 그동안 요소도 움직임 (측정: 1.184 → 1, 90f) | 5장 "카메라 움직이는 동안 요소 시작 안 함"과 반대 · 기존 `cam-release`와 같은지 확인 필요 | snapcn-roster-grant |
| `pointer-click` (빼기로 2026-10-24) | 포인터가 두 번에 나눠 들어와 버튼 끝에 안착 · 클릭, 버튼 상태 1f 전환, 포인터 오른쪽 아래로 나감 | 커서는 `text-type`뿐, 포인터 부품 없음 | snapcn-roster-grant |
| `grant-light` (빼기로 2026-10-24) | 클릭 뒤 모노그램이 줄을 섞은 순서로 하나씩 1f 만에 켜짐 (측정: 7f 간격) | `emphasis` + `stagger`와 비슷하나 섞인 순서 · 즉시 전환 없음 | snapcn-roster-grant |

기존 후보와 겹친 것 (새로 쓰지 않음)

- 기존 후보와 같음: `whip-blur` — word-flip 나갈 때 모션 블러 (snapcn-word-flip)
- 기존 후보와 같음: `word-swap` — 한 단어 슬롯만 바꾸는 구도 (대상이 brand-icon인 경우) (snapcn-word-flip)
- 기존 후보와 같음: `phone-rise-tilt` — 등장 `rise`(70px 오르며 페이드) · `rotate-in`(-8° 회전 · 0.94 → 1) (snapcn-phone-frame)
- 기존 후보와 같음: `phone-tip` — 변형 `tilt`(정적 rotateY -12°) (snapcn-phone-frame)
- 기존 후보와 같음: `cam-pan` · `cam-push` — `showcase`의 위로 쓸기 · 줌인 (snapcn-phone-frame; 마지막 당겨 빠짐은 기존 `cam-pull`)
- 기존 후보와 같음: `cam-push` · `cam-pan` · `icon-expand` · `modal-dismiss` · `orbit-collapse` · `line-draw` · `word-flip` (skillry-saadpastadev)
- 기존 후보와 같음: `cam-push`(끝 가속 push, `hold-end`와 부딪힘) · `cam-drift`/`cam-pan`(컷 직전 drift) (snapcn-wordmark-cut)
- 기존 후보와 같음: `cam-pan`(끝 가속 팬) · `button-press` 차이(스프링 복귀 약 3배) (snapcn-roster-grant)
