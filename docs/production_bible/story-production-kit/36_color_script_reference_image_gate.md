# Color Script Reference Image Gate

Purpose: lock the episode color direction before storyboard splitting, image
generation, and Jimeng / Seedance video prompting.

This file controls `색도`, color script, tone board, lighting palette, and
reference-image consistency for `《棺中檀色》`.

## 1. Core Rule

Before making any split storyboard, storyboard reference board, clean keyframe,
or video prompt, first confirm whether the episode or CUT already has an
approved color script.

```text
No approved color script = do not proceed to final split storyboard / image prompt / video prompt.
```

The color script is not decoration. It is a continuity lock.

It must match:

```text
episode theme
current story emotion
location logic
time of day
previous CUT ending
next CUT transition
character temperament
genre identity
```

## 2. Source Order

When creating the color script, use this order:

```text
1. User's latest instruction.
2. The actual storyboard / shot sequence / 분진 source.
3. Episode theme and current story function.
4. Worldbuilding and character rules.
5. Location, prop, weather, time, and sound logic.
6. Reference video analysis as support only.
```

Never create a color script from production-bible theory alone. The real 분진
source must be checked first.

## 3. Required Color Script Card

For each episode or major location block, create a short color script card:

```markdown
## Episode / CUT Color Script Card

- Source file:
- Episode / CUT:
- Story theme:
- Emotional temperature:
- Location:
- Time / weather:
- Dominant colors:
- Supporting colors:
- Forbidden colors:
- Lighting:
- Contrast:
- Saturation:
- Texture:
- Character color notes:
- Prop color notes:
- Transition from previous CUT:
- Transition to next CUT:
- Approved reference image:
- Lock status: DRAFT / APPROVED
```

Do not mark `APPROVED` unless the color choice is checked against the source
storyboard and theme.

## 4. Color Deviation Ban

After a color script is approved, all later outputs must follow it.

This applies to:

```text
storyboard split
storyboard reference board
clean keyframe
Jimeng prompt
Seedance prompt
Liblib / LibTV prompt
CapCut edit notes
```

Forbidden:

```text
changing the scene into a random blue/orange film look
turning grounded urban suspense into fantasy glow
using purple/blue gradients without source reason
using bright commercial lighting in a tense old-house scene
making each CUT look like a different location or genre
changing the palette because the model output looks prettier
```

If a later CUT needs a color shift, explain:

```text
Original color script / Required change / Story reason / Continuity risk
```

Wait for user approval before changing the color standard.

## 5. Reference Image Requirement

After the color script is approved, create one accurate color reference image
for the episode or CUT block.

This image is used as a video-production reference image.

It must show:

```text
approved palette
lighting direction
contrast level
saturation level
location atmosphere
key prop color state
character color relationship when needed
```

It must not redesign:

```text
character faces
character outfits
body proportions
canon props
location logic
story event order
```

If character faces are risky, use faceless/blocking mode. The color reference
image is for color, lighting, atmosphere, and continuity, not for redesigning
characters.

## 6. Storyboard Split Workflow

When the user provides a 분진 source:

```text
1. Extract source facts.
2. Identify episode / CUT theme.
3. Build color script card.
4. Check whether the color script fits the theme.
5. Ask for approval if the palette changes the mood or continuity.
6. Generate one color reference image prompt.
7. Only then produce split storyboard / image prompts / video prompts.
```

Do not create final split storyboard first and color later. Color is part of the
shot logic.

## 7. Video Prompt Color Lock

Every video prompt must include a compact color lock:

```text
Color lock: follow the approved episode color script and approved color reference image. Keep the same palette, lighting, contrast, saturation, and location atmosphere. Do not change the scene into a new color style.
```

For Jimeng / Seedance compressed prompts, shorten it to:

```text
色彩锁定：遵循已批准色彩参考图，保持同一色调、光线、饱和度和场景气氛，不切换风格。
```

## 8. Self Check

Before outputting any final storyboard/image/video prompt, check:

```text
[ ] Did I read the actual 분진 / shot sequence source first?
[ ] Did I create or find the approved color script?
[ ] Does the palette match the story theme and emotional state?
[ ] Did I mark forbidden colors and forbidden lighting?
[ ] Did I generate or reference one approved color reference image?
[ ] Did every later prompt follow the same color lock?
[ ] Did I avoid turning the scene into a different genre or location?
```

If any answer is no, stop and fix the color script before continuing.
