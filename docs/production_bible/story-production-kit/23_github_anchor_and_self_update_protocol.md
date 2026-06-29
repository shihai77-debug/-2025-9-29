# GitHub Anchor And Self Update Protocol

목적: `《棺中檀色》` 제작 규칙이 로컬 메모로 흩어지지 않고, GitHub 저장소 안에서 항상 먼저 읽히고 계속 개선되게 만드는 기준이다.

핵심:

```text
GitHub는 저장 창고가 아니라 제작 기준의 본체다.
Codex/local은 작업장과 백업이다.
모든 소설/분경/프롬프트/CapCut 판단은 GitHub의 read_order를 먼저 읽고 시작한다.
```

## 1. GitHub에 반드시 박아야 하는 3개 축

### A. Root Anchor

저장소 루트에 아래 파일을 둔다.

```text
AGENTS.md
```

역할:

```text
이 저장소에서 작업하는 Codex/AI/작업자는 반드시 production_bible/read_order를 먼저 읽는다.
세계관/캐릭터/계약 규칙보다 새 아이디어를 우선하지 않는다.
자가 업데이트는 검증된 후보만 반영한다.
```

### B. Production Bible

공식 제작 규칙은 아래 폴더에 둔다.

```text
docs/production_bible/
```

필수 파일:

```text
00_read_order.md
01_contract_rules.md
02_worldview.md
03_character_cards.md
04_location_cards.md
05_prop_cards.md
06_storyboard_split_rules.md
07_prompt_rules.md
08_reference_video_style_bible.md
09_story_continuity_and_dialogue_rules.md
10_director_actor_camera_simulation_workflow.md
11_self_update_protocol.md
12_cut_editing_authority_rules.md
13_capcut_timeline_export_rules.md
```

### C. Episode Review Loop

각 화마다 결과를 저장하는 폴더를 둔다.

```text
episodes/ep21/
  novel/
  storyboard/
  prompts/
  capcut/
  review/
    ep21_story_logic_check.md
    ep21_prompt_result_review.md
    ep21_update_candidates.md
```

역할:

```text
한 화가 끝날 때마다 좋았던 점/실패한 점/다음 화에 적용할 후보를 남긴다.
후보는 바로 공식 규칙이 아니다.
검증 후에만 production_bible로 승격한다.
```

## 2. AGENTS.md에 넣을 핵심 문장

GitHub 저장소 루트의 `AGENTS.md`에는 아래 내용을 넣는다.

```markdown
# Project Operating Rules

This repository is the source of truth for 《棺中檀色》 production.

Before writing or editing any novel, storyboard, image prompt, video prompt, or CapCut timeline, always read:

1. `docs/production_bible/00_read_order.md`
2. contract/regulation/prohibition rules
3. worldview
4. character cards
5. location and prop cards
6. storyboard and prompt rules
7. reference video style bible
8. self update protocol

Never start from a blank prompt.
Never change canon, character voice, relationship, reveal order, or contract rules without explicit approval.

Each episode must preserve direct continuity from the previous episode's final line/action/sound/prop.

Dialogue must carry character personality, current emotion, and story information together.

After each episode or generated result, create review files:

- `story_logic_check`
- `prompt_result_review`
- `update_candidates`

Only verified update candidates may be promoted into `docs/production_bible/`.
```

## 3. 00_read_order.md에 반드시 들어갈 순서

`docs/production_bible/00_read_order.md`는 아래 순서를 가진다.

```markdown
# Read Order

Before any production work, read in this order:

1. Contract, regulation, and absolute prohibition rules
2. Worldview
3. Character cards
4. Location cards
5. Prop cards
6. Existing episode continuity log
7. Story continuity and dialogue rules
8. Canon character priority over reference video
9. Reference video style bible
10. Novel AI short drama gold standard
11. Creative preflight audience story gate
12. Story density no-drag execution gate
13. Bad example quarantine and style do-not-copy
14. Director actor camera storyboard execution gate
15. Director/actor/camera simulation workflow
16. Three second hook and character entry rules
17. Anti-drag pacing rules
18. Dialogue freshness and non-template rules
19. Dialogue clarity and global quality gate
20. Storyboard split rules
21. Image/video prompt rules
22. CUT editing authority rules
23. CapCut timeline export rules
24. Self update protocol

If any rule conflicts, higher priority files win.
Do not overwrite canon from lower priority notes.
Ask for approval before changing worldview, character identity, relationship, or contract rules.
```

