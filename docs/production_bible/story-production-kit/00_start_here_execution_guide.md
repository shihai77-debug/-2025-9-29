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
outputs/story-production-kit/jimeng_dialogue_voice_prompt_reference.md
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
12. 대사 규칙 확인
13. 질질 끌림 방지 체크
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
참고 영상 분석 기준과 질질 끌림 방지 규칙도 적용해줘.
```

영상 프롬프트로 넘어갈 때:

```text
이 분경을 영상 생성 프롬프트로 바꿔줘.
캐릭터 고정, 장소 연속성, 소품 공개 타이밍, 금지사항을 포함하고,
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
7. 분할 이미지 프롬프트
8. 영상 생성 프롬프트
9. 저해상도 테스트 영상
10. CapCut 타임라인 표
11. 편집/재생성 판단
12. 최종본
13. 리뷰 문서 작성
14. 업데이트 후보 기록
```

## 5. 절대 바로 하면 안 되는 것

```text
세계관 안 읽고 소설 쓰기
캐릭터 카드 안 보고 대사 쓰기
이전 화 마지막 대사 무시하기
대사를 무조건 짧게만 만들기
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
대사가 캐릭터답고 알아듣기 쉽다.
대사 안에 감정과 정보가 같이 있다.
10초마다 새 정보/위험/감정 변화가 있다.
마지막 5초에 다음 화를 보고 싶은 질문이 남는다.
분경에서 배우 연기와 카메라가 보인다.
영상 프롬프트에서 금지사항이 명확하다.
CapCut에서 편집할 것과 재생성할 것이 구분된다.
```

## 7. 가장 짧은 시작 문장

바쁘면 이 한 줄만 쓰면 된다.

```text
규칙 먼저 전부 확인하고, 이전 화 마지막 대사에서 바로 이어지는 이번 화 소설부터 시작해줘. 대사/감정/분경/영상/CapCut까지 이어질 구조로 만들어줘.
```
