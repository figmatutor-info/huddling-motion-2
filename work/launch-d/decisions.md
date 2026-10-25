# decisions — launch-d

- 2026-10-25 새 후보 `card-rail` docs에 넣음 (사람 승인): 바탕은 asset-card로 넘어가는 튕김 동안 soft → bg 전환 · 세로 가운데 맞춤 · badge-approved는 줄에서 빼고 mission-card에서 `mission-done`. → motion.md 3장 · video.md 5장 예외
- 2026-10-25 새 후보 `plane-tilt` · `rail-tilt` docs에 넣음 (사람 승인): `plane-angle` rotateX 55° · rotateZ -20° (원본 측정) · 폰 phone-size + video-gap · dur-l · ease-inout · dolly-scale로 조립 / `rail-angle` rotateX 20°. → motion.md 1장 · 3장
- 2026-10-25 넣지 않음 (그 요소 없이 진행): parts-fly · word-blob · screen-build · phone-trio · snap-row · float-loop
- 2026-10-25 고른 안: a · 이유: BRIEF 흐름(스킬 → 제출 → 승인 → 수익) 그대로, 폰 등장(비트7) 강조 — 사람 선택

## 장면표 detail — 안 a (조립)

장면 · 이름 · 조립한 토큰 · 근거 비트
- 장면1 · 흩어짐 → 아이콘 · 부품 6개 첫 프레임부터 놓임 → `hold-s` → `scene-out` → 빈 프레임에 카메라를 `cam-in` 상태로 둠 → brand-icon `flip-turn` (180° → 0, 뒷면 안 보임) · `dur-m` · `ease-out` (`logo-reveal`의 `scale-from` · `tilt` 대신) → `cam-pull` → logo 글자 `enter` · `stagger` `dur-xs` · skillry-lnkiai 비트1 (흩어짐) · 비트2 (돌며 앞면 · 물러남 · 이름 글자)
- 장면1 · `cam-pull` 대상 brand-icon · `cam-pull` (`cam-in` → × 1 · `dur-l` · `ease-inout`)을 `screen-reveal` 밖에서 씀, 주변 `enter` 없음 · skillry-lnkiai 비트2
- 장면2 · 단어 컷 · 단어마다 `enter` → `hold-s` → `transition` (바탕 · 단어 같이 컷) · skillry-lnkiai 비트3 (`word-blob` 없이)
- 장면3 · 폰 줄 물러남 → 훑음 · `cam-pull` (01-home 미션 카드 → 01-home 폰, `screen-reveal` 밖) → `hold-l` → `cam-pan` (거리 = 폰 두 대 간격 = 2 × (`phone-size` 폭 + `video-gap`)) → `hold-l` · skillry-lnkiai 비트4 · 5
- 장면4 · 평면 머묾 · 밀고 들어감 · `plane-tilt` 뒤 `hold-l` 동안 `cam-drift` (`dolly-scale` 상태 그대로) → `cam-push` (`dolly-scale` 상태에서 `cut-scale`만큼 더, 대상 02-skills 폰) · skillry-lnkiai 비트6
- 장면5 · 폰 + 제목 한 덩어리 → 화면 컷 · `phone-rise-tilt` + `headline-in` `stagger` (hold 한 번) → `screen-change` 02 → 03 + 같은 컷에 바탕 `video-bg-soft` → `video-bg` · skillry-lnkiai 비트7 (`phone-trio` 없이 바탕 · 화면 컷) · remotion-device-rise 비트1
- 장면8 · 튕김 → 숫자 · 튕김 도착을 `count-up`의 `part-in` 자리로 씀 · `count-up` 뒤 `hold-s`는 card-rail 마지막 `hold-m`이 덮음 · badge-approved는 mission-card 아래 `video-gap-s`, 같이 튕김 · skillry-lnkiai 비트10+11 · snapcn-card-rail 비트1
- 장면8 → 9 · 같은 평면 이어짐 · `match-cut` + 장면9에 `rail-angle` 평면을 이어 씀 (stat-card · badge-approved) · skillry-lnkiai 비트11 → 12 "이어짐" — 다시 쓰기에서 없앰 (아래)
- 장면9 · 비켜남 → 내려앉음 · stat-card 위로 (거리 = stat-card + `video-gap` + badge 묶음 가운데 맞춤) · `dur-m` · `ease-out` → badge-approved `enter` + 마스크 대신 `cut-scale` → 1 · 투명도 0 → 1 · `dur-m` · `ease-out` → `hold-m` → `cam-push` → `screen-dissolve` · skillry-lnkiai 비트12 — 다시 쓰기에서 없앰 (아래)

## 기록 보충 (critic)

