# Dialogue Timing Fit Audit Rules｜台词时长适配强制检查

This file is mandatory for every Jimeng / Seedance video prompt that contains dialogue.

The agent must not wait for the user to point out that a line is too long for the CUT duration.

## Core Rule

Before writing any video prompt, run a dialogue timing fit audit.

```text
原分镜时长不是最终可用时长。
如果原分镜时长装不下自然表演、呼吸、停顿、口型和听者反应，必须主动延长、拆节点，或建议画面与后期配音分离。
不得为了塞进原秒数而让台词变成快速朗读。
```

## Required Per-Line Audit

For every spoken line, calculate a practical speech budget.

```text
台词时长适配：
角色：
原台词：
台词字数：
安全语速：
裸读所需：
停顿/气口：
动作占用：
听者反应/尾音：
最低安全时长：
原分镜窗口：
判断：可用 / 不可用
处理：原时长 / 延长到X秒 / 拆成X个视频节点 / 建议后期配音
```

## Speech Rate Budget

Use this estimate before accepting a timing window.

```text
normal dramatic Mandarin dialogue: 4.0-4.8 Chinese characters per second.
exposition / professional analysis / clue explanation: 3.6-4.2 Chinese characters per second.
emotional, restrained, or weighty delivery: 3.2-4.0 Chinese characters per second.
rushed upper limit: 5.0 Chinese characters per second, but avoid this for final video prompts.
```

Add time for performance:

```text
pre-line breath: +0.3-0.6s.
each major punctuation / phrase turn: +0.25-0.5s.
important emphasis: +0.3-0.8s.
simultaneous prop/action/camera movement: +0.5-1.5s.
tail pause or listener reaction: +0.5-1.0s.
```

Practical categories:

```text
short line: 1.5-3s plus breath/reaction.
medium line: 3-6s plus breath/reaction.
long line: 6-10s plus breath/reaction.
information-heavy exposition: 8-12s or split into multiple nodes.
two exposition lines in one CUT: usually 16-20s, or two separate video nodes.
```

If a line contains professional analysis, case details, warnings, or multiple clauses, treat it as exposition-heavy even if the written text looks moderate.

## Failure Trigger

If any of these are true, the original timing is unsafe:

```text
assigned speaking window is under the calculated minimum.
speaker also performs a prop action while speaking.
speaker face is small or moving.
camera moves during mouth-sync.
line contains more than one information point and no pause window.
two long lines share a short CUT.
listener reaction is required but no time remains.
the prompt would require faster than 4.8 Chinese characters per second for exposition.
```

## Mandatory Repair

When unsafe, do not output the old timing.

Choose one:

```text
EXTEND：increase total duration while preserving story and dialogue.
SPLIT_NODES：split into A/B/C video nodes, e.g. action node -> dialogue node -> reaction/cutaway node.
CUTAWAY_SUPPORT：keep speaker audio across prop/detail cutaway when face stability is not needed.
VOICE_SEPARATE：generate visual-only video and add exact dialogue in dubbing/TTS later.
```

## CUT-10 Known Risk

CUT-10 contains two professional feng-shui analysis lines. A literal 10-second single video with both lines is unsafe for natural delivery.

Line audit:

```text
CUT-10 line 1:
台词：你看地上的积灰。正常闲置房屋的灰尘，都会堆积在门内角落，但这里的灰尘，全是从屋内被推扫到了门外。
台词字数：43 Chinese characters, 5 punctuation breaks.
最低安全时长：9.5-10s.
Reason: professional observation + explanation + contrast, must include a visible pause after “积灰” and before “但这里的灰尘”.

CUT-10 line 2:
台词：天光能够照进屋内，却没有半点穿堂风。空气凝滞不动，完全不符合常理。
台词字数：29 Chinese characters, 4 punctuation breaks.
最低安全时长：7.5-8s.
Reason: professional conclusion, must pause before “完全不符合常理”.
```

Default repair:

```text
CUT-10A：10秒，陆沉舟俯身看积灰，说第一句。固定近景或中近景，结尾留0.5秒低巷内环境声。
CUT-10B：8秒，陆沉舟抬眸望走廊，说第二句。固定中近景，结尾留0.5秒安静空气。
```

Alternative repair:

```text
Use one extended 18-second clip only if the platform supports stable 18s generation.
If the platform limit is 15s, do not force both lines into one clip; split into CUT-10A and CUT-10B.
```
