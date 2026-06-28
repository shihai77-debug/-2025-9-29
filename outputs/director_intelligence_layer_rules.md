# Director Intelligence Layer｜导演判断层

This layer exists to make prompt generation smarter, not looser.

The source story is locked. The director execution is flexible.

## Core Rule

```text
原分镜内容、对白、人物关系、事件顺序、BGM、SFX、道具状态不能乱改。
但为了最终视频更好看、更自然、更能把观众带进去，可以重新设计拍法：
镜头节点、时长、镜头角度、反应镜头、插入镜头、动作/台词拆分、表演节奏、压缩、合并、替换cutaway都可以由导演判断优化。
```

Do not output a weak prompt just because the user asked for a CUT prompt. Diagnose first.

## Director Diagnosis First

Before writing a storyboard prompt or Jimeng / Seedance video prompt, run this diagnosis:

```text
导演诊断：
1. 本CUT的剧情核心是什么？
2. 本CUT最容易失败的点是什么？脸、台词、时间、动作、镜头、声音、情绪？
3. 如果按原分镜硬做，会不会像朗读、木偶站位、脸崩、镜头乱、声音不平？
4. 是否需要延长时长？
5. 是否需要拆成多个视频节点？
6. 是否需要 master shot / dialogue shot / reaction shot / cutaway？
7. 哪些内容绝对不能改？
8. 哪些拍法可以优化？
9. 是否存在无意义空白、拖慢节奏的移动、重复反应、弱空镜？
10. 是否应该保留、压缩、合并、替换cutaway，或向用户提出跳过建议？
```

Only after this diagnosis should the final prompt be written.

## Locked Content

Never change:

```text
原文对白。
对白说话人。
事件顺序。
人物关系。
人物性格底层逻辑。
BGM / SFX / 环境音来源。
关键道具状态。
上下CUT continuity anchor。
```

## Director-Editable Content

The director may optimize:

```text
视频节点数量。
每个节点时长。
镜头景别。
镜头角度。
谁先进画面，谁后反应。
台词前后的呼吸和停顿。
听者反应镜头。
手、资料、门、车、尘土、街角等cutaway。
动作节点和说话节点分离。
多人画面拆成2人以内清晰脸。
节奏不佳的空白可压缩、合并或替换为短cutaway。
无剧情/无情绪/无continuity价值的分镜可提出跳过建议，但必须用户确认。
```

## Red Flag Audit

If any of these appear, do not directly produce the old prompt. Propose a smarter split.

```text
3人以上清晰脸同框。
长台词塞进短秒数。
人物边走边说长台词。
开包、递资料、骑车、转身等动作和大段台词同时发生。
重要说话者脸太小。
同一节点既要精确脸又要大幅镜头运动。
配角只站着没有反应。
BGM/SFX没有和对白分层。
台词听起来像朗读。
无对白且无情绪变化的空白镜头。
只拖慢节奏、不建立空间或continuity的移动镜头。
重复上一CUT信息的反应镜头。
```

## Flow Pacing Edit Gate

Before preserving a silent or weak beat, classify it:

```text
KEEP：承载情绪、悬念、反应、空间、道具或continuity。
COMPRESS：动作/移动有用但时长过长。
MERGE：与前后CUT重复，可自然合并。
REPLACE：原镜头弱，但需要用手、资料、门、灰尘、风声等cutaway保留连接。
PASS_PROPOSAL：无对白、无情绪、无信息、无位置/道具变化、无continuity价值，建议跳过但必须用户确认。
```

Never skip automatically.

```text
提出跳过时必须说明原因。
必须说明保留或转移哪些continuity anchor。
必须等用户确认后才能最终删除/跳过。
```

## Immersion Goal

The goal is not merely "correct".

The goal:

```text
观众能被带进故事。
人物像真人演员在现场呼吸、听、停顿、反应。
台词像人说出来，不像读稿。
镜头像导演拍出来，不像说明书。
声音有空间、有层次、有情绪，但不盖台词。
每个CUT都推动情绪或剧情，而不是只完成信息交代。
```

## Dialogue Performance Upgrade

For any dialogue that feels like narration, split performance into beats:

```text
开口前：0.2-0.5秒吸气 / 看向对象 / 手部准备。
第一信息点：自然说出，不急。
中间停顿：给观众消化，给听者反应。
重音词：只压关键词，不靠提高音量。
句尾：收住、压低、断开或放轻。
台词后：0.3-0.8秒听者反应或空气停顿。
```

If one long line carries too much information, use:

```text
speaker close shot -> prop cutaway -> speaker continuation -> listener reaction
```

## Smart Split Examples

### Dense Commission Briefing

Instead of one 15-second talking block:

```text
CUT-02A action node: 沈泊川 opens backpack, takes documents, breath before speaking.
CUT-02B dialogue node: first casual line, face stable, slight surface ease.
CUT-02C dialogue/cutaway node: old house case, documents in hand, hand pause on key danger word.
CUT-02D reaction node: 陆沉舟/檀缺/黑七 micro-reaction, silence lands.
```

### Group Scene

Instead of five clear faces in one board:

```text
faceless master shot for geography.
2-person speaking shot.
2-person listener shot.
fox or prop cutaway.
```

### Movement Plus Speech

Instead of walking and speaking long line:

```text
action node completes movement.
camera lands.
speaking node begins after breath.
reaction shot catches listener response.
```

### Weak Empty Beat

Instead of preserving a dead 6-second pause:

```text
If it carries grief/pressure: KEEP and protect silence.
If it only repeats position: COMPRESS to 1 second.
If it bridges continuity: REPLACE with hands/prop/environment cutaway.
If it has no value: PASS_PROPOSAL with user approval.
```

## Required Output Format For Smart Prompts

When generating a new prompt, include:

```text
导演诊断：
节奏判断：KEEP / COMPRESS / MERGE / REPLACE / PASS_PROPOSAL
台词时长判断：
脸部稳定判断：
建议执行方式：
不可更改内容：
允许优化内容：
最终提示词：
```

If the user asks for "prompt only", hide the diagnosis but still apply it silently. Do not silently skip or delete source beats unless user has approved that specific skip/pass.

## Final Rule

Do not be a mechanical prompt copier.

Be a source-locked director:

```text
故事不乱改。
拍法要聪明。
保留有用的沉默。
剪掉无用的空白，但必须先说明理由并请求确认。
表演要像人。
镜头要能剪。
声音要能听。
观众要想继续看。
```
