# GitHub Chat Short Handoff Prompt

목적: 다른 GitHub 채팅창에 짧게 붙여넣어, 기존 저장소 규칙을 덮지 않고 영상 분석/소설/분경 스타일 기준을 보조 레이어로 붙이게 한다.

## 1. 짧은 전달문

아래를 GitHub 채팅창에 그대로 보낸다.

```text
이 저장소의 기존 계약/규제/세계관/캐릭터/분경/프롬프트 규칙을 먼저 확인해.

다른 Codex 채팅에서 만든 영상 스타일 분석/소설-분경 기준 파일은 기존 규칙을 대체하지 말고,
감성, 초반 3초 훅, 대사 리듬, 캐릭터 행동, 다음화 유도, AI 영상화 기준을 보강하는 보조 스타일 레이어로만 추가해.

특히 참고 영상 분석은 세계관/캐릭터/관계/말투보다 우선하면 안 돼.
캐릭터 카드와 세계관이 항상 위이고, 참고 영상은 연출 문법만 참고해야 해.

먼저 기존 파일과 충돌표를 만들고,
그다음 AGENTS.md와 docs/production_bible/00_read_order.md 초안을 만들어줘.

update_candidates는 바로 공식 규칙으로 승격하지 말고,
사용자 확인 후 production_bible에 반영하는 구조로 만들어줘.
```

## 2. 같이 전달할 로컬 파일 위치

GitHub 채팅창에는 아래 파일 경로도 같이 준다.

```text
C:\Users\user\Documents\Codex\2026-06-26\use-imagegen-to-make-or-edit\outputs\story-production-kit\05_handoff_prompt_for_github_chat.md
C:\Users\user\Documents\Codex\2026-06-26\use-imagegen-to-make-or-edit\outputs\story-production-kit\23_github_anchor_and_self_update_protocol.md
C:\Users\user\Documents\Codex\2026-06-26\use-imagegen-to-make-or-edit\outputs\story-production-kit\24_dialogue_freshness_and_non_template_rules.md
C:\Users\user\Documents\Codex\2026-06-26\use-imagegen-to-make-or-edit\outputs\story-production-kit\25_dialogue_clarity_and_global_quality_gate.md
C:\Users\user\Documents\Codex\2026-06-26\use-imagegen-to-make-or-edit\outputs\story-production-kit\26_canon_character_priority_over_reference_video.md
C:\Users\user\Documents\Codex\2026-06-26\use-imagegen-to-make-or-edit\outputs\story-production-kit\27_novel_ai_short_drama_gold_standard.md
```

## 3. GitHub 쪽에 요청할 작업

```text
1. 기존 계약/규제/세계관/캐릭터 설정 확인
2. 기존 분경/프롬프트 규칙 확인
3. 위 로컬 스타일 기준과 충돌하는 부분 표로 정리
4. 덮어쓰면 안 되는 규칙 표시
5. 추가 가능한 보조 스타일 레이어 표시
6. AGENTS.md 초안 작성
7. docs/production_bible/00_read_order.md 초안 작성
8. docs/production_bible/self_update_protocol.md 초안 작성
9. 21화 작업용 read order에 캐릭터/세계관 우선순위 반영
```

## 4. 반드시 지킬 우선순위

```text
1. 계약/규제/금지 규칙
2. 세계관
3. 캐릭터 카드
4. 인물 관계와 기존 회차 사건
5. 장소/소품 설정
6. 대사/말투 규칙
7. 스토리 연속성
8. 참고 영상 분석
9. 소설/분경/영상/CapCut 기술 규칙
```

## 5. 절대 금지

```text
기존 세계관을 참고 영상 스타일에 맞춰 바꾸기
캐릭터 성격을 영상 샘플 캐릭터처럼 바꾸기
대사를 무조건 짧게 자르기
참고 영상 분석을 공식 캐릭터/세계관보다 위에 두기
update_candidates를 사용자 확인 없이 production_bible로 승격하기
```
