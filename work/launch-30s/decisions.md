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

기존 후보와 겹친 것 (새로 쓰지 않음)

- 기존 후보와 같음: `whip-blur` — word-flip 나갈 때 모션 블러 (snapcn-word-flip)
- 기존 후보와 같음: `word-swap` — 한 단어 슬롯만 바꾸는 구도 (대상이 brand-icon인 경우) (snapcn-word-flip)
- 기존 후보와 같음: `phone-rise-tilt` — 등장 `rise`(70px 오르며 페이드) · `rotate-in`(-8° 회전 · 0.94 → 1) (snapcn-phone-frame)
- 기존 후보와 같음: `phone-tip` — 변형 `tilt`(정적 rotateY -12°) (snapcn-phone-frame)
- 기존 후보와 같음: `cam-pan` · `cam-push` — `showcase`의 위로 쓸기 · 줌인 (snapcn-phone-frame; 마지막 당겨 빠짐은 기존 `cam-pull`)
