# 출처: https://snapcn.dev/docs/screens/phone-frame (2026-10-24 수집)
용도: 구도 · 전환 · 패턴 참고. 기기 모양 · 색은 video.md 4장 폰 프레임을 따름.

Remotion iPhone 프레임. 배경 투명, 등장 후 부드러운 float 루프. 8.0s · 30fps 데모.

변형(variant)
- flat: 정면 (기본)
- tilt: 정적 rotateY = tiltAngle(-12°)
- showcase: 크레인 무브 — 왼쪽 아래 낮은 곳에서 시작 → 위로 쓸며 줌인 → 정면으로 당겨 빠짐. 컴포지션 길이에 맞춰 정규화.

등장(entrance)
- rise: 기본. 70px 위로 오르며 페이드, 빠른 ease-out
- rotate-in: 오르며 -8° 평면 회전, scale 0.94 → 1
- float: 이동 없음. 페이드 + 0.96에서 커짐, float 루프 0f부터

기타: floatLoop 주기 4.5s · floatAmplitude 6px · 기본 크기 320×656 · radius 53 · screenRadius = radius-12
포스터: poster.webp (640×360). 데모 영상 URL 없음.
