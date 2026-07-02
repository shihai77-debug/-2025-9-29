# Jimeng Dialogue Voice Prompt Reference

목적: 即梦 / Seedance 영상 프롬프트에서 대사가 AI 낭독처럼 뜨거나, 캐릭터 감정 없이 평평하게 읽히거나, 누가 말하는지 흐려지는 문제를 막는다. 이 문서는 소설/분경에서 확정된 대사를 영상 프롬프트용 음성·연기 지시로 바꾸는 기준이다.

핵심:

```text
대사는 먼저 장면 행동에서 나온다.
그다음 화자, 원문, 감정, 속도, 숨, 멈춤, 강조, 말끝, 듣는 사람 반응을 붙인다.
AI에게 "자연스럽게 말해"라고만 쓰지 않는다.
사람처럼 들리게 하려면 사람이 말하는 조건을 구체적으로 준다.
```

## 1. 사용 순서

이 파일은 대사를 새로 쓰는 문서가 아니다. 아래 순서를 통과한 뒤 사용한다.

```text
1. Canon / character cards 확인
2. Cultural aesthetic sensibility gate 실행
3. LU protagonist voice gate 실행
4. Dialogue stage necessity gate 실행
5. Scene action before dialogue gate 실행
6. Dialogue clarity gate 실행
7. Jimeng dialogue voice prompt reference 적용
```

즉, 행동과 말할 이유가 없는 대사는 이 파일로 포장하지 않는다.

## 2. 한 대사마다 필요한 정보

Jimeng / Seedance 프롬프트에서 대사가 들어가는 CUT은 아래 항목을 반드시 가진다.

```markdown
| Field | Required Content |
|---|---|
| Speaker | 정확한 캐릭터 라벨: @陆沉舟 / @沈泊川 / @黑七 / @檀缺 / @韩知玄 |
| Exact line | 최종 확정 중국어 대사 원문 |
| Voice base | 음색, 높이, 안정감 |
| Emotion state | 겉 감정 + 속 감정 |
| Speaking speed | 느림/보통/빠름, 어디서 느려지는지 |
| Breath | 숨을 들이마시는 위치, 숨이 눌리는 위치 |
| Pause | 말 중간 멈춤, 대사 전/후 침묵 |
| Emphasis | 강조 단어 1~2개 |
| Tail tone | 말끝이 잘리는지, 낮아지는지, 흔들리는지 |
| Face/mouth | 입 움직임, 눈, 턱, 시선 |
| Body support | 손, 어깨, 발, 자세 변화 |
| Listener reaction | 듣는 사람의 표정/행동 반응 |
```

## 3. 프롬프트 문장 형식

좋은 형식:

```text
@角色 says exact line "……" in a [voice base], with [emotion state].
Speech speed is [speed], with a short pause after "关键词".
Breath is [breath note]. Emphasis falls on "关键词".
Tail tone [falls/cuts/softens].
Mouth movement matches the line, eyes stay on [target], body [action].
Listener @角色 reacts by [reaction].
```

중국어 최종 프롬프트에 넣을 때는 아래처럼 압축한다.

```text
@角色 用低稳/发紧/压低/急促的声音说出原句“……”，语速……，在“……”后短暂停顿，重音落在“……”，尾音……；说话时视线……，手/肩/身体……；听者@角色……反应。
```

## 4. 캐릭터별 음성 기준

### LU / 陆沉舟

```text
Voice base: 厚实偏低的青年中音, low and stable.
Emotion: 절제, 판단, 책임 압력. 슬픔을 소리치지 않는다.
Speed: 보통보다 조금 느림. 위험 판단에서는 단어 사이가 더 또렷해진다.
Breath: 대사 전 짧게 숨을 눌러 잡는다.
Pause: 핵심 판단 전 0.3~0.5초 멈춤.
Emphasis: 위험 조건, 局의 구조, 행동 지시.
Tail tone: 말끝을 낮게 닫는다. 허세처럼 길게 끌지 않는다.
Body: 시선은 단서에 먼저, 마지막 단어에서 상대에게 간다.
```

LU 금지:

```text
무조건 짧고 차가운 판정문
설명 없는 멋있는 침묵
분노한 고함
감정 없는 TTS 설명
```

### SHEN / 沈泊川

```text
Voice base: 현실적이고 젊은 남성 목소리, 약간 빠르지만 또렷함.
Emotion: 불안, 책임감, 상황을 이해하려는 긴장.
Speed: 놀랄 때 빨라지고, 위험을 깨달으면 말끝이 눌린다.
Breath: 문을 만지거나 후퇴할 때 숨이 짧아진다.
Pause: 농담 뒤 바로 본론으로 꺾인다.
Emphasis: 자기 책임, 의뢰 정보, 방금 위험했던 행동.
Tail tone: 허세가 아니라 현실적 두려움으로 낮아진다.
Body: 손이 멈추거나 뒤로 빠지며 말한다.
```

