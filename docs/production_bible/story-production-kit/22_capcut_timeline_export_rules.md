# CapCut Timeline Export Rules

목적: 소설, 분경, 이미지 생성, 영상 생성 결과를 CapCut에서 바로 편집할 수 있는 타임라인 표로 변환하는 기준을 만든다.

핵심:

```text
CapCut에 넣을 것은 영상 파일만이 아니다.
CUT 순서, 길이, 자막, 효과음, 음악, 전환, 재생성 여부까지 같이 넣어야 한다.
```

## 1. CapCut 작업 순서

권장 순서:

```text
1. 세계관/캐릭터/금지 규칙 확인
2. 에피소드 소설 확정
3. CUT 분할 확정
4. 각 CUT의 영상 생성 프롬프트 확정
5. 저해상도 테스트 영상 생성
6. CapCut 1차 배열
7. 자막/대사 싱크 맞춤
8. 효과음/음악/전환 삽입
9. 흐름이 느린 CUT 트리밍
10. 깨진 CUT만 선별 재생성
11. 본편 편집본 확정
12. 도입부 A/B/C 버전 제작
```

## 2. CapCut 폴더 구조

에피소드별로 아래처럼 정리한다.

```text
ep20_capcut/
  01_video_generated/
  02_images_storyboard/
  03_dialogue_subtitles/
  04_sfx/
  05_music/
  06_project_exports/
  07_regen_needed/
  ep20_timeline_table.md
  ep20_edit_review.md
```

원본 영상과 참고 영상은 GitHub에 올리지 않는다.

```text
GitHub: 규칙/대본/분경/프롬프트/리뷰 문서
Local: 원본 영상/테스트 영상/CapCut 프로젝트/프레임 이미지
```

## 3. 타임라인 표 기본 양식

모든 에피소드는 아래 표로 편집 기준을 만든다.

```markdown
| CUT | Timecode | Duration | Visual | Dialogue/Subtitles | SFX | Music | Transition | Edit Note | Regen? |
|---|---:|---:|---|---|---|---|---|---|---|
| 20-01 | 00:00-00:12 | 12s | Kunlun aftermath, SHEN motorcycle entry | selected lines | distant engine -> close engine | low hold | hard sound bridge | keep LU stillness | No |
```

각 칸 기준:

```text
CUT: 에피소드-CUT 번호
Timecode: CapCut 안 실제 위치
Duration: 최종 길이
Visual: 화면에서 반드시 보여야 하는 것
Dialogue/Subtitles: 최종 자막 또는 대사
SFX: 필요한 효과음
Music: 음악 분위기와 볼륨
Transition: 컷 전환 방식
Edit Note: 편집자가 지켜야 할 의도
Regen?: 재생성 필요 여부
```

## 4. 트랙 구성

CapCut 트랙은 단순하게 고정한다.

```text
V1: 메인 영상
V2: 인서트 컷/반응 컷/이미지 줌
V3: 전환 카드 또는 보조 화면
T1: 중국어 본대사 자막
T2: 짧은 정보 라벨 또는 장소/시간 카드
A1: 대사 원음
A2: 효과음
A3: 배경음악
```

중요:

```text
대사 자막은 T1에만 둔다.
긴 설명 라벨을 화면에 넣지 않는다.
스토리 정보는 대사/소품/반응 컷으로 나눈다.
```

## 5. 자막 기준

대사가 잘 들리고 이해되는 것이 우선이다.

```text
중국어 대사는 원문 유지가 기본.
자막은 대사 의미를 바꾸지 않는다.
한 줄이 너무 길면 자연스러운 호흡에서 줄을 나눈다.
대사 시작보다 자막을 아주 조금 빨리 띄울 수 있다.
대사 종료 후 0.2~0.4초 정도 남겨 읽을 시간을 준다.
감정 대사는 너무 빨리 넘기지 않는다.
```

삭제 금지:

```text
핵심 단서
인물 감정 전환
말투가 살아 있는 농담/비꼼/침묵 후 한마디
다음 화로 이어지는 질문
```

## 6. 효과음 기준

효과음은 사건을 설명하지 않고 감각을 앞당긴다.

좋은 효과음:

