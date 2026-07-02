# EP21 Storyboard Compatibility Check With Rules 39 / 40

Source checked:

```text
episode21_storyboard_draft.md
```

Status of source:

```text
draft, not canon
```

This review checks whether the existing EP21 分镜 can be converted into the
new expert video prompt structure from:

```text
39_expert_video_prompt_method_extraction.md
40_video_prompt_scene_input_card.md
```

## 1. Overall Result

Compatible, but not production-complete yet.

The EP21 storyboard already contains many useful production elements:

```text
CUT numbers
per-CUT duration
fixed blocking coordinates
character positions
dialogue lines
camera intent
SFX / BGM notes
hidden-threat rules
forbidden visual reveals
```

So it can be converted into 39-layer video prompts without changing the story.

However, it still lacks several expert-prompt-level locks:

```text
approved color script
approved color reference image
reference asset mapping
BG / PROP split decision
sound continuity map
platform-specific compressed prompt versions
```

Do not generate final video prompts until these are filled or marked as
ASSUMED / NEEDS USER APPROVAL.

## 2. Strong Compatibility Points

### 2.1 Source / Blocking Is Clear

EP21 has a strong coordinate rule:

```text
iron door center = (0,0)
LU west side, 1m from door
SHEN east side, 1m from door
HEIQI near LU's left heel
TAN 3m back, southwest shadow
```

This matches Rule 39's spatial blocking requirement.

### 2.2 Dialogue Is Already Assigned

Most CUTs have named speakers and exact lines. This supports dialogue
preservation and voice prompting.

### 2.3 Hidden Threat Control Is Good

Repeated restrictions are useful:

```text
no black smoke
hidden thing inside door must not appear
door remains closed
use shadow / sound / vibration instead of visible monster
HEIQI remains small black fox body
```

This matches Rule 40's horror pressure / unseen threat type.

### 2.4 Scene Types Are Easy To Classify

Most CUTs fit the 40 scene selector:

```text
CUT-01 = G horror pressure / unseen threat
CUT-02 = F action disturbance + B confrontation
CUT-03 = C investigation / clue reading
CUT-04 = C investigation explanation + B dialogue
CUT-05 = C clue reading / G unseen threat
CUT-06 = A static emotional hold / G pressure
CUT-07 = B dialogue confrontation
CUT-08 = B dialogue confrontation
CUT-09 = B dialogue confrontation / I hook logic
CUT-10 = B realization
CUT-11 = G unseen threat
CUT-12 = F control action / G pressure
CUT-13 = B short confrontation
CUT-14 = A fear hold
CUT-15 = B pressure dialogue
CUT-16 = B reveal dialogue
CUT-17 = A silent fear close-up
CUT-18 = B supporting pressure
CUT-19 = E exit / I handoff
CUT-20 = I ending hook / G unseen threat
```

## 3. Missing Items Before Final Video Prompts

### 3.1 Approved Color Script Missing

The current storyboard uses generic phrases such as:

```text
cinematic dark lighting
moody shadows
volumetric light
high contrast
```

But it does not lock one EP21 color script.

Need from user or create from source:

```text
EP21 color script card
approved color reference image
allowed accent color for red formation glow
lighting direction
saturation limit
shadow tone
forbidden color drift
```

Recommendation:

```text
Create EP21 老宅/铁门 color script before final split images or video prompts.
```

### 3.2 Reference Asset Mapping Missing

The storyboard does not map references like:

```text
LU character ref
SHEN character ref
TAN character ref
HEIQI black fox ref
iron door / corridor location ref
old red formation pattern prop ref
voice refs
color card ref
```

Need to request or locate these before final prompt.

### 3.3 BG / PROP Split Decision Missing

EP21 likely needs a HYBRID split:

```text
MASTER BACKGROUND = iron door corridor / 老宅 sealed door space
ANGLE SET = door gap macro, floor formation marks, profile confrontation, rear exit, empty door ending
PROP INSERT SET = old red formation pattern, iron door seam, falling dust, wrist-stop contact, fox shadow on wall
```

Characters should usually be omitted from split reference images. Character
movement, acting, position, and dialogue stay in video prompts.

### 3.4 Sound Continuity Map Missing

CUTs include SFX / BGM, but there is no continuous sound map across the full
151 seconds.

Need to decide:

```text
What sound begins in CUT-01 and continues?
Where does BGM stop completely?
Where does ear-ringing replace space sound?
Where does low-frequency pressure return?
Which sounds bridge into CUT-20?
```

Without this, platform prompts may randomly add or drop BGM.

### 3.5 Platform-Specific Versions Missing

EP21 CUTs range from 4s to 13s. Need per-platform handling:

```text
Seedance = detailed 39-layer prompt, can handle more description
Jimeng = stable prompt with exact dialogue / actor / camera / forbidden locks
Kling = compressed prompt, one camera purpose and one action chain
```

CUT-04, CUT-05, CUT-09, CUT-11, CUT-12, CUT-19 are likely long or dense enough
that platform-specific split decisions may be needed.

### 3.6 Draft / Canon Status Needs Approval

The source says:

```text
Status: draft, not canon
```

Before final video prompts, user should confirm whether this draft is the
approved source or still only a draft.

## 4. CUT Risk Notes

### CUT-02

Wide group shot is acceptable if faces are not all clear. If it tries to show
LU, SHEN, TAN, and HEIQI clearly at once, use master/blocking shot rather than
face-stable dialogue shot.

### CUT-04

LU has a long explanation line. It can work at 11s, but the video prompt must
include breathing and pause timing. Do not shorten the line without approval.

### CUT-05

HEIQI voice while fox mouth is not visible is a good stability solution. Keep
mouth hidden and use shadow / sound / posture.

### CUT-10

Tight two-shot is acceptable because only two human faces are clear.

### CUT-11

Unseen threat rule is strong. Prompt must forbid smoke, visible entity, monster
face, arms, claws, or fantasy apparition unless source changes.

### CUT-12

Action and dialogue happen together. Use one clear camera purpose: low-angle LU
control action. Do not add extra character movement.

### CUT-18

Three-person shot can work if only TAN is foreground clear and LU / SHEN stay
background blurred. Otherwise face stability risk rises.

### CUT-19

Exit tracking shot is compatible with expert prompt method. Needs clear direction
lock: all move south away from iron door.

### CUT-20

Strong ending hook. Best treated as empty-frame continuity anchor with sound
bridge.

## 5. Required User Inputs To Request Actively

Before final EP21 video prompts, request:

```text
1. Confirm whether episode21_storyboard_draft.md is now approved source.
2. Approved EP21 color script or permission to create one from the draft.
3. Character reference images / 三面图 locations for LU, SHEN, TAN, HEIQI.
4. Location reference for 老宅铁门 / corridor, if available.
5. Prop references for iron door, old red formation marks, door seam, if available.
6. Voice reference availability for LU, SHEN, TAN, HEIQI.
7. Target platform for first output: Jimeng / Seedance / Kling.
8. Whether final prompts should preserve existing BGM notes or switch to environment-only sound.
```

If the user cannot provide references, mark missing fields as ASSUMED and create
a draft prompt only, not final locked production prompt.

## 6. Verdict

EP21 is structurally compatible with Rules 39 / 40.

It should not be rewritten. It should be converted.

Correct next workflow:

```text
1. Confirm EP21 source status.
2. Create / approve EP21 color script.
3. Create one color reference image.
4. Decide HYBRID BG / PROP split plan.
5. Build reference asset map.
6. Convert each CUT into 39-layer video prompts.
7. Create platform-specific compressed versions.
8. Review prompt result and update only approved lessons.
```
