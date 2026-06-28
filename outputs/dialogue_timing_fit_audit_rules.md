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

## Required Audit

For every spoken line, check:

```text
1. line text length.
2. assigned speaking window.
3. whether the line is exposition-heavy.
4. required breath before speech.
5. required internal pause.
6. required tail pause or listener reaction.
7. action overlap: opening bag, walking, turning, looking down, handing documents, camera movement.
8. face/lip-sync stability: close enough, stable enough, no major camera motion.
```

## Timing Heuristic

Use this as a practical prompt-writing estimate:

```text
short line: 1.5-3 seconds plus 0.3-0.8 second breath/reaction.
medium line: 3-6 seconds plus 0.5-1.0 second breath/reaction.
long line: 6-10 seconds plus 0.8-1.5 seconds breath/reaction.
information-heavy exposition: 8-12 seconds or split into multiple nodes.
two exposition lines in one CUT: usually 14-18 seconds, or two separate video nodes.
```

If a line contains professional analysis, case details, warnings, or multiple clauses, treat it as exposition-heavy even if the written text looks moderate.

## Failure Trigger

If any of these are true, the original timing is unsafe:

```text
assigned speaking window is under the heuristic minimum.
speaker also performs a prop action while speaking.
speaker face is small or moving.
camera moves during mouth-sync.
line contains more than one information point and no pause window.
two long lines share a short CUT.
listener reaction is required but no time remains.
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

## Output Requirement

Every video prompt with dialogue must contain:

```text
台词时长适配：
原分镜时长：
自然表演所需时长：
判断：可用 / 不可用
处理：原时长 / 延长到X秒 / 拆成X个视频节点 / 建议后期配音
```

If the user asks for prompt only, hide the long explanation but still apply the repair inside the final prompt.

## CUT-10 Known Risk

CUT-10 contains two professional feng-shui analysis lines. A literal 10-second single video with both lines is unsafe for natural delivery.

Default repair:

```text
CUT-10A：0-7秒，陆沉舟俯身看积灰，说第一句。固定近景或中近景。
CUT-10B：0-8秒，陆沉舟抬眸望走廊，说第二句。固定中近景，结尾留0.5秒空气。
```

Alternative repair:

```text
Extend CUT-10 to 15-16 seconds if the platform supports one longer clip.
```
