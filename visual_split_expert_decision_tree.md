# 영상 분할 전문가 자동 판단 트리｜Visual Split Expert Decision Tree

## 문서 목적

이 문서는 Codex가 분진/분할자료/자리배치/배경/영상 프롬을 만들 때 **자동으로 더 똑똑한 영상 분할 전문가처럼 판단**하도록 하기 위한 공통 규칙이다.

이 문서는 스토리, 대사, 사건 순서를 새로 쓰기 위한 문서가 아니다.

```text
Do not rewrite story, dialogue, or plot.
Only decide split count, actor blocking, camera rhythm, reference priority, continuity, and prompt type.
```

---

## 0. 반드시 참고할 기존 기준 파일

새 분할자료나 영상 프롬을 만들기 전에 아래 파일을 먼저 확인한다.

```text
1. FIXED_DIRECTOR_GENERATION_RULES.md
2. episode19_acting_split_timing_rules.md
3. episode20_director_acting_image_guide.md
4. episode20_precision_self_check_rules.md
5. episode20_background_reference_old_house_gate.md
6. episode20_character_reference_shen_bochuan.md
```

역할:

```text
FIXED_DIRECTOR_GENERATION_RULES.md：전체 최고 규칙. 삼면도 우선, 연속성, 대사, 다인물, 출력 형식.
episode19_acting_split_timing_rules.md：분할 수, 대사 반복 방지, 흑백 참고도와 최종 영상 분리.
episode20_director_acting_image_guide.md：EP20 공식 분진, 초수, 대사, 컷 구조.
episode20_precision_self_check_rules.md：출력 전 자가 시뮬레이션 및 PASS/FAIL 체크.
episode20_background_reference_old_house_gate.md：EP20 老宅外部 배경과 자리 공간 고정.
episode20_character_reference_shen_bochuan.md：沈泊川 외형/도구/혼동 방지.
```

---

## 1. Split Count Decision Tree｜분할 수 결정 트리

분할 참고도를 만들기 전에 먼저 CUT 유형을 판단한다. 분할 수는 초수만 보고 정하지 않고, 실제 변화량으로 정한다.

```text
If the CUT has only one still reaction and no movement:
  use 1 split.

If the CUT is a static emotional beat with eye-line change or one short line:
  use 2-3 splits.

If the CUT has one speaker + one hand action:
  use 2 splits.

If the CUT has movement from point A to point B:
  use 2-3 splits.

If the CUT has arrival + object action + final pose:
  use 3-4 splits.

If the CUT has long logical dialogue with 3 layers:
  use 3 splits.

If the CUT has action, location change, and multiple visual beats:
  use 4-5 splits.

Never increase split count only because the image looks richer.
Split only when action, eye-line, mouth state, camera function, or object position changes.
```

절대 원칙:

```text
분할 수를 많이 만든다고 정확해지는 것이 아니다.
정적인 컷을 과도하게 쪼개면 표정이 흔들리고 같은 장면이 반복된다.
```

---

## 2. CUT Type Labels｜컷 유형 라벨

각 CUT은 프롬프트 작성 전에 아래 중 하나로 분류한다.

```text
STATIC_REACTION
STATIC_EMOTION
DIALOGUE_ONLY
DIALOGUE_WITH_HAND_ACTION
MOVEMENT_TO_POSITION
ARRIVAL_TRANSITION
OBJECT_HANDOFF
GROUP_REACTION
LOGIC_JUDGMENT
ENDING_EYE_SHIFT
```

라벨별 기준:

