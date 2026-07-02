# Video Prompt Scene Input Card

Purpose: prevent vague video-prompt requests. Use this card whenever the user
asks for Jimeng / Seedance / Kling / Liblib / LibTV video prompts from a novel,
분진, CUT, storyboard, or reference prompt.

This file works with:

```text
36_color_script_reference_image_gate.md
37_colored_background_prop_split_gate.md
38_reference_prompt_rebuild_camera_video_gate.md
39_expert_video_prompt_method_extraction.md
```

## 1. Minimum User Input

If the user gives only one scene, ask for or extract these fields first:

```text
Episode / CUT number:
Source file or pasted source:
Previous CUT ending:
Next CUT handoff:
Must happen in this CUT:
Must not happen in this CUT:
Characters present:
Location:
Exact dialogue source:
Visible props:
Hidden props:
Duration target:
Platform target: Jimeng / Seedance / Kling / Liblib / LibTV
```

If the source already contains these details, extract them instead of asking the
user again.

## 2. Expert Prompt Reference Inputs

When the user wants the high-level expert prompt method, actively check whether
these references exist:

```text
character visual references / 三面图
location reference image
prop reference image
approved color reference image or color card
voice audio reference
first frame image
last frame image
platform target
aspect ratio
duration limit
BGM / no-BGM policy
forbidden reveals
previous / next CUT continuity
```

If a needed reference is missing and affects quality, ask for it directly. Do not
pretend it exists.

## 3. Active Request Rule

Ask the user for missing material when any of these are absent:

```text
No approved color script / color reference image.
No character reference for a face-visible dialogue shot.
No location reference for a stable recurring location.
No prop reference for a plot-critical prop.
No exact dialogue for a speaking node.
No platform target when prompt length and format matter.
No duration target when dialogue timing matters.
No hidden-prop / reveal timing instruction for mystery scenes.
No previous / next CUT connection for continuity scenes.
```

If the user is in a hurry, continue with an assumption only after marking:

```text
ASSUMED / NEEDS USER APPROVAL
```

## 4. Scene Type Selector

Before writing a final video prompt, classify the CUT:

```text
A. static emotional hold
B. dialogue confrontation
C. investigation / clue reading
D. prop reveal / document reveal
E. movement / entrance / exit
F. action / impact / disturbance
G. horror pressure / unseen threat
H. spatial establishing / master background
I. transition / handoff / ending hook
```

Each type changes camera and sound priority.

## 5. Scene Type Rules

### A. Static Emotional Hold

```text
camera: static hold / slow push-in
priority: breath, gaze, silence, tiny movement
sound: low environment bed, no noisy BGM unless source says so
risk: dragging; add one visible change every 3-5 seconds
```

### B. Dialogue Confrontation

```text
camera: clean one-person or two-person dialogue shot
priority: exact dialogue, speaker, listener reaction, eye line
sound: dialogue forward, environment below
risk: 3+ clear faces; split if needed
```

### C. Investigation / Clue Reading

```text
camera: prop insert, hand action, focus pull, over-shoulder
priority: what is noticed, who notices first, why it matters
sound: finger scrape, paper, metal, dust, breath
risk: explanation without action; show touch / gaze / physical evidence
```

### D. Prop Reveal / Document Reveal

```text
camera: controlled insert or reveal angle
priority: exact reveal timing
sound: cloth, zipper, paper, object contact
risk: showing the prop too early; hide until approved beat
```

### E. Movement / Entrance / Exit

```text
camera: lateral follow, rear tracking, foreground occlusion
priority: start position, end position, direction, handoff
sound: footsteps, engine, fabric, space echo
risk: changing geography; use BG reference and direction lock
```

### F. Action / Impact / Disturbance

```text
camera: one clear action, one camera purpose
priority: cause -> impact -> reaction
sound: impact transient, debris, body reaction
risk: too much action in one node; split if action and dialogue collide
```

### G. Horror Pressure / Unseen Threat

```text
camera: door gap, shadow, sound source, reaction face
priority: never reveal the hidden thing early
sound: low rumble, scrape, air pressure, silence cut
risk: AI adding monsters / smoke / effects; forbid them clearly
```

### H. Spatial Establishing / Master Background

```text
camera: wide or high-angle readable blocking
priority: geography, entry/exit route, scale, object positions
sound: environment bed
risk: overpopulated faces; omit characters or use silhouettes if needed
```

### I. Transition / Handoff / Ending Hook

```text
camera: end-frame anchor, empty frame, prop state, sound bridge
priority: what question carries into next CUT
sound: fade, held tone, off-screen cue
risk: ending too soft; leave one sharp unanswered question
```

## 6. Required Output Before Final Prompt

Before the final platform prompt, output this compact audit:

```markdown
## Scene Input Audit

- Source found:
- Canon / character lock:
- Scene type:
- Color script status:
- BG / PROP split status:
- Reference assets available:
- Missing assets to request:
- Dialogue source:
- Timing risk:
- Face stability risk:
- Hidden reveal risk:
- Proceed / pause:
```

If `Proceed / pause` is `pause`, ask for the missing item and do not generate a
final video prompt yet unless the user explicitly says to proceed with
assumptions.

## 7. Final Prompt Assembly

After the audit passes, write the final prompt in the 39-layer order:

```text
STYLE LOCK
REFERENCE LOCK
SOURCE LOCK
SHOT DESIGN
ACTION FLOW
ACTING / VOICE
PROP / REVEAL
SOUND
CONTINUITY
FORBIDDEN
PLATFORM
```

## 8. Compatibility With Existing 分진

When a 分진 already has camera, timing, dialogue, and SFX, do not rewrite it.
Convert it into the 39-layer prompt structure.

Allowed:

```text
reformat
split dense node
add missing reference locks
add color lock
add BG / PROP lock
add sound continuity lock
add forbidden failures
mark missing user inputs
```

Not allowed without user approval:

```text
change event order
change speaker
change confirmed dialogue
change character position
change hidden reveal timing
change ending hook
replace the CUT's purpose
```

## 9. One-Line User Request Template

The user can request a video prompt with this short sentence:

```text
이 CUT을 39번 고수 프롬 구조로 영상 프롬 만들어줘. 부족한 참고자료 있으면 먼저 요구하고, 색도/배경/소품/대사/금지사항까지 확인해줘.
```
