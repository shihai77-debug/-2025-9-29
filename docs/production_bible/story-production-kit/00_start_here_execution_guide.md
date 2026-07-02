# Start Here Execution Guide

목적: `《棺中檀色》` 소설, 분경, 이미지 프롬프트, 영상 프롬프트, CapCut 편집을 실제로 시작할 때 쓰는 첫 실행 순서다.

핵심:

```text
먼저 세계관/캐릭터/규칙을 확인한다.
그다음 소설을 쓴다.
소설이 통과하면 분경으로 나눈다.
분경이 통과하면 이미지/영상 프롬프트를 만든다.
영상 결과는 CapCut 편집표로 정리한다.
결과를 보고 규칙을 업데이트 후보로만 남긴다.
```

## 1. 사용자가 해야 할 일

처음 시작할 때 사용자는 아래 중 하나만 주면 된다.

```text
이번 화 번호
이전 화 마지막 대사/마지막 행동
이번 화에서 꼭 일어나야 하는 사건
나오면 안 되는 것
마지막에 남길 다음 화 궁금증
```

전부 완벽하게 줄 필요는 없다. 부족한 부분은 Codex가 먼저 세계관/캐릭터/기존 규칙을 읽고 가정안을 만든다.

## 1-A. GitHub 기준 고정

이 작업은 로컬 폴더만 기준으로 삼지 않는다. GitHub 저장소에 아래 구조가 있어야 한다.

```text
AGENTS.md
docs/production_bible/00_read_order.md
docs/production_bible/11_self_update_protocol.md
episodes/epXX/review/
```

Codex는 작업 전 GitHub의 `AGENTS.md`와 `00_read_order.md`를 먼저 읽어야 한다.

자가 갱신은 자동으로 설정을 바꾸는 것이 아니다.

```text
결과 확인 -> 업데이트 후보 기록 -> 사용자 승인 -> production_bible 반영
```

자세한 기준:

```text
outputs/story-production-kit/23_github_anchor_and_self_update_protocol.md
outputs/story-production-kit/24_dialogue_freshness_and_non_template_rules.md
outputs/story-production-kit/25_dialogue_clarity_and_global_quality_gate.md
outputs/story-production-kit/26_canon_character_priority_over_reference_video.md
outputs/story-production-kit/27_novel_ai_short_drama_gold_standard.md
outputs/story-production-kit/29_story_density_no_drag_execution_gate.md
outputs/story-production-kit/30_bad_example_quarantine_and_style_do_not_copy.md
outputs/story-production-kit/31_creative_preflight_audience_story_gate.md
outputs/story-production-kit/32_director_actor_camera_storyboard_execution_gate.md
outputs/story-production-kit/33_cultural_aesthetic_sensibility_gate.md
outputs/story-production-kit/34_lu_protagonist_voice_scene_leadership_gate.md
outputs/story-production-kit/35_dialogue_stage_necessity_gate.md
outputs/story-production-kit/36_color_script_reference_image_gate.md
outputs/story-production-kit/37_colored_background_prop_split_gate.md
outputs/story-production-kit/38_reference_prompt_rebuild_camera_video_gate.md
outputs/story-production-kit/39_expert_video_prompt_method_extraction.md
outputs/story-production-kit/40_video_prompt_scene_input_card.md
outputs/story-production-kit/41_max_quality_image_dialogue_voice_and_legacy_cleanup.md
outputs/story-production-kit/42_blocking_coordinate_character_position_gate.md
outputs/story-production-kit/jimeng_dialogue_voice_prompt_reference.md
```

## Color Script Gate

Before final storyboard splitting, storyboard reference board generation, clean
keyframe prompting, video prompting, or CapCut planning, create or confirm the
approved color script.

Required order:

```text
1. Read the actual 분진 / shot sequence source.
2. Identify the episode theme and emotional temperature.
3. Create the color script card.
4. Check whether the palette fits the theme and source.
5. Create one approved color reference image.
6. Use that image as the color / lighting / atmosphere reference for later video work.
7. Do not let later split storyboard or video prompts deviate from the approved color script.
```

No approved color script means do not proceed to final split storyboard, image
prompt, or video prompt. See
`docs/production_bible/story-production-kit/36_color_script_reference_image_gate.md`.

Canonical path:

```text
docs/production_bible/story-production-kit/36_color_script_reference_image_gate.md
```

## Colored Background / Prop Split Gate

After the color script is approved, decide how to create background and prop
reference images before making final split storyboard or video prompts.

Required order:

```text
1. Read the full 분진 / shot sequence source.
2. Decide whether the location needs MASTER BACKGROUND, ANGLE SET, PROP INSERT SET, or HYBRID.
3. Create colored background / prop reference prompts using the approved color script.
4. Do not include characters in split reference images by default.
5. Keep character movement, acting, and position in the video prompt.
6. Use approved BG / PROP references to keep video prompts in the same space and color.
```

