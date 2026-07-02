# Cinematic Shot Grammar Rules｜电影化镜头拆分规则

This file defines the default filming grammar for storyboard boards, clean keyframes, and Jimeng / Seedance video prompts.

The goal is not to mechanically split every CUT into A/B panels. The goal is to judge the CUT like a real director: what should be a master shot, what should be a dialogue shot, what should be a reaction shot, and what should be a cutaway.

## Core Principle

Do not force every emotion, line, movement, face, prop, and camera move into one image or one video node.

Real filming separates functions:

- master shot establishes space and relationships.
- dialogue shot protects face, acting, voice, and lip sync.
- reaction shot protects listening performance and emotional continuity.
- cutaway protects props, clues, sound, and tension without risking face drift.
- action node handles movement.
- speaking node handles stable performance.

This is a quality upgrade, not a downgrade.

## Multi-Character Generation Limit｜多人画面生成限制

One generated storyboard panel, clean keyframe, or video node should contain at most two clear human faces.

If the source CUT has three or more people, do not ask the model to render all faces clearly in one frame. Split the CUT with camera/editing grammar so the story remains continuous while each generated image stays stable.

Hard rule:

```text
3+ clear human faces in one generated frame = high face-break risk.
Use max 2 clear human faces per dialogue/keyframe/video node.
Use 3+ character frames only as faceless/blocking master shots.
```

Recommended split:

```text
5 characters -> 2-person dialogue/action shot + 2-person reaction shot + fox/prop/environment cutaway.
4 characters -> 2-person shot + 2-person shot.
3 characters -> 2-person shot + 1-person reaction, or a faceless 3-person master shot.
```

When the original CUT requires a group sense, preserve it with continuity anchors instead of forcing all faces:

```text
same background direction.
same prop state.
same eye-line direction.
same screen geography.
same audio bed.
same BGM/SFX continuation.
```

If a group frame is necessary:

```text
Use faceless style reference mode.
Do not draw clear eyes, nose, or mouth.
Keep hairstyle, outfit, body shape, posture, position, and movement direction exact.
The image is for blocking only, not final face reference.
```

## Shot Function Types

### Master Shot｜关系场面

Use for:

- three or more characters in the same space.
- relationship, blocking, distance, and continuity.
- entry, arrival, standoff, shared silence, group reaction.

Rules:

- Do not put long dialogue here.
- Do not demand perfect small faces in deep background.
- Keep the main speaker either silent or with only a very short line.
- Supporting characters must still act: micro breathing, eye movement, hand tension, jaw tension, tiny shoulder reaction.
- This shot may use side face, back, silhouette, or slightly softer face for distant characters, but identity must remain clear through costume, body, position, and reference lock.

### Dialogue Shot｜台词镜头

Use for:

- important spoken lines.
- speaker face stability.
- lip sync.
- emotional reading.

Rules:

- Prefer one speaker, or at most two characters.
- Use clean keyframe, not storyboard board.
- Face must come from turnaround / character reference, not from the storyboard board.
- Camera should be stable: medium close-up, close-up, or controlled two-shot.
- If the line is long, extend time or split into multiple speaking nodes.
- Actor performance directions are mandatory: voice base, volume continuity, speed, breath, outer emotion, inner emotion, emphasis, pause, tail sound, mouth/eye behavior, body support.

### Reaction Shot｜反应镜头

Use for:

- listener emotion.
- silent continuation after a line.
- emotional bridge between CUTs.
- showing that supporting characters are alive, not wooden.

Rules:

- Usually no dialogue.
- Focus on eyes, breath, hand tension, stillness, slight shift of attention.
- Do not add new plot information.
- Keep reaction continuous with the previous line or action.

### Cutaway｜插入镜头

Use for:

- hands, documents, backpack, helmet, motorcycle, door, dust, ash, corridor, street corner, props, environment.
- clues and tension.
- covering long dialogue without forcing unstable faces.

Rules:

- Cutaway can carry SFX, prop state, atmosphere, and continuity.
- It avoids face drift by not forcing a talking face when the important thing is a clue or object.
- Never invent props not in the source.

### Action Node｜动作节点

Use for:

- walking, entering, turning, taking documents, stopping motorcycle, opening door, moving to a new location.

Rules:

