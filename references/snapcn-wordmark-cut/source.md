# 출처: https://snapcn.dev/docs/scenes/wordmark-cut (2026-10-24 수집)
원본: https://media.snapcn.dev/demos/wordmark-cut.mp4 → `original.mp4` (960×540 · 60fps · 2.2초) · 포스터 `poster.webp`
용도: 구도 · 전환 · 패턴 참고. 색(gradient) · 폰트는 가져오지 않음 (motion.md 머리말).

Remotion 워드마크 엔드카드. 화면 폭 2배짜리 워드마크가 빛나는 그라데이션에서 잉크색으로 식으며 자리잡고,
마지막 글자들과 점으로 하드컷 — 더 가깝고 얕고, 밀고 들어감. 원래 설정 66f @30fps · 1280×720.

| 박자 | 초 | 움직임 |
|---|---|---|
| Settle | 0 – 0.8 | 단어가 50px 위로 올라옴, exponential easing |
| Cool | 0.36 – 1.03 | 글자 빛 → 잉크, linear |
| Drift | 0.66 – 1.20 | 21px 왼쪽으로 미끄러짐, 가속 |
| Cut | 1.20 | 245px 글자 → 419px 글자, 단어 앞쪽에서 끝쪽으로 |
| Spring | 1.20 – 1.45 | 클로즈샷 안착, 5px 오버슈트 |
| Hold | 1.45 – 1.63 | 정지 |
| Push | 1.63 – 2.20 | scale 1 → 1.30, 마지막 프레임까지 가속 |

구도: 두 샷 하드컷. 와이드 = 단어 앞쪽(잉크 윗선 기준 프레이밍), 클로즈 = 1.71배 가까이 · 단어 끝과 점(점 기준 프레이밍).
점은 식지 않고 끝까지 그라데이션.

| prop | 기본값 | 뜻 |
|---|---|---|
| word | "snapcn." | 끝 마침표는 그려진 점으로 |
| warm | 1 | 글자가 가장 밝을 때 빛 양 |
| speed | 1 | 재생 속도 |
| (가져오지 않음) dotFrom #3072db · dotTo #4fd8f5 · fontFamily Inter | | |
- 프레임: `frames/` (10fps, 640폭)