Canonical path:

```text
docs/production_bible/story-production-kit/37_colored_background_prop_split_gate.md
```

## Reference Prompt Rebuild Camera / Video Gate

When the user provides a high-quality outside video prompt, director prompt, or
platform prompt, do not keep using the old camera / video shooting method as the
final authority. Treat old camera and video prompt notes as legacy support only,
then rebuild the active method from the new reference.

Required order:

```text
1. Read the full outside reference prompt or source provided by the user.
2. Separate content from method.
3. Reject outside story, characters, dialogue, worldview, palette, and scene content.
4. Extract only reusable method: prompt structure, camera grammar, motion control, BG / PROP control, color continuity, and platform stability wording.
5. Rebuild our camera / video prompt method from the actual 분진, approved color script, approved BG / PROP references, canon character / worldview files, and platform rules.
6. Mark the rebuilt method as candidate until the user approves it.
```

Old camera / video shooting notes may explain past failures, but they must not
override the new reference-prompt-derived method after this gate is active. See
`docs/production_bible/story-production-kit/38_reference_prompt_rebuild_camera_video_gate.md`.

Canonical path:

```text
docs/production_bible/story-production-kit/38_reference_prompt_rebuild_camera_video_gate.md
```

## Expert Video Prompt Method Gate

For final video prompts, use the user-approved expert prompt method extraction
after the color and BG / PROP gates.

Required video prompt layer order:

```text
1. STYLE LOCK
2. REFERENCE LOCK
3. SOURCE LOCK
4. SHOT DESIGN
5. ACTION FLOW
6. ACTING / VOICE
7. PROP / REVEAL
8. SOUND
9. CONTINUITY
10. FORBIDDEN
11. PLATFORM
```

This method improves prompt structure, camera grammar, actor behavior, sound
layering, color stability, and failure prevention. It does not allow copying
outside story, characters, dialogue, worldview, palette, or scene content. See
`docs/production_bible/story-production-kit/39_expert_video_prompt_method_extraction.md`.

Canonical path:

```text
docs/production_bible/story-production-kit/39_expert_video_prompt_method_extraction.md
```

## Video Prompt Scene Input Card Gate

Before final video prompts, run a scene input audit and actively request missing
materials if they affect output quality.

Required check:

```text
Episode / CUT number
source file or pasted source
previous CUT ending
next CUT handoff
must happen / must not happen
characters present
location
exact dialogue source
visible props / hidden props
approved color reference
BG / PROP split status
platform target
duration target
```

If a needed item is missing, ask the user for it. If the user wants to proceed
without it, mark the field as ASSUMED / NEEDS USER APPROVAL. See
`docs/production_bible/story-production-kit/40_video_prompt_scene_input_card.md`.

Canonical path:

```text
docs/production_bible/story-production-kit/40_video_prompt_scene_input_card.md
```

## Max Quality Image / Auto Voice / Legacy Cleanup Gate

Before production image generation or final video prompts, apply the 41 gate.

Required behavior:

```text
1. ChatGPT / image generation reference images use the maximum available quality.
2. High image quality must not redesign canon, character, prop, location, or approved color logic.
3. If 分镜 has dialogue but lacks AI-readable voice direction, create AUTO VOICE DIRECTION.
4. AUTO VOICE DIRECTION may add tone / speed / pause / emphasis / listener reaction / sound mix only.
5. It must not rewrite, shorten, move, or replace dialogue.
6. Old unused camera / video materials are not deleted until 3 approved production cycles or explicit user approval.
7. Never delete character references / 三面图, worldbuilding, source, confirmed 分镜, approved references, or contract files.
```

Canonical path:

```text
docs/production_bible/story-production-kit/41_max_quality_image_dialogue_voice_and_legacy_cleanup.md
```

## Blocking Coordinate / Character Position Gate

Before split image selection or final video prompts, confirm or create the
filming-space blocking map.

Required behavior:

```text
1. Read the full 分镜 / shot sequence source before creating coordinates.
2. If coordinates already exist, preserve them as highest filming-space source.
3. If coordinates are missing, create AUTO BLOCKING MAP.
4. Mark inferred positions as ASSUMED / NEEDS USER APPROVAL.
5. Create a CUT Blocking Card for each final video prompt.
6. Decide selected images after the full scene geography is understood.
7. Label each selected image by what it locks: color / location / prop / angle / character / first frame / last frame.
8. Put selected images into the final video prompt as REFERENCE LOCK.
```