### HEIQI / 黑七

```text
Voice base: 검은 여우 본체의 낮고 빠른 비꼼, 위험 시 톤이 낮아짐.
Emotion: 겉은 비꼼, 속은 경계와 걱정.
Speed: 평소 빠름. 감각이 끊기면 한 박자 멈춘다.
Breath: 냄새를 맡는 동작 뒤 말이 나온다.
Pause: "不对" 같은 감각 변화 뒤 짧은 침묵.
Emphasis: 냄새가 나는 것보다 비정상적으로 비어 있는 지점.
Tail tone: 농담처럼 올리다 위험 순간 낮게 꺼진다.
Body: 귀, 코, 꼬리, 낮은 자세 반응을 반드시 붙인다.
```

### TAN / 檀缺

```text
Voice base: 차분하고 짧게 찌르는 젊은 여성 목소리.
Emotion: 관찰, 냉정, 黑七의 허세를 끊는 정확함.
Speed: 짧고 또렷함. 독설처럼 과장하지 않는다.
Pause: 상대 말을 듣고 0.2~0.4초 뒤 찌른다.
Emphasis: 장면 구조를 바꾸는 단어.
Tail tone: 낮고 깨끗하게 닫는다.
Body: 눈만 움직이거나 고개를 아주 작게 돌린다.
```

### HAN / 韩知玄

```text
Voice base: 절제된 공무식 남성 목소리.
Emotion: 직무, 경계, 보고 책임.
Speed: 안정적. 급해도 공무식 선을 유지한다.
Emphasis: 규정, 보고, 위험 등 직무 단어.
Tail tone: 감정을 크게 터뜨리지 않고 닫는다.
Body: 자세가 흐트러지지 않는다.
```

## 5. 사람처럼 들리는 대사 조건

아래가 없으면 대사가 AI 낭독처럼 들린다.

```text
대사 전 행동
대사 중 시선 대상
대사 중 몸의 긴장
숨 위치
멈춤 위치
강조 단어
말끝 처리
듣는 사람 반응
다음 행동 변화
```

특히 대사만 길게 쓰고 반응 컷이 없으면 실패한다.

## 6. 지멍 프롬프트에서 피할 것

금지:

```text
natural dialogue only
emotional voice
speaks dramatically
realistic acting
clear speech
human-like voice
```

이런 말만 쓰면 너무 추상적이다.

대신:

```text
low stable voice, short breath before the line, 0.4s pause after "气口", emphasis on "不能破", tail tone falls, eyes remain on the threshold dust line, listener freezes and lowers hand.
```

## 7. CUT 작성 템플릿

```markdown
Dialogue Voice Block:
- Speaker: @角色
- Exact line: "……"
- Voice:
- Emotion:
- Speed:
- Breath/Pause:
- Emphasis:
- Tail tone:
- Face/Mouth:
- Body:
- Listener reaction:
- Next action caused by this line:
```

## 8. 21화 老宅 예시

```text
@陆沉舟 用低稳、压住情绪的青年中音说出原句“手离门远点。它等的不是钥匙，是第一个替它开口的人。” 语速偏慢，在“远点”后短暂停顿，重音落在“第一个”和“开口”，尾音低低收住；说话时视线先落在门环和门槛灰线，最后才看向@沈泊川；@沈泊川的手停在门环前，指节发白，慢慢收回。
```

```text
@黑七 鼻尖先动，耳朵压低，用比平时更低的声音说“不是脏，是太干净了。” 语速先快后慢，在“太干净了”前停半拍，重音落在“干净”，尾音压低；身体贴近地面，尾巴不再晃；@檀缺看向它，眼神从嫌弃变成警觉。
```

## 9. 최종 검사

Jimeng / Seedance 대사 프롬프트를 내기 전에 검사한다.

```text
[ ] 대사 전에 행동이 있는가?
[ ] 정확한 화자 라벨이 있는가?
[ ] 최종 중국어 원문 대사가 들어갔는가?
[ ] 감정이 추상어가 아니라 숨/멈춤/강조/말끝으로 지시됐는가?
[ ] 입 움직임과 시선 대상이 있는가?
[ ] 듣는 사람 반응이 있는가?
[ ] 대사가 다음 행동을 발생시키는가?
[ ] 같은 인물 발화 순서가 반복되지 않는가?
```

## 10. 출력 명령

```text
Jimeng Dialogue Voice Prompt Reference를 적용해.
각 대사마다 화자, 원문, 음색, 감정, 속도, 숨, 멈춤, 강조, 말끝, 입/눈/몸 연기, 듣는 사람 반응, 다음 행동 변화를 붙여.
"자연스럽게 말함" 같은 추상 지시는 쓰지 말고, 사람이 실제로 말하는 조건을 구체적으로 적어.
```
