# Colored Background And Prop Split Gate

Purpose: control how storyboard split reference images are created after the
color script is approved.

This rule changes the reference-image workflow:

```text
Old mode: black-and-white storyboard board with characters.
New mode: color-locked background / prop / camera reference images, usually without characters.
```

The goal is to help video generation keep the same space, props, camera logic,
and color script without confusing character faces, outfits, or body positions.

## 1. Core Rule

When the user provides a 분진 / shot sequence source, read the entire source
first. Do not make background images CUT by CUT before understanding the whole
location and continuity.

Required order:

```text
1. Read the full 분진 / shot sequence source.
2. Confirm story theme and color script.
3. Decide whether the background should be one overall master background, several camera-angle background references, or prop insert references.
4. Create color-locked background / prop reference image prompts.
5. Keep character movement, position, and acting in the video prompt, not in the background image.
```

## 2. No Character In Split Images By Default

For split reference images, do not include characters by default.

Use background / prop-only images for:

```text
location geography
door / corridor / room / street layout
object state
lighting direction
camera angle
color script
atmosphere
continuity between CUTs
```

Character action belongs in:

```text
video prompt
actor blocking note
camera movement note
dialogue / voice prompt
```

Only include a character silhouette when the user explicitly asks, or when scale
is impossible to understand without a neutral placeholder. If used, it must be:

```text
faceless, generic, no identity, no costume redesign, no face, no acting detail
```

## 3. Color, Not Black-And-White

After the color script is approved, split reference images must be colored.

```text
All split reference images must follow the approved color script.
No black-and-white storyboard style unless the user explicitly asks for storyboard-only planning.
No random palette shift between CUTs.
No new genre color style in the next split image.
```

The reference image is used for video generation, so it must show the actual
color, lighting, saturation, contrast, and texture direction.

## 4. Background Split Decision

After reading the full 분진, choose one of these modes:

```text
MASTER BACKGROUND: one continuous location image covers the whole scene.
ANGLE SET: same location split into camera-angle references.
PROP INSERT SET: key objects need close-up reference images.
HYBRID: master background + angle refs + prop inserts.
```

Do not split the background just because the CUTs are split. Split only when the
camera, prop state, or spatial continuity requires it.

## 5. Continuity Lock

All background / prop reference images from the same location block must match:

```text
same architecture
same door / window / wall / floor logic
same prop position unless source changes it
same time of day
same weather
same lighting direction
same color script
same atmosphere
```

Forbidden:

```text
one CUT looks like a mountain wilderness and the next like a city road unless source says location changes
same old house door changes material or direction without source reason
prop appears in one image and disappears in the next without source reason
color temperature changes randomly between split images
different background style because each image was prompted independently
```

## 6. Output Format

When making split background references, output this first:

```markdown
## Background / Prop Split Decision

- Source:
- Location block:
- Color script:
- Chosen mode: MASTER BACKGROUND / ANGLE SET / PROP INSERT SET / HYBRID
- Reason:
- Continuity anchors:
- Forbidden deviations:
```

Then make each reference prompt:

```markdown
### BG-XX / PROP-XX

- Used by CUTs:
- Purpose:
- Camera angle:
- Frame:
- Background / prop content:
- Color lock:
- Continuity anchors:
- Must not include:
- Image prompt:
```

## 7. Video Prompt Link

Every later video prompt must refer back to the approved background / prop image:

```text
Use approved BG-XX / PROP-XX as the environment and color reference. Character movement, acting, and position follow the video prompt, not the background image. Keep the background continuous and do not create a new location.
```

For Jimeng / Seedance compressed prompts:

```text
参考已批准BG-XX作为环境和色彩参考，人物动作按本提示执行，背景保持同一空间，不切换地点、不改变色调。
```

## 8. Self Check

Before outputting background split prompts, check:

```text
[ ] Did I read the full 분진 source first?
[ ] Did I use the approved color script?
[ ] Did I decide master / angle / prop / hybrid before prompting?
[ ] Did I keep characters out of split images by default?
[ ] Did I keep character action in the video prompt?
[ ] Did I preserve location continuity between CUTs?
[ ] Did I prevent random background or palette changes?
```

If any answer is no, stop and revise before making images or video prompts.