Coordinates help AI understand space; they must not change source story,
dialogue, character identity, relationship logic, or reveal timing.

Canonical path:

```text
docs/production_bible/story-production-kit/42_blocking_coordinate_character_position_gate.md
```

## 2. Codex가 매번 먼저 해야 할 일

작업 전 자동 확인 순서:

```text
1. 계약/규제/금지 규칙 확인
2. 세계관 파일 확인
3. 캐릭터 설정 확인
4. 陆沉舟가 말없는 쿨남이 아니라 장면을 끌고 가는 주인공인지 확인
5. 장소/소품 설정 확인
6. 기존 분경/프롬프트 규칙 확인
7. 참고 영상 분석 규칙 확인
8. 이전 화 마지막 대사와 현재 화 첫 장면 연결 확인
9. 이번 화의 3초 후킹 확인
10. 대사 전 현장 위험/말할 필연성 확인
11. Jimeng 대사 음성/연기 프롬프트 기준 확인
12. 색도 / approved color reference image 확인
13. 배경 / 소품 분할 방식 확인
14. 좌표 / 인물 위치 / CUT Blocking Card 확인
15. 새 참고 프롬 기반 카메라 / 영상 방식 재구축 여부 확인
16. 39번 고수 영상 프롬 레이어 순서 적용 여부 확인
17. 40번 장면 입력 카드 / 부족 참고자료 요청 여부 확인
18. 41번 최대화질 이미지 / 자동 대사 음성 / 레거시 정리 기준 확인
19. 42번 이미지 핸드오프 / REFERENCE LOCK 확인
20. 대사 규칙 확인
21. 질질 끌림 방지 체크
```

이 확인 없이 바로 소설이나 분경을 쓰면 안 된다.

## 3. 실제 실행 명령문

새 화를 시작할 때 이렇게 말하면 된다.

```text
세계관/캐릭터/제작 규칙 먼저 확인하고,
이번 화 소설부터 만들어줘.
이전 화 마지막 대사와 바로 이어지게 하고,
대사는 캐릭터 성격+감정+스토리 정보를 같이 살려줘.
분경/영상 프롬프트/CapCut 편집표까지 이어갈 수 있게 써줘.
작업 전 자가진단도 먼저 해줘.
```

분경으로 넘어갈 때:

```text
이 소설을 기준으로 분경 만들어줘.
CUT마다 화면, 배우 연기, 카메라, 대사, 소품, 금지사항, 다음 컷 연결까지 넣어줘.
가능하면 좌표/인물 위치/동선 기준도 같이 만들어줘.
좌표가 없으면 전체 분진을 읽고 AUTO BLOCKING MAP으로 자동 보강해줘.
대사 읽는 방식이 없으면 AUTO VOICE DIRECTION으로 자동 보강하되 원문 대사는 바꾸지 마.
참고 영상 분석 기준과 질질 끌림 방지 규칙도 적용해줘.
```

영상 프롬프트로 넘어갈 때:

```text
이 분경을 영상 생성 프롬프트로 바꿔줘.
먼저 전체 분진을 읽고 좌표/인물 위치/동선이 있는지 확인해줘. 없으면 AUTO BLOCKING MAP과 CUT Blocking Card를 만들어줘.
먼저 40번 장면 입력 카드로 부족한 참고자료를 점검하고, 필요한 자료가 있으면 적극적으로 요구해줘.
이미지 생성이 필요한 경우 ChatGPT/imagegen에서 가능한 최대 화질 기준으로 만들어줘.
분할 이미지나 참고이미지가 선정되면 각 이미지가 무엇을 잠그는지 확정하고, 영상 프롬의 REFERENCE LOCK에 공유해줘.
대사 읽는 방식이 분진에 없으면 AUTO VOICE DIRECTION으로 자동 생성해줘. 원문 대사는 절대 바꾸지 마.
그다음 39번 고수 영상 프롬 레이어 순서대로 STYLE LOCK / REFERENCE LOCK / SOURCE LOCK / SHOT DESIGN / ACTION FLOW / ACTING / SOUND / CONTINUITY / FORBIDDEN / PLATFORM을 나눠줘.
캐릭터 고정, 색도 고정, 배경/소품 연속성, 소품 공개 타이밍, 금지사항을 포함하고,
자료나 반전이 너무 일찍 보이지 않게 해줘.
```

CapCut으로 넘어갈 때:

```text
이 영상 결과를 CapCut 타임라인 표로 만들어줘.
CUT별 시간, 화면, 대사 자막, 효과음, 음악, 전환, 편집 메모, 재생성 여부를 나눠줘.
편집으로 해결할 문제와 다시 생성해야 할 문제를 구분해줘.
```

## 4. 한 화 제작 흐름

권장 순서:

