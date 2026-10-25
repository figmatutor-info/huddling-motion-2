# 출처: https://snapcn.dev/docs/scenes/roster-grant (2026-10-24 수집)
원본: https://media.snapcn.dev/demos/roster-grant.mp4 → `original.mp4` (960×540 · 60fps · 4.0초) · 포스터 `poster.webp`
용도: 구도 · 전환 · 패턴 참고. 색 · 폰트는 가져오지 않음 (motion.md 머리말).

Remotion "access granted" 장면. 로스터 카드 세 줄이 CTA 버튼 옆을 흘러가고, 포인터가 들어와 클릭,
모노그램이 하나씩 강조색으로 켜짐. 원래 설정 120f @30fps · 1280×720.

| 박자 | 초 | 움직임 |
|---|---|---|
| Settle | 0 – 3.0 | 카메라 1.184 → 1 풀백, 가운데 줄이 버튼 쪽으로 좁혀옴 |
| Approach | 0 – 1.32 | 포인터 두 번에 나눠 도착 |
| Press | 1.62 – 2.33 | 버튼 눌림 후 스프링 복귀 (복귀가 누름의 약 3배) |
| Flip | 1.69 | 버튼이 한 프레임에 강조색으로 바뀜 |
| Leave | 2.05 – 3.1 | 포인터 오른쪽 아래로 나감 |
| Grant | 2.33부터 0.233초(7f)마다 | 모노그램 하나씩 켜짐, 순서 위·가운데·아래·위·아래·가운데 |
| Push | 3.0 – 4.0 | 장면 전체 왼쪽 팬, 가속 |

구도: 카메라와 가운데 줄은 같은 이징. 바깥 두 줄은 반대 방향 · 다른 이징 → 완전 대칭으로 안 보임.
버튼은 내용 폭, 포인터는 버튼 끝쪽에 안착.

| prop | 기본값 | 뜻 |
|---|---|---|
| rows | registry | 세 줄 { name, role, initials? }, 줄마다 반복 |
| label | "Install all" | 버튼 문구 |
| speed | 1 | 재생 속도 |
| (가져오지 않음) accentColor theme.primary · fontFamily Inter | | |
- 프레임: `frames/` (6fps, 640폭)
