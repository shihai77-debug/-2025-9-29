# Flow Pacing Edit Decision Rules｜节奏空镜 / 压缩合并 / 跳过建议规则

This file makes prompt generation behave like an editor-director, not a mechanical CUT copier.

Use it whenever a CUT, sub-shot, storyboard panel, silence, movement, or empty beat may damage video rhythm.

## Core Rule

```text
无对白不等于删除。
沉默不等于无用。
空镜不等于坏。
但如果一个分镜没有剧情信息、没有情绪变化、没有空间/道具/continuity作用，只会拖慢节奏或破坏氛围，必须提出压缩、合并、替换或跳过建议。
```

Do not silently remove source material. Diagnose first and ask user approval before final pass/skip.

## Pacing Diagnosis Questions

```text
这个分镜是否推动剧情？
这个分镜是否推动情绪？
这个分镜是否改变人物关系、视线、位置、道具状态或信息量？
这个沉默是否有压迫、余韵、悲伤、悬念、呼吸、转折？
这个空镜是否建立空间、时间、危险、环境音或下一CUT连续性？
如果删掉，观众是否会看不懂下一CUT？
如果保留，观众是否会觉得拖、散、假、无聊、出戏？
```

## Keep

Keep the beat when it contains:

```text
情绪沉默。
眼神转折。
听者反应。
紧张累积。
空间建立。
道具状态变化。
人物位置/视线/距离变化。
下一CUT必须承接的 continuity anchor。
BGM/SFX/环境声的关键转场。
观众需要消化上一句台词的空气停顿。
```

## Compress

Recommend compression when:

```text
走路、停车、起身、转身、拿东西等动作太长，但只需要交代结果。
同一动作没有表演变化。
沉默没有新的情绪层次。
环境空镜只需建立空间，不需要完整时长。
AI生成风险高而信息量低。
```

## Merge

Recommend merging when:

```text
两个分镜表达同一情绪、同一站位、同一道具状态。
前一CUT末尾和后一CUT开头重复。
一个反应镜头可以承接两个信息点。
一个动作节点可以自然接入下一句对白。
```

When merging, preserve:

```text
dialogue order.
prop state.
screen geography.
eye-line direction.
audio transition.
continuity anchor.
```

## Replace With Cutaway

If deletion would break continuity but the original shot is weak, replace it with a short cutaway:

```text
手指收紧。
资料边缘。
背包拉链。
头盔落在手边。
摩托车余震。
门缝灰尘。
地面积灰。
铁门把手。
风停住。
脚步声远去。
空街角。
```

Cutaway length:

```text
0.8-2.5秒 for small prop/emotion bridge.
2-4秒 for space/danger setup.
```

## Pass / Skip Proposal

Only propose pass/skip when all are true:

```text
无对白。
无新情绪。
无新信息。
无位置变化。
无道具状态变化。
无必要空间建立。
无BGM/SFX/环境转场价值。
删除后不会破坏下一CUT理解。
保留会让节奏拖慢、气氛变弱或AI画面风险增加。
```

Required wording:

```text
节奏判断：此分镜可跳过/可合并/建议压缩。
原因：
会保留的continuity anchor：
建议替代方式：
需要用户确认后才能最终跳过。
```

## Never Pass Automatically

```text
不要自动删除原文剧情。
不要自动删对白。
不要自动删关键反应。
不要自动删道具交接。
不要自动删情绪转折。
不要自动删连接下一CUT的姿势/视线/声音。
```

If a pass is approved, move continuity anchors into the adjacent CUT or replacement cutaway.

## Output Decision Labels

Every questionable beat should receive one verdict:

```text
KEEP：保留，因其承载情绪/信息/continuity。
COMPRESS：压缩，保留结果和关键动作。
MERGE：合并到前后CUT，避免重复。
REPLACE：用短cutaway替代弱画面。
PASS_PROPOSAL：建议跳过，但必须用户确认。
```

## Final Rule

```text
观众不会因为“分镜完整”而喜欢视频。
观众会因为节奏、表演、情绪、声音和剪辑自然而继续看。
保留有用的沉默。
剪掉无用的空白。
所有跳过都必须先说明理由并请求确认。
```
