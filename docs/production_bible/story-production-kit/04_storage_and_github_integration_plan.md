# Storage And GitHub Integration Plan

목적: 로컬 Codex에서 만든 영상 분석/스타일 기준을 기존 GitHub 저장소의 소설, 분경, 영상 프롬프트 제작 흐름과 충돌 없이 연결한다.

## 1. 최종 권장 구조

GitHub 저장소를 원본 기준으로 둔다.

```text
GitHub repo = 원본/공식 제작 기준
Codex local workspace = 분석, 초안, 테스트, 임시 산출물
```

이유:

```text
1. 기존 소설/분경 작업이 클라우드 또는 GitHub 기준으로 진행됨
2. 여러 채팅창에서 작업해도 같은 기준을 읽을 수 있음
3. 나중에 다른 회차를 만들 때 규칙 유실이 적음
4. 로컬 파일만 두면 새 Codex 세션에서 기준을 놓칠 수 있음
```

## 2. GitHub에 넣을 파일 분류

지금 만든 파일은 GitHub 저장소에 넣는 것이 좋다. 단, 위치와 역할을 분리해야 한다.

추천 구조:

```text
docs/
  production_bible/
    00_read_order.md
    01_contract_rules.md
    02_worldview.md
    03_character_cards.md
    04_location_cards.md
    05_prop_cards.md
    06_style_reference_ai_shortform_video.md
    07_novel_before_storyboard_template.md
    08_novel_to_storyboard_workflow.md

episodes/
  ep20/
    novel/
    storyboard/
    prompts/
    review/
```

## 3. 파일별 권장 역할

### 06_style_reference_ai_shortform_video.md

현재 파일:

```text
outputs/story-production-kit/01_reference_video_style_bible.md
```

GitHub 권장 위치:

```text
docs/production_bible/06_style_reference_ai_shortform_video.md
```

역할:

```text
좋아하는 영상 기준
감성 방식
초반 훅 방식
다음화 유도 방식
대사 리듬
```

주의:

```text
계약/규제/절대 규칙보다 우선하지 않는다.
기존 분경 분할 규칙을 덮어쓰지 않는다.
```

### 07_novel_before_storyboard_template.md

현재 파일:

```text
outputs/story-production-kit/02_novel_before_storyboard_template.md
```

GitHub 권장 위치:

```text
docs/production_bible/07_novel_before_storyboard_template.md
```

역할:

```text
분경 전 소설/장면 원문 작성 양식
대사 보존
소품 공개 시점
장면 질문 설계
```

### 08_novel_to_storyboard_workflow.md

현재 파일:

```text
outputs/story-production-kit/03_novel_to_storyboard_workflow.md
```

GitHub 권장 위치:

```text
docs/production_bible/08_novel_to_storyboard_workflow.md
```

역할:

```text
소설 원문을 비트, CUT, 영상 프롬프트로 변환하는 절차
```

## 4. 규칙 우선순위

모든 작업에서 아래 순서를 따른다.

```text
1. 계약/규제/절대 금지 규칙
2. 세계관/캐릭터/장소/소품 카드
3. 기존 분경 분할 규칙
4. 영상 스타일 분석 파일
5. 회차별 지시
6. 개별 프롬프트
```

중요:

```text
영상 스타일 분석은 맛을 정한다.
분경 분할 규칙은 구조를 정한다.
계약/규제 파일은 허용 범위를 정한다.
```

## 5. Codex에 매번 줄 지시문

새 채팅이나 새 Codex 작업에서 아래처럼 지시하면 된다.

```text
GitHub 저장소의 docs/production_bible/00_read_order.md를 먼저 읽고,
그 순서대로 계약/규제, 세계관, 캐릭터 카드, 장소 카드, 소품 카드,
분경 분할 규칙, 스타일 레퍼런스 파일을 적용해.

작업 기준:
1. 계약/규제 파일이 최우선이다.
2. 캐릭터/장소/소품 카드는 변경하지 않는다.
3. 스타일 레퍼런스는 감성, 훅, 대사 리듬, 다음화 유도에만 사용한다.
4. 소설은 분경 전 단계로 먼저 작성한다.
5. 분경은 기존 분할 규칙에 맞춰 작성한다.
6. 영상 프롬프트는 기존 프롬프트 규칙을 우선 유지하고, 필요한 경우 스타일만 보강한다.
```

## 6. 기존 영상 프롬프트를 고칠지 판단 기준

영상 프롬프트는 무조건 고치지 않는다.

고쳐야 하는 경우:

```text
첫 3~5초 훅이 약함
장면 질문이 없음
소품 공개가 너무 빠름
다음화 유도가 없음
감정이 대사로만 설명됨
장면 연결 이유가 약함
캐릭터 위치/소품/장소 연속성이 흔들림
```

그대로 둬도 되는 경우:

```text
캐릭터 고정이 잘 되어 있음
분경 분할이 명확함
영상 프롬프트가 짧고 실행 가능함
소품/장소/대사 충돌이 없음
기존 규제 파일과 충돌하지 않음
```

## 7. 다음 작업 순서

권장 순서:

```text
1. GitHub 저장소의 기존 docs/rules/prompt 관련 파일 확인
2. 현재 story-production-kit 파일과 충돌 검사
3. 충돌 없는 파일만 GitHub에 추가
4. read_order 파일 작성
5. 다음 소설 장면을 이 기준으로 작성
6. 기존 분경/프롬프트 중 고칠 부분만 선택적으로 수정
```

## 8. 핵심 결론

```text
GitHub 저장소를 원본으로 둔다.
Codex 로컬 파일은 초안/분석/작업물로 둔다.
지금 만든 영상 분석은 스타일 레이어로 GitHub에 넣는다.
기존 계약/규제/분경 규칙은 절대 덮어쓰지 않는다.
소설은 이 스타일 기준으로 이어서 쓰되, 분경 전 단계로 별도 저장한다.
```
