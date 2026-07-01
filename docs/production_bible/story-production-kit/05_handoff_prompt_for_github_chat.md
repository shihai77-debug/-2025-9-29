# Handoff Prompt For GitHub Chat

아래 문장을 GitHub 저장소를 다루는 다른 Codex 채팅창에 그대로 전달한다.

```text
이 저장소는 AI 숏폼 드라마 제작용 기준 저장소로 사용한다.

현재 다른 Codex 채팅에서 사용자가 좋아하는 AI 숏폼 영상 3개를 분석했고,
그 분석은 "스타일 레이어"로만 사용해야 한다.

중요 우선순위:
1. 기존 계약/규제/절대 금지 규칙
2. 세계관 설정
3. 캐릭터 설정
4. 장소/소품 설정
5. 기존 분경 분할 규칙
6. 기존 이미지/영상 프롬프트 규칙
7. 새로 추가할 영상 스타일 분석 규칙

절대 하지 말 것:
- 기존 계약/규제 파일을 덮어쓰지 말 것.
- 기존 세계관/캐릭터 설정을 영상 스타일 분석에 맞춰 바꾸지 말 것.
- 기존 분경 분할 규칙을 새 분석으로 교체하지 말 것.
- 영상 프롬프트를 무조건 다시 쓰지 말 것.

해야 할 일:
1. 저장소 안의 기존 세계관 파일을 확인한다.
   관련 브랜치/작업명: codex/create-worldbuilding-markdown-file

2. 저장소 안의 기존 캐릭터 설정 파일을 확인한다.
   관련 브랜치/작업명: codex/create-character-settings-markdown-file-5zxmil

3. 기존 계약/규제/분경/프롬프트 규칙 파일을 찾는다.

4. 아래 새 파일들을 GitHub 저장소에 넣을 위치를 제안한다.
   이 파일들은 기존 규칙을 대체하지 않고 보조 레이어로 추가한다.

   - 06_style_reference_ai_shortform_video.md
   - 07_novel_before_storyboard_template.md
   - 08_novel_to_storyboard_workflow.md

5. 권장 저장 위치:

   docs/production_bible/
     00_read_order.md
     01_contract_rules.md
     02_worldview.md
     03_character_cards.md
     04_location_cards.md
     05_prop_cards.md
     06_storyboard_split_rules.md
     07_prompt_rules.md
     08_style_reference_ai_shortform_video.md
     09_novel_before_storyboard_template.md
     10_novel_to_storyboard_workflow.md

6. 충돌표를 만든다.
   출력 형식:

   - 유지할 기존 규칙
   - 새로 추가해도 되는 스타일 규칙
   - 충돌 가능성이 있는 규칙
   - 이동/이름 변경이 필요한 파일
   - 최종 read_order.md 초안

7. 새 스타일 분석 규칙의 역할은 아래로 제한한다.

   - 초반 3~5초 훅 강화
   - 감성 장면 처리
   - 대사 리듬 보정
   - 다음화 클리프행어 설계
   - 소설에서 분경으로 넘어가기 전 장면 질문 설계

이 분석은 작품 설정을 바꾸는 기준이 아니라,
기존 세계관/캐릭터/분경 규칙 위에 얹는 연출 취향 기준이다.
```

## 현재 채팅에서 만든 로컬 파일

현재 Codex 로컬 작업공간의 파일:

```text
outputs/story-production-kit/01_reference_video_style_bible.md
outputs/story-production-kit/02_novel_before_storyboard_template.md
outputs/story-production-kit/03_novel_to_storyboard_workflow.md
outputs/story-production-kit/04_storage_and_github_integration_plan.md
outputs/story-production-kit/05_handoff_prompt_for_github_chat.md
```

GitHub에 넣을 때 권장 이름:

```text
01_reference_video_style_bible.md
→ 08_style_reference_ai_shortform_video.md

02_novel_before_storyboard_template.md
→ 09_novel_before_storyboard_template.md

03_novel_to_storyboard_workflow.md
→ 10_novel_to_storyboard_workflow.md
```
