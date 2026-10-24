# 출처: https://snapcn.dev/docs/text/word-flip (2026-10-24 수집)
용도: 구도 · 전환 · 패턴 참고. 색(gradient) · 폰트는 가져오지 않음 (motion.md 머리말).

Remotion 3D word-flip. 헤드라인이 타이핑되고, 한 단어 슬롯만 3D로 넘어가며 바뀜. 슬롯 폭은 가장 긴 단어에 고정 → 줄 재배치 없음.
동작: anticipation dip → motion-blur 던지기(위로) → 아래에서 들어와 안착.

| prop | 기본값 | 뜻 |
|---|---|---|
| cps | 9 | 초당 타이핑 글자 |
| typeStart | 4f | 첫 키 입력 전 |
| charFade | 6f | 글자당 페이드 |
| jitter | 0.18 | 타이핑 불균일 |
| pause | 6f | 타이핑 후 첫 flip 전 |
| cycle | 35f | flip 간격 |
| exitDuration | 9f | 나가는 단어 |
| enterDuration | 9f | 들어오는 단어 |
| overlap | 3f | 들어오는 단어가 먼저 시작 |
| caret | true | 타이핑 중 커서 깜빡임 |
| motion.exitY | -1.29em | 위로 던짐 |
| motion.enterY | 0.135em | 아래에서 시작 |
| motion.rotate | 90° | 베이스라인 기준 회전 |
| motion.scale | 0.98 | 나갈 때 축소 / 들어올 때 확대 시작 |
| motion.blur | 0.085em | 최고 속도에서 최대 흐림 |
| perspective | 6.5em | 3D 깊이 |
| (가져오지 않음) gradient #2A8BF5→#D382B0 · fontSize 72 · fontWeight 600 | | |

포스터: poster.webp (640×360). 데모 영상 URL 없음.
