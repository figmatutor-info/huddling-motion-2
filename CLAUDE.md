# huddling-motion

초보자가 BRIEF와 레퍼런스만 바꿔도 같은 품질의 런칭 영상이 나오게 하는 하네스.
시작: 사용자가 "모션 만들자" → `make-video` 스킬 (`.claude/skills/make-video/SKILL.md`).

## 바뀌는 것 · 고정된 것

| 구분 | 위치 | 누가 고치나 |
|---|---|---|
| 바뀜 | `BRIEF.md` (무엇을 · 몇 초 · 레퍼런스 이름) | 사람 |
| 바뀜 | `references/<이름>/` (원본 영상 · 프레임 · `notes.md`) | 사람 · art-director(`notes.md`만) |
| 고정 | `docs/design.md` 색 · 글자 · `docs/motion.md` 움직임 · `docs/video.md` 영상 화면 규칙 | 사람만 (승인 후) |
| 고정 | `src/screens` · `src/parts` · `src/assets` | 사람만 |
| 결과 | `work/<BRIEF 이름>/` 장면표 · 스냅보드 · 영상 · 판정 기록 | 에이전트 |

## 규칙

1. 값은 docs에서만. 색 · 글자 · 크기 · 프레임 수 · 이징 · 움직임 이름은 docs 세 문서에 있는 것만 쓴다. 장면에서는 이름으로 부른다 (motion.md 머리말 · 2장 참고).
2. UI는 src에서만. 화면 · 부품 · 로고 · 문구를 새로 그리지 않는다.
3. 에이전트는 `docs/` · `src/`를 고치지 않는다. 필요한 움직임은 motion.md 3장 "새 후보" 형식으로 제안만 하고, 사람이 승인해 docs에 들어간 뒤에 쓴다.
4. 레퍼런스에서는 타이밍 · 장면 흐름만 가져온다. 가져오지 않는 것은 motion.md 머리말 참고.
5. 에이전트 문서에는 docs 내용을 옮겨 적지 않는다. "motion.md 3장 참고"처럼 어디를 볼지만 적는다.

## 역할 (`.claude/agents/`)

art-director(레퍼런스 정리) → director(장면표) → builder(스냅보드 · 영상) → critic(판정만, 각 단계 뒤).
사람 승인: 장면표 뒤 · 스냅보드 뒤, 두 번.

## 게이트

- 통과 = docs에 없는 값 · 움직임 0, 화면에 없는 UI 0.
- 결과물을 먼저 보여주고 판정은 한 줄.
- 같은 장면 · 같은 항목에서 2번 불합격 → 멈추고 사람에게 묻는다.
