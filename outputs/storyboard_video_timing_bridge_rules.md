# Storyboard To Video Timing Bridge Rules

This file prevents conflicts between storyboard split timing and final Jimeng / Seedance video prompt timing.

## Core Rule

Storyboard panel time is not automatically final video duration.

```text
分镜图秒数 = visual beat / blocking reference time.
原文CUT秒数 = source story timing.
视频节点秒数 = final generation duration.
```

The agent must never silently mix these three values.

## Required Timing Bridge Table

Every video prompt made from a storyboard board must include:

```text
分镜-视频时间桥接表：
原文CUT时长：
分镜图标注时长：
分镜图秒数性质：visual beat only / approved video duration
台词自然表演所需时长：
最终视频节点时长：
采用原因：
是否改变原文时长：否 / 是，原因
```

## Which Duration Wins

Use this order:

```text
1. Final CUT source index controls original story timing, dialogue, BGM, SFX, emotion, and continuity.
2. Dialogue timing fit audit can extend or split the video duration when speech would be rushed.
3. Flow pacing rules can compress, merge, or replace weak visual beats, but pass/skip requires user approval.
4. Storyboard panel labels only control visual beat timing unless explicitly marked as approved video duration.
```

## When 3-4 Seconds And 6 Seconds Conflict

If storyboard board says 3-4 seconds but source says 6 seconds:

```text
If 3-4s is only a storyboard visual beat:
  final video prompt should keep source 6s unless flow pacing audit approves compression.

If 3-4s is an approved video edit decision:
  final video prompt may use 3-4s, but must state COMPRESS and explain what audio/continuity is preserved.

If dialogue, BGM, SFX, or important acting requires 6s:
  final video prompt must not shrink to 3-4s.

If the beat has no dialogue, no new information, and no meaningful action:
  it may be compressed, merged, replaced, or pass-proposed according to flow pacing rules.
```

## Mandatory Output Wording

When generating the final video prompt, write:

```text
注意：批准 storyboard board 的面板秒数只作为动作节奏和构图参考；最终视频节点时长以 source index、台词时长适配、节奏判断和本次批准的执行方案为准。
```

## Failure Triggers

The prompt is unsafe if:

```text
It says storyboard is 3-4s, then video prompt uses 6s without explaining why.
It changes source 6s to 3-4s without COMPRESS / MERGE / REPLACE / PASS_PROPOSAL judgment.
It keeps source 6s even though dialogue audit says it needs longer.
It treats storyboard panel time as source dialogue time.
It omits the final video node duration.
```

## Repair

When timing conflict appears, output:

```text
时间冲突修正：
分镜图秒数：
原文秒数：
最终视频秒数：
判断：KEEP_SOURCE / COMPRESS / EXTEND / SPLIT_NODES / MERGE / REPLACE / PASS_PROPOSAL
原因：
```