```text
멀리서 들어오는 엔진음
문 안쪽의 낮은 숨소리
낡은 철문 미세한 떨림
가방 지퍼가 닫힌 상태로 흔들리는 소리
전화 진동
먼 도시 소음
바람이 없는데 먼지만 움직이는 소리
```

주의:

```text
효과음이 너무 크면 대사가 죽는다.
판타지 효과음을 과하게 넣지 않는다.
공포 장면도 싸구려 점프스케어로 만들지 않는다.
```

## 7. 음악 기준

음악은 감정을 밀지만 대사를 덮지 않는다.

```text
대사 구간: 음악 낮게
정적 구간: 거의 무음 또는 낮은 드론
외부 사건 진입: 리듬 또는 엔진음 중심
조사 구간: 얇은 긴장음
클리프행어 직전: 음악을 줄이고 소리를 선명하게
클리프행어 순간: 짧게 끊거나 낮게 남긴다
```

## 8. 재생성 판단 칸

`Regen?` 칸은 아래 중 하나로 쓴다.

```text
No: 그대로 사용
Edit: CapCut에서 수정 가능
Partial: 특정 인서트/반응 컷만 추가 생성
Regen: 해당 CUT 다시 생성
Hold: 판단 보류, 앞뒤 컷 붙여보고 결정
```

판단 기준:

```text
얼굴/인물 정체 문제 = Regen
소품 공개 타이밍 문제 = Regen 또는 Partial
속도 느림 = Edit
전환 어색함 = Edit
대사 잘 안 들림 = Edit 또는 재녹음/자막 보강
장면 의미가 깨짐 = Regen
```

## 9. EP20 예시 타임라인

예시: 19화 마지막 정적에서 20화 첫 도시 의뢰로 들어가는 구조.

```markdown
| CUT | Timecode | Duration | Visual | Dialogue/Subtitles | SFX | Music | Transition | Edit Note | Regen? |
|---|---:|---:|---|---|---|---|---|---|---|
| 20-01 | 00:00-00:12 | 12s | LU seated left, HEIQI low, TAN/HAN still, SHEN motorcycle enters from right | none or one short reaction only | distant engine -> close engine | dead low hold | sound bridge from silence | preserve 19 ending grief, no docs visible | No |
| 20-02 | 00:12-00:28 | 16s | SHEN stops, helmet off, reads room, closed backpack | SHEN brings commission without prying | engine off, leather glove, city ambience | light tension | cut on helmet movement | SHEN is external event, not comic relief only | Hold |
| 20-03 | 00:28-00:42 | 14s | HAN prepares to leave toward 镇灵司 | HAN report line, LU care line | distant city, steps | controlled quiet | clean cut | HAN exits by duty, not emotion escape | No |
| 20-04 | 00:42-01:05 | 23s | old house exterior, dust, iron door, still air | LU/HEIQI analyze abnormality | no wind, dust, low door creak | investigation pulse | cut to object inserts | show before explaining | Partial |
| 20-05 | 01:05-01:18 | 13s | LU stops SHEN opening door, inside sound answers | final hook line | sudden low breath from inside | music drop | hard cut to black | bigger question for EP21 | No |
```

## 10. CapCut 출력 전 점검

출력 전 아래 질문을 확인한다.

```text
첫 3초가 다음 컷을 보게 만드는가?
10초마다 새 정보/위험/감정 변화가 있는가?
대사가 이해되는가?
캐릭터 말투가 살아 있는가?
소품 공개 순서가 맞는가?
장면 전환이 같은 공간/시간 흐름으로 느껴지는가?
불필요하게 질질 끄는 컷이 있는가?
편집으로 덮을 문제와 재생성할 문제를 구분했는가?
마지막 5초가 다음 화 질문을 만든는가?
```

## 11. Codex에 요청할 때 쓰는 문장

앞으로 CapCut용 편집표가 필요하면 이렇게 요청한다.

```text
이 에피소드를 CapCut 타임라인 표로 만들어줘.
세계관/캐릭터/분경 규칙 먼저 확인하고,
CUT별 시간, 화면, 대사 자막, 효과음, 음악, 전환, 재생성 여부까지 넣어줘.
편집으로 해결 가능한 문제와 다시 생성해야 하는 문제를 구분해줘.
```

