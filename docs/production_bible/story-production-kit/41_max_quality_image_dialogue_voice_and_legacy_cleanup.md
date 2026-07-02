# Max Quality Image, Dialogue Voice, And Legacy Cleanup Rule

Purpose: lock three production behaviors for `《棺中檀色》`:

```text
1. Generate reference images at the maximum available quality.
2. Add AI-readable dialogue voice direction whenever 分镜 / video prompts need speech.
3. Retire old unused camera / video materials only after safe multi-episode validation.
```

This file works with:

```text
36_color_script_reference_image_gate.md
37_colored_background_prop_split_gate.md
39_expert_video_prompt_method_extraction.md
40_video_prompt_scene_input_card.md
jimeng_dialogue_voice_prompt_reference.md
```

## 1. Maximum Quality Image Rule

When using ChatGPT / image generation to create any production reference image,
use the maximum quality available in the current tool or platform.

Applies to:

```text
approved color reference image
MASTER BACKGROUND reference
ANGLE SET reference
PROP INSERT reference
clean keyframe reference
storyboard reference board when image quality matters
CapCut / video-production visual reference
```

Required behavior:

```text
use the highest available image quality / resolution
preserve the requested aspect ratio
avoid compression unless platform requires it
make the image production-readable, not decorative
lock color script, lighting, location, object state, and continuity
```

If the image tool exposes no explicit quality parameter, write the prompt as:

```text
highest available quality, high-resolution production reference, clean readable details, no compression artifacts, stable lighting and material detail
```

Do not generate low-quality reference images for official production unless the
user explicitly asks for quick draft / cheap test.

## 2. Image Quality Does Not Override Canon

High quality does not permit redesign.

Never improve image quality by changing:

```text
character face
age
body proportion
hair
outfit
silhouette
temperament
worldview logic
prop design
location logic
approved color script
```

Character reference sheets / 三面图 remain higher priority than any generated
image's beauty, style, or cinematic appeal.

## 3. Dialogue Voice Direction Rule

Every speaking line in 分镜 or final video prompts must be AI-readable.

A good voice direction tells the video / voice model how the actor should read
the line without rewriting the line.

Required fields:

```text
speaker
exact dialogue
voice / tone
speed
volume
breath state
pause timing
emphasis word
mouth / face visibility
listener reaction
sound mix priority
```

The exact dialogue text must remain unchanged unless the user approves a rewrite.

## 4. Auto Voice Direction When Missing

If a 分镜 contains dialogue but lacks AI voice direction, Codex must create it
automatically when producing video prompts.

Mark it as:

```text
AUTO VOICE DIRECTION
```

This is allowed because it does not change the dialogue. It only adds acting /
voice delivery instructions.

Allowed automatic additions:

```text
tone
speed
pause
breath
emphasis
volume
listener reaction
environment sound under dialogue
```

Not allowed automatically:

```text
rewrite dialogue
shorten dialogue
change speaker
change meaning
change emotional intention from the source
add new plot information
```

## 5. Dialogue Voice Direction Format

Use this compact format in 分镜 / video prompts:

```text
Speaker: [Tone: ...] [Speed: ...] [Volume: ...] [Breath: ...] "exact dialogue" [Pause: ...] [Emphasis: ...] [Listener reaction: ...]
```

For Jimeng / Seedance prompts, the line may be written as:

```text
@角色名 read the exact line in <tone>, <speed>, <breath>, with <pause/emphasis>, while <listener reaction>; keep dialogue clear above environment sound.
```

## 6. Sample: EP21 Style Dialogue Voice Direction

Source line must remain exact:

```text
陆沉舟：这阵不挡人，只困物。寻常凶宅驱人，这里是死死按住门内的东西，不让外泄。
```

AI-readable direction:

```text
陆沉舟: [Tone: calm field judgment, low authority] [Speed: 0.88x] [Volume: low but clear] [Breath: controlled, no panic]
"这阵不挡人，只困物。" [Pause: 0.7s]
"寻常凶宅驱人，" [Pause: 0.3s]
"这里是死死按住门内的东西，不让外泄。" [Emphasis: 死死按住 / 不让外泄]
[Listener reaction: 沈泊川 stops breathing for a beat, eyes fixed on the iron door]
[Sound mix: LU voice stays forward; low door rumble remains under the line]
```

Short Jimeng-style version:

```text
@陆沉舟 低声、冷静、带现场判断感朗读原句，语速0.88x，第一句后停0.7秒，重读“死死按住”和“不让外泄”；沈泊川屏息看向铁门，门内低频声压在台词下方，不盖过人声。
```

## 7. Dialogue Voice Direction By Character

Use canon personality, not generic emotion.

```text
陆沉舟 = scene leader / field judge; calm, controlled, decisive, can explain when story needs it; not a short-line machine.
沈泊川 = realistic young man; fear, questions, survival instinct, quick breath, understandable audience proxy.
檀缺 = cold observer; sharp, economical, often cuts through the situation.
黑七 = small black fox body; sarcastic first, concerned underneath; mouth visibility may be hidden for stability.
韩知玄 = public-duty restraint; formal, controlled, official pressure.
```

## 8. Sound Mix With Dialogue

Do not let environment sound swallow dialogue.

For each speaking node define:

```text
dialogue priority: forward / normal / background
base sound bed: wind / low rumble / city ambience / silence / BGM
foreground action sound: paper / metal / footsteps / engine / fabric
BGM policy: none / low / stop / return
```

If BGM is present, specify whether dialogue must remain clearly intelligible.

## 9. Legacy Camera / Video Material Cleanup Rule

Old unused camera / video rules should not remain active forever, but they must
not be deleted impulsively.

Legacy cleanup begins only after:

```text
3 consecutive approved episode-production cycles use the new 39 / 40 / 41 method successfully
or the user explicitly asks for cleanup now
```

An episode-production cycle means:

```text
source / 분진 reviewed
color script approved
BG / PROP split decided
video prompts generated
test result reviewed
user accepts the method
```

## 10. What Can Be Retired

After validation, old materials may be moved to a legacy archive or deleted only
with user approval.

Can retire:

```text
outdated camera wording notes
old failed prompt templates
duplicate temporary production drafts
old method files marked do-not-use
obsolete test prompts
bad example files kept only for debugging
```

Must keep:

```text
worldbuilding
character cards
character reference sheets / 三面图
approved costume references
approved color scripts
approved BG / PROP references
source manuscripts
confirmed 分镜 / CUT sources
contract / regulation / banned-setting files
self-update logs
review records explaining why a rule changed
```

## 11. Legacy Cleanup Audit Format

Before moving or deleting old material, produce:

```markdown
## Legacy Cleanup Audit

- File / folder:
- Current status:
- Why it is obsolete:
- Replaced by:
- Used in last 3 approved episodes? yes / no
- Contains canon / character / source / approved asset? yes / no
- Action: keep / archive / delete candidate
- Needs user approval: yes / no
```

If any file contains canon, character references, source text, approved visuals,
or legal / contract rules, do not delete it.

## 12. Self Check

Before final image or video prompt output:

```text
[ ] Did I use maximum available image quality for production reference images?
[ ] Did I preserve canon and approved color while increasing image quality?
[ ] Did every dialogue line have AI-readable voice direction?
[ ] If voice direction was missing, did I add AUTO VOICE DIRECTION without changing dialogue?
[ ] Did I keep dialogue clear above SFX / BGM?
[ ] Did I avoid deleting legacy files before 3 approved cycles or user approval?
[ ] Did I protect character references / 三面图 from cleanup?
```