```text
STATIC_REACTION：표정/시선 반응만 있는 컷. 보통 1분할.
STATIC_EMOTION：정지 구도에서 눈빛이나 감정이 변하는 컷. 보통 2-3분할.
DIALOGUE_ONLY：한 인물이 말하는 컷. 입 닫힘/입 열림/말 끝을 기준으로 2-3분할.
DIALOGUE_WITH_HAND_ACTION：대사와 손/자료/문 등 물체 행동이 같이 있는 컷. 보통 2분할.
MOVEMENT_TO_POSITION：A지점에서 B지점으로 이동. 2-3분할.
ARRIVAL_TRANSITION：장소 전환, 도착, 정지. 1-3분할.
OBJECT_HANDOFF：자료, 도구, 인장 등 물체가 손에서 손으로 넘어가는 컷. 2분할 우선.
GROUP_REACTION：여러 인물이 같은 사건에 반응. 주체 1명, 보조 반응 1-2명만 선명.
LOGIC_JUDGMENT：판단/분석 대사가 논리 단계로 나뉨. 논리 층수만큼 분할.
ENDING_EYE_SHIFT：엔딩 눈빛 변화. 과한 동작 없이 시선 변화 중심.
```

---

## 3. Required Blocking Map｜필수 자리배치 지도

모든 분할 프롬프트는 반드시 간단한 자리배치 지도를 포함한다.

필수 형식:

```text
画面左侧：
画面中间：
画面右侧：
前景：
中景：
背景：
低位角色：
不出现角色：
```

규칙:

```text
黑七가 등장하면 반드시 低位角色에 적는다.
등장하지 말아야 할 인물은 不出现角色에 적는다.
주인공이 아닌 인물은 edge / background / blurred / silent로 표시한다.
배경 인물이 주체 위치를 빼앗지 않게 한다.
화면에 모든 인물을 억지로 선명하게 넣지 않는다.
```

---

## 4. Camera Function Lock｜카메라 기능 고정

모든 CUT은 행동 설명 전에 카메라 기능을 먼저 고정한다.

필수 형식:

```text
镜头功能：
起点画面：
终点画面：
运镜：
禁止运镜：
```

허용 카메라 유형:

```text
固定镜头
稳定跟随
轻微横向跟随
缓慢推近
低角度细节
近景固定
中景群像固定
```

각 유형의 기본문:

```text
固定镜头：固定镜头，不推，不拉，不摇，不绕圈。
稳定跟随：稳定跟随拍摄，轻微跟随人物移动，不乱摇，不快速变焦。
缓慢推近：缓慢推近到眼神或手部重点，不突然变焦。
低角度细节：低角度拍摄关键线索，背景保持同一空间。
中景群像固定：中景固定群像，只变化视线、头部小动作和嘴型。
```

금지 카메라:

```text
绕圈
快速变焦
大幅摇晃
无意义推拉
突然切大特写
连续随机换角度
```

---

## 5. Reference Priority Reminder｜참고 우선순위 알림

매번 내부적으로 아래를 확인한다.

```text
角色外形 = 三面图 / 定妆图
背景 = 背景参考文件
动作 = 正式分镜
站位 = 上一CUT结尾 + 当前CUT要求
镜头 = 当前CUT镜头功能
情绪 = 当前CUT演技说明
道具 = 上一CUT已经出现的物体 + 当前CUT要求
```

금지:

```text
导演分割图不能决定角色脸、发型、服装。
背景图不能决定角色脸、服装。
临时草图不能替代三面图。
上一张失败图不能作为角色外形依据。
```

---

## 6. Pass / Reject Examples｜통과/폐기 예시

### PASS

```text
背景参考有足够前景空地，可以站下本CUT需要的人物。
分割参考显示不同动作阶段，不是重复同一姿势。
主角在视觉上明确，其他人物不抢中心。
黑七仍是小型黑狐本体。
沈泊川与陆沉舟、韩知玄脸型和服装明显区分。
资料文件、头盔、背包等道具在前后CUT中连续。
老宅铁门、门槛、门外积灰、暗走廊在CUT-08~15中稳定。
```

### REJECT

```text
画面好看但没有演员站位空间。
老宅变成垃圾废墟、鬼屋、豪宅或古代府门。
角色该站却坐，该坐却站。
上一CUT已有道具，下一CUT无故消失。
五格分割重复同一个姿势，没有动作或视线变化。
黑七变成狗、狼、怪物、人形。
沈泊川像陆沉舟或韩知玄。
檀缺像白清檀或穿回白衣。
背景人物抢主角位置。
最终视频提示词里重复写多遍对白。
```