```text
1. Episode Input Card 작성
2. 자가진단
3. 소설 초안
4. 스토리/대사/캐릭터 검사
5. 소설 수정본
6. CUT 분경
7. 좌표 / AUTO BLOCKING MAP / CUT Blocking Card 확인
8. 색도 카드 + approved color reference image
9. 최대화질 이미지 생성 기준 확인
10. 배경 / 소품 분할 판단
11. Reference Image Handoff 확정
12. 새 참고 프롬 방식 추출 / 카메라-영상 문법 재구축
13. 39번 고수 영상 프롬 레이어 적용 체크
14. 40번 장면 입력 카드 / 부족 자료 요청 체크
15. 41번 AUTO VOICE DIRECTION / 레거시 정리 기준 체크
16. 42번 REFERENCE LOCK 공유 체크
17. 분할 이미지 프롬프트
18. 영상 생성 프롬프트
19. 저해상도 테스트 영상
20. CapCut 타임라인 표
21. 편집/재생성 판단
22. 최종본
23. 리뷰 문서 작성
24. 업데이트 후보 기록
```

## 5. 절대 바로 하면 안 되는 것

```text
세계관 안 읽고 소설 쓰기
캐릭터 카드 안 보고 대사 쓰기
이전 화 마지막 대사 무시하기
대사를 무조건 짧게만 만들기
좌표/인물 위치 확인 없이 영상 프롬 만들기
분진 전체를 읽지 않고 AUTO BLOCKING MAP 만들기
좌표를 핑계로 인물 위치나 사건 순서 바꾸기
색도 기준 없이 분할 이미지 만들기
최대화질 기준 없이 공식 참고 이미지 만들기
이미지 선정 후 REFERENCE LOCK 없이 영상 프롬 만들기
색도 기준 없이 영상 프롬프트 만들기
분경 전체를 읽지 않고 배경을 임의 분할하기
분경 대사를 읽는 방식 없이 최종 영상 프롬 만들기
AUTO VOICE DIRECTION을 핑계로 대사 원문 바꾸기
고수 참고 프롬의 내용/인물/스토리/색감을 베끼기
고수 참고 프롬의 구조를 빼고 분위기만 흉내내기
부족한 참고자료를 확인하지 않고 최종 영상 프롬 만들기
옛 카메라/영상 방식을 새 참고 프롬보다 우선하기
3화 검증/사용자 승인 없이 옛 자료 삭제하기
분경 전에 영상 프롬프트부터 만들기
영상 실패를 전부 재생성으로 해결하기
참고 영상 스타일을 분위기만 베끼기
CapCut에서 사건 순서 바꾸기
업데이트 후보를 검증 없이 공식 규칙으로 넣기
```

## 6. 성공 기준

한 화가 제대로 된 상태:

```text
처음 3초에 질문이 생긴다.
이전 화 마지막 감정과 바로 이어진다.
인물이 왜 거기 있는지 분명하다.
좌표/인물 위치/동선이 촬영 가능하게 정리되어 있다.
대사가 캐릭터답고 알아듣기 쉽다.
대사 안에 감정과 정보가 같이 있다.
대사 읽는 방식이 AI가 알아듣게 분리되어 있다.
10초마다 새 정보/위험/감정 변화가 있다.
마지막 5초에 다음 화를 보고 싶은 질문이 남는다.
색도 기준이 장면 주제와 감정에 맞다.
분할 이미지가 색도 기준에서 벗어나지 않는다.
공식 참고 이미지는 가능한 최대 화질로 만든다.
분할 배경/소품 이미지가 영상의 실제 카메라 각도와 이어진다.
선정된 이미지가 무엇을 잠그는지 REFERENCE LOCK에 공유되어 있다.
새 참고 프롬에서 배운 카메라/영상 문법이 우리 분진에 맞게 재구축되어 있다.
영상 프롬프트가 39번 레이어 순서를 따른다.
40번 입력 카드로 부족 참고자료를 확인했다.
41번 기준으로 AUTO VOICE DIRECTION과 레거시 정리 기준을 확인했다.
42번 기준으로 AUTO BLOCKING MAP / CUT Blocking Card / Reference Image Handoff를 확인했다.
분경에서 배우 연기와 카메라가 보인다.
영상 프롬프트에서 금지사항이 명확하다.
CapCut에서 편집할 것과 재생성할 것이 구분된다.
```

## 7. 가장 짧은 시작 문장

바쁘면 이 한 줄만 쓰면 된다.

```text
규칙 먼저 전부 확인하고, 이전 화 마지막 대사에서 바로 이어지는 이번 화 소설부터 시작해줘. 대사/감정/분경/영상/CapCut까지 이어질 구조로 만들어줘.
```
