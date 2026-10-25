# decisions — launch-c

- 고른 안: a (뼈대 그대로 "하나가 여럿으로, 다시 하나로") · 이유: 사람 선택 (이유 말 없음) · 2026-10-25

## 장면표 detail — 안 a (조립)

장면 · 이름 · 조립한 토큰 · 근거 비트
- 장면1 · `cam-pull` 격자 · `cam-pull` (`cam-in` → × 1 · `dur-l` · `ease-inout`)을 `screen-reveal` 밖에서 brand-icon 격자에 씀, 격자는 첫 프레임부터 놓여 있고 주변 `enter` 없음 · 1password 비트1
- 장면1→2 · 깊이 컷 · 격자 전체 × 1 → `scale-from` · `dur-s` · `ease-in` → `transition` → 다음 장면 `cam-release` · 1password 비트3 컷 + langease 비트1–3 전환
- 장면4 · button-press → cam-pan · `button-press` 앞 `hold-m` · 누름 · 뗌 → 떼는 끝 프레임에 `transition` 대신 다음 `cam-pan` · 1password 비트7 (항목 사이 `cam-pan`)
- 장면5 · 그물 붙음 · 둘레 부품 5개 `part-in` + `stagger` (brand-icon 둘레) · 1password 비트8 (`orbit-in` 대신 우리 부품)
- 장면5 · 그물 나감 · 그물 부품만 `scene-out` (brand-icon 남음) · 1password 비트9→10 (`orbit-collapse` 대신)
- 장면5→6 · 주인공 이어받기 · 그물 `scene-out` 절반에서 `transition` + brand-icon 같은 자리 (`match-cut`, 크기는 `dolly-scale` 상태 → × 1) · 1password 비트9→10 · 시각 규칙 4
- 장면6 · 아이콘 → 엔드 · `icon-spin` → `hold-s` → brand-icon `exit` → `end-reveal` · 1password 비트10→11

## 기록 보충 (critic)

- 장면1→2 · 기본 스타일 `cut-in-motion` (motion.md 3장 장면 경계) 대신 비트 시트 1password 비트3 컷 + langease 비트1–3 깊이 컷 (`scale-from` 나감 → `transition` → `cam-release`)
- 장면2 · 기본 스타일 "카메라 움직이는 동안 요소 시작 안 함" (motion.md 5장) 대신 비트 시트 1password 비트4 (`cam-release` 동안 `icon-spin`)
- 장면2→3 · 기본 스타일 `cut-in-motion` (motion.md 3장 장면 경계) 대신 비트 시트 1password 비트5 `cam-pan` 오른쪽
- 장면3→4 · 기본 스타일 `cut-in-motion` (motion.md 3장 장면 경계) 대신 비트 시트 1password 비트6 `cam-pan` 아래
- 장면4→5 · 기본 스타일 `cut-in-motion` (motion.md 3장 장면 경계) 대신 비트 시트 1password 비트7 컷 (`transition`, 다음 첫 프레임 주인공 아이콘 크게)
- 장면5 · 기본 스타일 "hold 동안 카메라 정지" (motion.md 4장) 대신 비트 시트 1password 비트9 `cam-dolly-out`

## 장면표 detail — 안 a 다시 (조립, 2026-10-25)

장면 번호가 바뀜: 옛 장면2 + 3 → 새 장면2 · 옛 4 → 3 · 옛 5 → 4 · 옛 6 → 5. 위 줄은 옛 번호. 아래는 바뀐 조립만.
장면 · 이름 · 조립한 토큰 · 근거 비트
- 장면2 · 주인공 → 첫 쓰임새 (비트4+5+6 합침) · `cam-release` → 멈춘 뒤 `icon-spin` → `hold-s` → `cam-pan` 오른쪽 (skill-card-1은 첫 프레임부터 화면 밖에 놓여 있음) → `hold-m` · 1password 비트4 · 5→6 (옛 장면2의 `cam-release` 동안 `icon-spin`은 카메라 멈춘 뒤로 옮김)
- 장면3 ⑤ · stat-card → asset-card 이동 · `cam-pan` + `pan-bg-shift` (video.md 5장 예외 승인, `?새 후보` 표시 지움) · 1password 비트7
- 장면4 · 다시 주인공 → 그물 · 컷 너머 brand-icon `cut-scale` → `cam-release` → 멈춘 뒤 둘레 5개 `part-in` + `stagger` → `hold-l` 동안 `cam-dolly-out` → 그물만 `scene-out` · 1password 비트7→8 (컷 너머 주인공 클로즈) · 비트8 `cam-release` · 비트9
- 장면4 · 부품 글자 크기 · `cam-dolly-out` 동안 × 1 아래 parts 글자 31px 미만 허용 (video.md 1장 예외 승인) · 1password 비트9
- 장면5 · 엔드 길이 · `hold-end` docs 값 그대로, 장면 길이 = 움직임 + hold 합 · 사람 결정 2026-10-25

## 기록 보충 (critic)

새 장면 번호 (2026-10-25 scenes 2회차).
- 장면2 · 기본 스타일 "한 장면에 카메라는 한 묶음" (motion.md 5장) 대신 비트 시트 1password 비트4 `cam-release` → 비트5→6 `cam-pan` 오른쪽 (합친 비트4+5+6)
- 장면4 · 기본 스타일 "한 장면에 카메라는 한 묶음" (motion.md 5장) 대신 비트 시트 1password 비트8 `cam-release` → 비트9 `cam-dolly-out` (합친 비트8+9)
