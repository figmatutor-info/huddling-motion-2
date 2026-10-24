---
name: make-video
description: 사용자가 "모션 만들자"라고 하면 쓴다. BRIEF와 레퍼런스로 art-director → director → builder 순서로 런칭 영상을 만들고, 단계마다 critic 판정, 장면표 · 스냅보드에서 사람 승인을 받는다.
---

# make-video

규칙 전체는 `CLAUDE.md`. 이 스킬은 순서와 멈출 곳만 정한다. 메인 세션이 진행하고, 각 단계는 해당 에이전트에게 맡긴다.

## 0. 준비
- `BRIEF.md`가 없으면 세 가지만 묻고 만든다: 무엇을 · 몇 초 · 레퍼런스 이름.
- `references/<레퍼런스 이름>/`가 없으면 멈추고 넣어 달라고 한다.
- `work/<BRIEF 이름>/`와 `log.md`를 만든다.

## 1. 레퍼런스 정리 — art-director
- 결과: `references/<이름>/notes.md`
- 새 후보가 있으면 사용자에게 목록만 보여주고 "docs에 넣을지"를 묻는다. 넣기로 하면 사람이 motion.md를 고친 뒤 진행. 안 넣으면 그 후보 없이 진행.

## 2. 장면표 — director → critic → ✋ 사람 승인 1
- critic 불합격 → director 다시 (사유는 log.md에서)
- critic 통과 → scenes.md 표를 보여주고, critic 한 줄을 붙이고, 승인을 묻는다.
- 반려 → 사유를 log.md에 적고 director만 다시.

## 3. 스냅보드 — builder(snapboard) → critic → ✋ 사람 승인 2
- 통과 → `snap/` 이미지를 보여주고, critic 한 줄을 붙이고, 승인을 묻는다.
- 반려 → 사유를 log.md에 적고 builder(snapboard)만 다시. 장면 구성 문제면 2로 돌아간다.

## 4. 영상 — builder(video) → critic
- 통과 → `out.mp4` 경로와 장면별 프레임을 보여주고 끝.

## 게이트 공통
- 판정은 critic만 한다. 보여줄 것 먼저, 판정은 critic의 한 줄을 그대로.
- 불합격마다 `log.md`에 `단계 · 장면N · 항목(값/UI) · 내용 · 회차`를 한 줄 추가.
- **같은 장면 · 같은 항목이 2회째 불합격이면 자동 수정을 멈추고** 사람에게 묻는다:
  1. docs에 넣는다 (사람이 docs를 고친 뒤 이어서)
  2. 빼고 간다 (그 요소 없이 다시)