## 4. 자가 갱신 방식

자가 갱신은 자동 수정이 아니다.

```text
자가 갱신 = 결과를 보고, 반복되는 성공/실패를 증거로 남기고, 검증된 규칙만 공식화하는 것.
```

반드시 3단계로 한다.

```text
1. Result Review
   실제 소설/분경/영상/편집 결과를 본다.

2. Update Candidate
   어떤 규칙을 추가/수정하면 좋은지 후보로만 적는다.

3. Promotion
   사용자 확인 후 production_bible에 반영한다.
```

## 5. 자동으로 바꾸면 안 되는 것

아래는 update_candidates에 있어도 자동 승격 금지다.

```text
세계관 핵심 규칙
캐릭터 성격/나이/외형/말투
인물 관계
계약/규제/금지 규칙
이미 확정된 회차 사건
주요 소품의 공개 순서
죽음/생존/정체 공개 같은 큰 반전
```

## 6. 자동으로 개선해도 되는 것

아래는 검증 후 production_bible에 반영 가능하다.

```text
3초 후킹 방식
CUT 길이 기준
대사 길이와 호흡 기준
분경 표 양식
영상 프롬프트 금지 문장
CapCut 편집표 양식
자막 타이밍 기준
재생성 판단 기준
반복 실패 blacklist
```

## 7. 21화부터 적용할 기준

21화는 새 출발이 아니다.

```text
20화 마지막 문/숨소리/封气 판단에서 바로 이어진다.
첫 3초는 老宅 안쪽 반응으로 질문을 만든다.
陆沉舟는 감정을 설명하지 않고 판단으로 주인공성을 보여준다.
黑七는 감각으로 먼저 이상함을 잡는다.
檀缺는 짧게 찌르는 관찰로 균형을 잡는다.
沈泊川는 현실적인 불안과 질문으로 시청자 몰입을 맡는다.
```

21화에서 피해야 할 것:

```text
문 앞에서 설명만 길게 하기
자료를 다시 길게 읽기
인물들이 서 있기만 하기
대사를 무조건 짧게 잘라 감정이 사라지기
20화 마지막 긴장을 새 장면으로 끊어버리기
```

## 8. GitHub에 올릴 때 우선순위

먼저 넣을 파일:

```text
1. AGENTS.md
2. docs/production_bible/00_read_order.md
3. docs/production_bible/11_self_update_protocol.md
4. docs/production_bible/09_story_continuity_and_dialogue_rules.md
5. docs/production_bible/10_director_actor_camera_simulation_workflow.md
6. docs/production_bible/12_cut_editing_authority_rules.md
7. docs/production_bible/13_capcut_timeline_export_rules.md
```

그다음 넣을 파일:

```text
episodes/ep21/review/ep21_story_logic_check.md
episodes/ep21/review/ep21_update_candidates.md
metrics/hook_ab_test_results.md
metrics/shortform_episode_metrics.md
```

## 9. 다른 채팅창에 보낼 문장

다른 GitHub 작업 채팅창에는 아래처럼 전달한다.

```text
이 저장소는 《棺中檀色》 제작 기준 저장소입니다.
작업 전 반드시 `AGENTS.md`와 `docs/production_bible/00_read_order.md`를 먼저 읽어주세요.
소설/분경/영상 프롬프트/CapCut 편집표는 세계관, 캐릭터 카드, 대사 규칙, 3초 후킹, 질질 끌림 방지, 자가 업데이트 프로토콜을 따른 뒤 작성해야 합니다.
update_candidates는 바로 공식 규칙으로 승격하지 말고, 사용자 확인 후 production_bible에 반영해주세요.
현재 작업 대상은 21화이며, 20화 마지막 老宅 문 앞 긴장에서 바로 이어져야 합니다.
```

## 10. Codex에게 GitHub 반영을 요청하는 문장

저장소 이름을 알고 있을 때 이렇게 말한다.

```text
GitHub 저장소 owner/repo는 [여기에 저장소명]이야.
현재 story-production-kit의 핵심 규칙을 GitHub에 넣어줘.
먼저 AGENTS.md, docs/production_bible/00_read_order.md, self_update_protocol부터 만들고,
기존 파일이 있으면 덮어쓰기 전에 충돌을 비교해서 알려줘.
```
