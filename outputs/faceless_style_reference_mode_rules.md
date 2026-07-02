# Faceless Style Reference Mode

Use this mode for storyboard reference boards and intermediate planning images
when exact face generation is unstable.

This is not a final video face rule. It is a safer reference-image mode that
keeps identity through silhouette, hairstyle, outfit, body proportion, posture,
screen position, and movement direction while avoiding broken facial details.

## Use When

Use this mode when:

- generated faces drift, shake, melt, or mix characters.
- storyboard boards produce wrong faces even with turnaround sheets.
- the image is mainly for blocking, actor position, camera path, props, and continuity.
- a wide master shot contains three or more characters.
- Jimeng / Seedance will still receive character turnaround sheets in the final video prompt.

## Core Visual Rule

The character is visible, but facial features are intentionally simplified.

Allowed:

- face outline.
- head shape.
- hair silhouette.
- hairstyle from turnaround sheet.
- side/back/three-quarter head direction.
- soft face plane with no detailed eyes, nose, or mouth.
- light sketch-like person rendering.
- clear outfit, body proportion, posture, and position.

Not allowed:

- detailed eyes.
- detailed nose.
- detailed mouth.
- expressive realistic face close-up.
- different face from turnaround sheet.
- random beautiful face.
- face copied from another character.
- blurred blob body with no hairstyle or costume identity.

## Character Identity Lock

Even without facial features, character identity must remain clear.

Use the turnaround sheets / 三面图 for:

- hairstyle and hair volume.
- hair length and silhouette.
- outfit cut, coat length, skirt/pants shape, boots, bag, uniform marks.
- body proportion and height relationship.
- temperament through posture.
- recurring props.

Character locks:

```text
LU / 陆沉舟: modern black leather jacket, black T-shirt, dark pants, boots; calm field leader.
SHEN / 沈泊川: realistic young cleaning-company boss; motorcycle/backpack when source requires; must not look like 韩知玄.
HAN / 韩知玄: 镇灵司 uniform, public-duty restraint, official posture; must not look like 陆沉舟.
TAN / 檀缺: dark modern daily clothing, restrained protector energy; must not become 白清檀.
HEIQI / 黑七: small black fox body, four legs, black fur, pointed ears, long tail; never human, wolf, dog, cat, or fox-boy.
白清檀: black clothing, queen identity, cold restrained presence; never white-robed ghost styling.
```

## Image Style

For storyboard/reference images:

```text
black-and-white or low-saturation cinematic storyboard sketch.
16:9 video frame composition.
clear blocking, screen position, camera direction, movement arrow, and short labels.
simple face planes, no detailed facial features.
high readability of silhouette, outfit, prop, and spatial relation.
```

Do not let faceless style become abstract blobs. The board must still show who
is who through clothing, body shape, posture, and position.

## Blocking And Acting Rule

Faceless style does not mean no acting.

Acting must still be shown through:

- head direction.
- eye-line direction indicated by head angle, not detailed eyes.
- shoulder tension.
- hand position.
- breath posture.
- body lean.
- distance between characters.
- prop handling.
- micro movement notes and arrows on storyboard boards.

Write acting as body performance:

```text
show silent grief through a still seated body, lowered shoulders, and a far head angle.
show caution through a stopped hand, half-step back, and head turning toward the sound.
show listening stillness through fixed feet, slight chest breath, and head angled toward the speaker.
```

## When Not To Use

Do not use this mode as the only source for:

- final dialogue close-up.
- final lip-sync face.
- exact emotional facial performance.
- final clean keyframe when a clear speaker face is required.

For important dialogue, still create a clean keyframe or face lock image from
the turnaround sheet.

## Prompt Snippet

Use this snippet in storyboard/reference image prompts when face accuracy is
failing:

```text
Faceless storyboard reference mode: keep each character identity through silhouette, hairstyle, outfit, body proportion, posture, screen position, and movement direction. Simplify facial features into soft face planes with no detailed eyes, nose, or mouth. Do not redesign the characters. The board is only for blocking, camera path, actor position, and continuity. Final video faces must follow the character turnaround sheets.
```

Negative prompt:

```text
detailed face, realistic close-up face, wrong face, random beautiful face, copied face, extra character, duplicated character, humanized black fox, wolf, dog, cat, fox-boy, blurred blob body, missing hairstyle, missing outfit identity
```

## Final Video Prompt Reminder

When using this reference board for Jimeng / Seedance:

- state that the board is only for blocking and position.
- state that final faces must follow the character turnaround sheets / 三面图.
- if exact face is needed, use `outputs/exact_face_style_mode_rules.md`.
- if the shot is a master shot or action node, the faceless reference board is acceptable.
- if the shot is a dialogue shot, use a clean keyframe with speaker face large enough.