---

## 7. Final Video Prompt Compression Rule｜最终视频提示词压缩规则

导演分割图提示词可以详细。最终视频生成提示词必须压缩。

最终视频提示词只保留:

```text
CUT number
exact duration
reference images used
background lock
character lock
action sequence
camera movement
dialogue once
sound priority
3-5 key negative rules
```

禁止:

```text
不要把整个导演分割计划原文贴进最终视频提示词。
不要在最终视频提示词中重复多次对白。
不要把黑白铅笔画风作为最终视频风格。
不要把分镜编号、箭头、文字、边框带入最终视频。
```

最终视频固定提醒:

```text
导演参考图只参考动作、站位、视线、镜头节奏和每格时间分割。
不要参考黑白画风、文字、箭头、编号、边框和临时人物外形。
本CUT对白只朗读一次，不要重复朗读，不要拆成多次重复对白。
```

---

## 8. Mandatory Self-Check Output｜내부 자가 체크 항목

최종 프롬프트를 주기 전에 내부적으로 아래를 실행한다.

```text
CUT type:
Recommended split count:
Official split count:
Continuity risk:
Blocking risk:
Character identity risk:
Background risk:
Object continuity risk:
Dialogue repetition risk:
PASS / MINOR PASS / FAIL:
```

운영 규칙:

```text
사용자가 요청하지 않으면 이 보고서를 길게 보여주지 않는다.
PASS면 계속 고치지 않는다.
MINOR PASS면 보정문 1-2개만 추가한다.
FAIL이면 실패한 부분 하나만 수정한다.
```

---

## 9. Episode 20 Specific Smart Checks｜第二十集 전용 스마트 체크

```text
CUT-01:
Check Episode 19 emotional aftertaste and Shen Bochuan motorcycle entrance.
Do not lose Lu Chenzhou's empty-after-farewell state.

CUT-02:
Check backpack, documents, helmet, and Shen Bochuan as main subject.

CUT-03:
Check object handoff. Documents must enter Lu Chenzhou's hand.

CUT-04-05:
Check documents remain in Lu Chenzhou's hand.

CUT-06-07:
Check Han Zhixuan exits and should not appear after CUT-07.

CUT-08-15:
Use old house exterior background.
Keep iron gate, threshold dust, dim inner corridor, enough standing space.

CUT-10:
Dust must be visible as a clue, not garbage.

CUT-11:
Black Seven must remain small black fox.

CUT-13:
Three logic layers: not ghost → human-made blockage → warning.
Do not merge all logic into one rushed speech beat.

CUT-15:
No dialogue. Eye shift only. End connects to Episode 21.
```

---

## 10. Do Not Over-Optimize｜과최적화 금지

```text
More checking is not always better.
If the prompt passes official script, continuity, blocking, character identity, background, and dialogue checks, stop.
Do not keep rewriting a PASS prompt.
Do not add more restrictions unless there is a real failure.
```

불안정 신호:

```text
같은 내용을 계속 다른 말로 반복.
금지문이 10개 이상으로 늘어나 핵심 행동이 흐려짐.
모든 인물을 매번 선명하게 넣으려 함.
배경 설명이 인물 행동보다 길어짐.
최종 영상 프롬에 분할도 설명을 전부 붙임.
```

단순화 우선순위:

```text
1. 주체 인물 1명 확정.
2. 보조 인물은 edge/background/silent 처리.
3. 카메라 고정.
4. 손/도구 노출 최소화.
5. 대사 1회만 남김.
6. 금지문은 3-5개 핵심만.
```

---

## 최종 원칙

Codex는 사용자가 매번 불안해하지 않도록, 출력 전에 위 규칙으로 자동 점검한다.

하지만 Codex는 자기 판단으로 스토리와 대사를 바꾸지 않는다.

```text
자동화 대상：분할 수, 자리배치, 카메라, 배경, 연기 리듬, 프롬프트 안정성.
자동화 금지 대상：스토리, 대사, 사건 순서, 캐릭터 관계, 세계관 설정.
```
