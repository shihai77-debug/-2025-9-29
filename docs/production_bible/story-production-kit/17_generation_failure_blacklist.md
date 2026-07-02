# Generation Failure Blacklist

목적: 이미지/영상 생성에서 반복 실패하는 문제를 기록하고, 다음 프롬프트에서 미리 막는다.

## 1. 캐릭터 실패

```text
HEIQI가 사람처럼 나옴
HEIQI가 반인반수로 나옴
SHEN이 HAN처럼 보임
LU가 감정 과잉으로 울부짖음
TAN이 설명 담당처럼 장황하게 말함
HAN이 공무적 책임 없이 사라짐
```

방지 문장:

```text
HEIQI must remain a true black fox body, never human, never humanoid.
Keep SHEN visually distinct from HAN.
Do not make LU emotionally explosive; show delayed response and restrained grief.
```

## 2. 소품 실패

```text
CUT-01에서 资料가 보임
닫힌 背包이 너무 빨리 열림
헬멧을 01-2에서 벗음
핵심 소품이 여러 개 동시에 강조됨
```

방지 문장:

```text
Documents must remain hidden until the specified cut.
Backpack stays closed unless explicitly opened.
Helmet remains on until the helmet-off beat.
Only one hero prop per scene.
```

## 3. 장소 실패

```text
배경이 산악 황야와 도시 도로 두 장소처럼 분리됨
같은 장소인데 컷마다 구조가 바뀜
老宅가 갑자기 현대 고급 주택처럼 나옴
도시 소음과 죽은 공기 대비가 사라짐
```

방지 문장:

```text
Keep spatial continuity across cuts.
The city transition must feel motivated by SHEN's entry, not a hard location reset.
Old house must remain damp, narrow, aging, and airless.
```

## 4. 스토리 실패

```text
전컷 마지막 대사를 받지 않음
첫 3초 질문이 없음
대사가 정보만 말함
다음화 질문 없이 끝남
티키타카가 감정 장면을 깨뜨림
```

방지 기준:

```text
Every scene must receive the previous final line/action.
Every opening must create a first-three-second question.
Major dialogue must contain character + emotion + story information.
End with a larger mystery, not a solved explanation.
```

## 5. 업데이트 방식

실패가 반복되면 아래 형식으로 추가한다.

```text
실패 유형:
발생 회차/CUT:
원인:
방지 문장:
다음 테스트 결과:
```