- Keep dialogue minimal or none.
- Action must have start position, movement direction, end position, prop state, and continuity anchor.
- If action and long dialogue happen together, split action node and speaking node.

### Speaking Node｜说话节点

Use for:

- stable dialogue performance.
- voice and mouth movement.

Rules:

- Keep body movement restrained.
- Do not combine with large movement, fast camera motion, or multi-person wide shot unless the line is very short.
- Speaker face must be large enough to recognize.

## Required Decision Before Every Video Prompt

Before writing a Jimeng / Seedance video prompt, output this judgment internally and reflect the result in the prompt:

```text
镜头功能判断：
- 本CUT原始功能：
- 是否三人以上同框：
- 是否包含长台词：
- 是否包含复杂动作：
- 是否需要精确脸：
- 风险判断：
- 建议拆分：
```

## Hard Split Rules

These combinations must not be forced into one video node:

- three or more characters in one wide frame + long dialogue.
- three or more clear human faces in one generated frame.
- complex movement + long dialogue.
- small distant speaker face + required lip sync.
- action entry + emotional close performance.
- prop operation + exposition line longer than the available duration.
- unstable generated face + important dialogue.

When these appear, split into:

```text
master shot -> dialogue shot -> reaction shot -> cutaway
```

or:

```text
action node -> speaking node -> reaction/cutaway
```

## Timing Rules

Use the final CUT source index as authority for original duration, but do not crush dense dialogue into an unsafe length.

- short line: 1.5-3 seconds plus breath/pause.
- medium line: 3-6 seconds plus breath/pause.
- long line: 6-10 seconds plus breath/pause.
- information-heavy exposition: 8-12 seconds or split into multiple video nodes.

Every video prompt must state one of:

```text
原时长可承载台词，不需要延长。
台词偏密，建议延长到 X 秒。
台词过密，建议拆成 CUT-XX-A / CUT-XX-B 两个视频节点。
本CUT无台词，不需要台词时长调整。
```

## Face Stability Rules

If exact face is important:

- use `outputs/exact_face_style_mode_rules.md`.
- create or use face lock image first.
- then create clean keyframe.
- then write Jimeng / Seedance video prompt from the clean keyframe.

Do not use a labeled storyboard board as final image reference for faces.

If exact face is not the main task:

- master shot may use side face, back view, soft focus, silhouette, or distant staging.
- dialogue shot still needs a clean and stable speaker face.

Do not blur important dialogue faces to hide errors. Blurred faces are only acceptable for distant background characters, transitional action, or non-dialogue master shots.

## Audio And Performance Rules

Dialogue, BGM, SFX, and environment sound always come from `outputs/episode20_final_cut_source_index.md`.

Volume priority:

```text
voice > core SFX > environment sound > BGM
```

For dialogue shots:

- BGM must duck under speech.
- SFX must not cover the first consonant or last tail sound.
- voice volume must remain continuous across adjacent CUTs.
- emotion is expressed through breath, speed, pauses, eyes, and body, not sudden volume jumps.

## Storyboard Board Rules

Storyboard reference boards may include labels, arrows, panel numbers, mini maps, and camera paths.

Storyboard board labels must use Chinese names / Chinese production labels, not English abbreviations.

Use:

- `陆沉舟`
- `黑七`
- `檀缺`
- `韩知玄`
- `沈泊川`
- `镜头固定`
- `镜头横移跟随`
- `位置锁定`
- `背景连续`
- `资料不可见`

Do not use:

- `LU`
- `HEIQI`
- `TAN`
- `HAN`
- `SHEN`

Clean keyframes and final video prompts must not contain labels, arrows, UI, panel borders, or storyboard text.

## Output Checklist

Before sending any final storyboard or video prompt, check:

```text
[ ] Did I judge shot function first?
[ ] Did I avoid multi-person wide shot with long dialogue?
[ ] Did I keep clear human faces to at most two per generated frame/node?
[ ] Did important dialogue get a stable dialogue shot?
[ ] Did action and speaking get split when needed?
[ ] Did reaction/cutaway carry emotion or clue when safer?
[ ] Did faces come from turnaround/reference images, not the storyboard board?
[ ] Did I include dialogue timing, actor performance, BGM, SFX, environment, props, and continuity?
[ ] Did I keep Chinese storyboard labels when labels are needed?
```