- 2026-10-25 장면1 · 기본 스타일 `cut-in-motion` 대신 비트 시트 비트2 "컷 (transition, 이어지는 요소 없음)"
- 2026-10-25 장면1 · 기본 스타일 "다음 움직임은 앞 hold가 끝난 뒤" 대신 비트 시트 비트1→2 "모임 → 돌며 앞면 → 물러남 → 이름 글자" 이어짐 (scene-out · flip-turn · cam-pull 사이 hold 없음)
- 2026-10-25 장면2 · 기본 스타일 `cut-in-motion` 대신 비트 시트 비트3 "컷 (흐림 섞인 컷)"
- 2026-10-25 장면3 · 기본 스타일 "한 장면에 카메라는 한 묶음" 대신 비트 시트 비트4 `cam-pull` → `cam-pan`
- 2026-10-25 장면3 · 기본 스타일 "폰 한 장면" 대신 비트 시트 비트4 · 5 폰 흐름도
- 2026-10-25 장면3 · 기본 스타일 `cut-in-motion` 대신 비트 시트 비트5 "이어짐 (plane-tilt)"
- 2026-10-25 장면4 · 기본 스타일 "한 장면에 카메라는 한 묶음" 대신 비트 시트 비트6 plane-tilt → `cam-drift` → `cam-push`
- 2026-10-25 장면4 · 기본 스타일 "hold 동안 카메라 정지" 대신 비트 시트 비트6 `cam-drift`
- 2026-10-25 장면4 · 기본 스타일 "경계는 scene-out" 대신 비트 시트 비트6 `cam-push` 끝 컷
- 2026-10-25 장면4 · 기본 스타일 "폰 한 장면" 대신 비트 시트 비트6 폰 5대 평면
- 2026-10-25 장면4 · 기본 스타일 `cut-in-motion` 대신 비트 시트 비트6 "cam-push 끝 프레임에서 컷"
- 2026-10-25 장면4 · 기본 스타일 "다가간 장면은 대상 동작(button-press · shape-morph)으로 넘김" 대신 비트 시트 비트6 `cam-push` 끝 컷 (장면표에 `대신:` 없음 · critic 대조)
- 2026-10-25 장면5 · 기본 스타일 "폰 한 장면" 대신 비트 시트 비트7 폰 한 대
- 2026-10-25 장면5 · 기본 스타일 `cut-in-motion` 대신 비트 시트 비트7 "컷"
- 2026-10-25 장면6 · 기본 스타일 "부품 장면에는 그 부품만" 대신 비트 시트 비트8 "부품 줄 아래 가운데 한 줄"
- 2026-10-25 장면7 · 기본 스타일 "hold 동안 카메라 정지" 대신 비트 시트 비트9 `cam-drift`
- 2026-10-25 장면7 · 기본 스타일 `cut-in-motion` 대신 비트 시트 비트9 "어둡게 → 밝게" 바탕 바뀜 뒤 컷
- 2026-10-25 장면9 · 기본 스타일 "경계는 scene-out" 대신 비트 시트 비트12 `cam-push`
- 2026-10-25 장면9 · 기본 스타일 `cut-in-motion` 대신 비트 시트 비트12 "cam-push + 밝아짐" → `screen-dissolve`
- 2026-10-25 장면9 · 기본 스타일 "다음 움직임은 앞 hold가 끝난 뒤" 대신 비트 시트 비트11→12 "숫자가 비켜나고 같은 자리에 큰 글자" (stat-card 위로 → 배지 사이 hold 없음 · 장면표에 `대신:` 없음 · critic 대조)
- 2026-10-25 장면9 · 기본 스타일 "다가간 장면은 대상 동작(button-press · shape-morph)으로 넘김" 대신 비트 시트 비트12 `cam-push` → 밝아짐 (장면표에 `대신:` 없음 · critic 대조)

## 장면표 detail — 안 a 다시 (조립, 2026-10-25 critic 1회차 불합격 수정)

장면 · 이름 · 조립한 토큰 · 근거 비트
- 장면2 · 글자 컷 · 줄마다 `enter` → `hold-s` → `transition` (바탕 · 글자 같이 컷), 글자는 화면 제목 3개 (02 · 03 · 05) 그대로 · skillry-lnkiai 비트3
- 장면8 → 9 · 이어짐 대신 `cut-in-motion` (`match-cut` · `rail-angle` 이어 쓰기 없앰, 조립 아님) · skillry-lnkiai 비트11 → 12
- 장면9 · 판매 중 자산 내려앉음 · asset-card (`selling`) `enter` + 마스크 대신 `cut-scale` → 1 · 투명도 0 → 1 · `dur-m` · `ease-out` → `hold-l` → `cam-push` · skillry-lnkiai 비트12 (큰 글자 내려앉음 → 우리 부품)
- 장면9 → 10 · 밀며 밝아짐 · `cam-push` 마지막 `dur-m` 동안 `screen-dissolve` (push는 멈추지 않고 dissolve 안에서 끝남) · skillry-lnkiai 비트12 전환
- 2026-10-25 스냅보드 승인 (사람)
