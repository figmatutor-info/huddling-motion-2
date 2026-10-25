---
name: make-video
description: 사용자가 "모션 만들자" · "새 영상 만들자"라고 하면 쓴다. BRIEF와 레퍼런스로 art-director → director → builder 순서로 런칭 영상을 만들고, 단계마다 critic 판정, 장면표 · 스냅보드에서 사람 승인을 받는다.
---

# make-video

규칙 전체는 `CLAUDE.md`. 이 스킬은 순서와 멈출 곳만 정한다. 메인 세션이 진행하고, 각 단계는 해당 에이전트에게 맡긴다.

## 0. 준비
- BRIEF는 영상마다 `work/<이름>/BRIEF.md`. "새 영상 만들자"면 세 가지(무엇을 · 몇 초 · 레퍼런스)를 묻고 새로 쓴다. 이미 말한 것은 다시 묻지 않는다.
  ```
  # BRIEF
  - 이름: <이름>
  - 무엇을:
  - 몇 초:
  - 레퍼런스:
    - <레퍼런스 이름> — 뼈대 (<URL 또는 "직접 넣음">)
    - <레퍼런스 이름> — <역할: 카메라 · 전환 · 글자 배치 등 하나> (<URL>)
  ```
- 레퍼런스는 여러 개 둘 수 있고, 레퍼런스마다 역할 하나. 뼈대는 1개 (비트 시트의 기준)이고 다른 역할을 같이 맡지 않는다. 역할이 안 적혀 있으면 묻고, 답이 없으면 첫 번째가 뼈대.
- 레퍼런스 받기:
  - `references/<레퍼런스 이름>/`가 이미 있으면 그 안의 영상 · 프레임을 그대로 쓴다. 다시 받지 않는다.
  - 영상 페이지(유튜브 등)만 `yt-dlp`로 `references/<레퍼런스 이름>/source.mp4`에 받는다 (`yt-dlp -t mp4 -o references/<레퍼런스 이름>/source.mp4 <URL>`). 같은 폴더 `source.md`에 URL · 받은 날짜를 적는다. `yt-dlp`가 없으면 설치 방법(`brew install yt-dlp` 또는 `pipx install yt-dlp`)을 알려주고 멈춘다.
  - 글로 된 프롬프트 페이지(Remotion prompts · snapcn 등)는 받지 않는다. 읽어서 `source.md`에 URL · 날짜 · 내용 요약(장면 · 카메라 · 전환 · 타이밍)을 정리한다. 페이지 안의 데모 영상도 받지 않는다.
  - URL이 아니고 `references/<레퍼런스 이름>/`도 없으면 멈추고 넣어 달라고 한다.
- `work/<이름>/`와 `log.md`를 만든다.

## 1. 레퍼런스 정리 — art-director
- 결과: `references/<이름>/beat-sheet.md` (옛 `notes.md`가 있어도 beat-sheet.md는 새로 쓴다. notes.md는 지우지 않는다.)
- 새 후보(docs에 없는 숫자가 필요하거나, 대상 부품 · 화면이 없는 것)가 있으면 사용자에게 목록만 보여주고 "docs에 넣을지"를 묻는다. 넣기로 하면 사람이 motion.md를 고친 뒤 진행. 안 넣으면 그 후보 없이 진행.

## 2. 장면표 — 3안 요약 → ✋ 사람 승인 1 (고르기) → 고른 안 상세
- director(summary)가 `scenes-summary.md`에 3안 요약을 쓴다 (안마다 한 줄 요약 · 비트 구성 줄 · 다르게 한 것, 맨 위 `합침:` 줄). 비트는 BRIEF 길이 기준 1.5초 미만이면 이웃과 합친다.
- director는 장면표 전에 motion.md 0장을 먼저 읽는다.
- critic(summary)은 반복(다른 영상과 겹침)만 본다. 불합격인 안만 director가 다시.
- 요약을 critic 줄과 함께 보여주고 하나를 고르게 한다. `decisions.md`에 "고른 안 · 이유"를 적는다.
- director(detail)가 고른 안만 `scenes.md` 상세(표 · `대신:` 칸)를 쓴다 → critic(scenes) 전체 판정.
  - 불합격 → director(detail) 다시 (사유는 log.md에서).
  - 통과 → scenes.md와 critic 줄(경고 "레퍼런스와 비슷할 수 있음"이 있으면 같이)을 보여주고 3으로.
- 셋 다 반려 → 사유를 log.md에 적고 director(summary)만 다시.

## 3. 스냅보드 — builder(snapboard) → critic → ✋ 사람 승인 2
- 통과 → `snapboard.png`(4열 그리드 한 장) 경로와 이미지를 보여주고, critic 한 줄을 붙이고, 승인을 묻는다.
- 반려 → 사유를 log.md에 적고 builder(snapboard)만 다시. 장면 구성 문제면 2로 돌아간다.

## 4. 영상 미리보기 — builder(video) → critic
- builder는 HyperFrames 프로젝트(`video/`)까지만 만든다. mp4로 렌더하지 않는다.
- 통과 → `npx hyperframes preview`로 브라우저에서 열고, 장면별 프레임과 critic 한 줄을 보여준다.
- 수정 요청은 이 미리보기에서 반복한다 (장면 구성이면 2, 컷이면 3으로).

## 5. 렌더 — 사람이 "렌더"라고 할 때만
- builder(render)가 `out.mp4`로 렌더 → critic(video)가 mp4 프레임으로 다시 판정 → 통과하면 경로를 보여주고 끝.

## 게이트 공통
- 판정은 critic만 한다. 보여줄 것 먼저, 판정은 critic의 한 줄을 그대로.
- 불합격마다 `log.md`에 `단계 · 장면N · 항목(값/UI/구성/반영/반복) · 내용 · 회차`를 한 줄 추가.
- **같은 장면 · 같은 항목이 2회째 불합격이면 자동 수정을 멈추고** 사람에게 묻는다:
  1. docs에 넣는다 (사람이 docs를 고친 뒤 이어서)
  2. 빼고 간다 (그 요소 없이 다시)
