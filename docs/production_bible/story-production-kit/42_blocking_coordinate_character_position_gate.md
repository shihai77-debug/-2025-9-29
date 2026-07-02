# Blocking Coordinate And Character Position Gate

Purpose: make storyboard / 分镜 / video prompt production use clear character
positioning, coordinates, movement paths, and reference-image handoff.

This file controls what to do when a 分镜 already has coordinates and what to do
when it does not.

Works with:

```text
37_colored_background_prop_split_gate.md
39_expert_video_prompt_method_extraction.md
40_video_prompt_scene_input_card.md
41_max_quality_image_dialogue_voice_and_legacy_cleanup.md
```

## 1. Core Rule

Coordinates and character position rules are a filming support layer. They help
AI understand space, but they must not rewrite story content.

They may define:

```text
origin point
X / Y / Z axis
landmarks
character start position
character end position
movement path
camera side / angle
prop location
hidden / visible object state
foreground / midground / background layer
next CUT handoff position
```

They may not change:

```text
event order
speaker
dialogue
character identity
relationship logic
hidden reveal timing
plot outcome
confirmed source blocking
```

## 2. If 分镜 Already Has Coordinates

When a 分镜 already includes coordinate or blocking rules, preserve them as the
highest filming-space source.

Allowed:

```text
reformat into a clearer table
convert coordinates into prompt language
add missing camera-facing notes
add missing foreground / midground / background layers
add hidden-prop state
add next CUT handoff
```

Not allowed without user approval:

```text
move a character to a different side
change distance relationship
change who faces whom
change entrance / exit direction
change which prop is visible
change who leads the frame
```

## 3. If 分镜 Lacks Coordinates

If a 分镜 or CUT has no clear coordinates, Codex must create an AUTO BLOCKING MAP
before final image or video prompts.

Required order:

```text
1. Read the full 分镜 / shot sequence source, not only one CUT.
2. Extract stable location landmarks.
3. Choose one origin point tied to the scene.
4. Define X / Y / Z axes.
5. Place each character by source logic.
6. Mark every inferred position as ASSUMED / NEEDS USER APPROVAL.
7. Preserve all source event order and dialogue.
8. Use the map in split images and video prompts.
```

If the source does not support a clear inference, ask the user instead of
pretending certainty.

## 4. AUTO BLOCKING MAP Format

Use this format:

```markdown
## AUTO BLOCKING MAP

- Source:
- Location:
- Origin point (0,0):
- X axis:
- Y axis:
- Z axis:
- Fixed landmarks:
- Camera-safe master direction:
- Hidden / forbidden zones:

| Character / Prop | Start Position | End Position | Movement | Facing / Eyeline | State | Confidence |
|---|---|---|---|---|---|---|
| LU |  |  |  |  |  | explicit / assumed |
```

Confidence must be either:

```text
explicit
inferred from source
ASSUMED / NEEDS USER APPROVAL
```

## 5. Per-CUT Blocking Card

Every CUT converted to a final video prompt should have a compact blocking card.

```markdown
## CUT Blocking Card

- CUT:
- Scene type:
- Camera purpose:
- Frame start:
- Character positions:
- Character movement:
- Prop positions:
- Hidden props / forbidden reveals:
- End frame / next CUT handoff:
- Reference images used:
```

This card should be created before the 39-layer final video prompt.

## 6. Character Position And Identity Lock

Positioning must include character identity locks.

For `《棺中檀色》`, always track:

```text
LU = 陆沉舟
SHEN = 沈泊川
HAN = 韩知玄
TAN = 檀缺
HEIQI = 黑七
```

Character lock examples:

```text
LU: scene leader / field judge; position should support his control of the scene.
SHEN: realistic young man / audience proxy; may stand slightly behind or recoil if source supports it.
HAN: public-duty restraint; formal posture and official spatial distance.
TAN: cold observer; often in shadow / offset position when source supports it.
HEIQI: small black fox body; low ground position; never humanized.
```

Do not use coordinates to make characters visually convenient if it breaks canon
or source logic.

## 7. Reference Image Selection Handoff

After CUT splitting and background / prop image planning, every selected image
must be assigned a role before video prompts are written.

Use this format:

```markdown
## Reference Image Handoff

- Color reference image:
- MASTER BACKGROUND:
- ANGLE SET:
- PROP INSERT SET:
- Character references / 三面图:
- First frame reference:
- Last frame reference:
- Voice references:
- Do not use these references for:
```

Each image must say what it locks:

```text
locks color only
locks location only
locks prop only
locks camera angle only
locks character identity only
locks first frame only
locks last frame only
```

Do not let a background image redesign characters. Do not let a color image
change character costumes. Do not let a prop image change plot reveal timing.

## 8. Video Prompt Reference Lock

When images are selected, share them into the video prompt through a clear
REFERENCE LOCK section.

Required format:

```markdown
[REFERENCE LOCK]
Color ref: <image name> locks palette / light / atmosphere only.
Location ref: <image name> locks space / architecture / camera angle only.
Prop ref: <image name> locks object shape / material / state only.
Character refs: <image names> lock face / hair / outfit / body proportion / silhouette.
First frame ref: <image name> locks opening composition only.
Last frame ref: <image name> locks ending composition only.
Do not use refs to change story, dialogue, character identity, or reveal timing.
```

A final video prompt without this section is incomplete if images were selected.

## 9. Per-CUT Split And Image Decision Workflow

When converting 分镜 to video production:

```text
1. Read full 分镜.
2. Confirm or create blocking coordinate map.
3. Classify each CUT scene type.
4. Decide whether each CUT needs master shot / dialogue shot / reaction / prop insert / action node.
5. Decide image needs: no image / color ref / master background / angle set / prop insert / first frame / last frame.
6. Confirm selected images and their lock roles.
7. Write video prompt with REFERENCE LOCK + blocking card + 39-layer prompt structure.
```

Do not choose images before understanding the full 分镜 geography.

## 10. AI Stability Rules

Coordinate and image handoff should reduce common AI errors:

```text
character drifting between panels
same place becoming two locations
hidden prop appearing too early
3+ faces breaking in one frame
HEIQI becoming human / dog / wolf / cat
camera direction flipping between CUTs
props changing state between shots
```

If a CUT has more than two clear human faces, use a master/blocking shot or
faceless / back-view / silhouette reference unless the user approves the risk.

## 11. EP21 Compatibility Note

EP21 already has a useful coordinate method:

```text
origin = iron door center
X axis = west/east
Y axis = outward corridor direction
Z axis = height
LU west, SHEN east, HEIQI low near LU, TAN southwest shadow
```

Future episodes should use this level of clarity when possible.

## 12. Self Check

Before final split image or video prompt output:

```text
[ ] Did I read the full 分镜 before creating coordinates?
[ ] Did I preserve any existing source coordinates?
[ ] If missing, did I create AUTO BLOCKING MAP and mark assumptions?
[ ] Did each CUT have a blocking card?
[ ] Did I decide image needs after reading the full scene?
[ ] Did I label each selected image by what it locks?
[ ] Did the final video prompt include REFERENCE LOCK?
[ ] Did I preserve source event order, dialogue, and reveal timing?
```
