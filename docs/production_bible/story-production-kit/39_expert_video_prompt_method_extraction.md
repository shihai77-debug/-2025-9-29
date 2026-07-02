# Expert Video Prompt Method Extraction

Purpose: official working method extracted from the user's high-quality expert
video prompt references. This file teaches how to write future `《棺中檀色》`
video prompts.

This method is approved as a prompt-writing standard by the user, but it never
copies the outside prompt's story, characters, setting, palette, dialogue, or
worldbuilding. Only the production method is reused.

## 1. What We Learn

The reference prompts are strong because they do not merely describe a pretty
shot. They lock the whole production chain:

```text
visual style
reference asset mapping
color card
camera grammar
spatial blocking
action progression
actor micro-performance
sound bed
platform format
negative constraints
```

Future video prompts must be built as a shootable scene, not as a mood board.

## 2. Do Not Copy

Never copy from the outside references:

```text
outside characters
outside creature designs
outside place names
outside dialogue
outside worldbuilding
outside plot events
outside color palette
outside cultural setting
outside jokes or catchphrases
```

For `《棺中檀色》`, always use our own:

```text
canon worldview
character cards
episode source / 분진
confirmed dialogue
approved color script
approved BG / PROP references
Jimeng / Seedance platform rules
```

## 3. Master Prompt Structure

Every serious video prompt should follow this order unless the platform requires
a shorter version.

```text
[STYLE LOCK]
Reference asset mapping
Color card lock
Audio policy
Shot / camera entry
Spatial layout
Action beat progression
Actor performance / micro-expression
Prop state and reveal timing
Background continuity
Sound design layering
Hard negatives / failure prevention
Platform output line
```

This order prevents AI drift because the model receives identity, color, space,
action, and sound before it receives decorative language.

## 4. STYLE LOCK Layer

The style lock should be concrete, not vague.

Include:

```text
film texture / lens feeling
aspect ratio
saturation level
lighting direction
contrast logic
time of day
atmosphere density
camera temperament
BGM policy
sound-world policy
```

Bad:

```text
cinematic, beautiful, mysterious
```

Good:

```text
35mm film grain, low-saturation cold urban dusk, soft practical streetlight from frame right, restrained handheld follow, no melodic BGM, only engine / wind / footsteps / dialogue
```

For our drama, never let the style lock erase the approved color script.

## 5. Reference Asset Mapping

The expert references are precise because each image/audio reference has a job.

Use this form:

```text
Image A = character identity anchor
Image B = location anchor
Image C = prop anchor
Image D = color card anchor
Audio A = speaker voice anchor
```

Rules:

```text
Do not say only "refer to image".
Name what the reference locks.
Separate character, location, prop, color, and voice references.
Do not let a location reference redesign characters.
Do not let a color card override canon costume colors unless approved.
```

## 6. Color Card Lock

The biggest usable lesson is strict color discipline.

Future workflow:

```text
1. Read the full 분진.
2. Create / confirm color script.
3. Generate one approved color reference image.
4. Use that image or palette as the color card anchor.
5. Every split BG / PROP image and video prompt must remain inside that color logic.
```

Prompt wording should include:

```text
all colors strictly follow the approved color card
no new palette
no random saturation shift
no unrelated fantasy glow
```

If a prompt needs color change, explain the story reason and continuity risk
before changing it.

## 7. Camera Grammar We Should Use

The expert prompts use exact camera verbs. Future `《棺中檀色》` prompts should
use controlled camera language such as:

```text
static hold
handheld slight shake
lateral follow
slow push-in
rack focus
tilt up
dolly zoom
hard cut
one-shot / 一镜到底
low angle reveal
high-angle blocking view
subjective POV
foreground occlusion
foreground / midground / background depth stack
```

Do not stack too many camera tricks in one short shot. One CUT should have one
main camera purpose.

## 8. Spatial Blocking Method

Always describe the shot as readable space, not only emotion.

Use layers:

```text
foreground
near side
middle distance
far side
deep background
left / right / center
high / low frame position
who faces whom
what blocks or reveals what
```

For background / prop split images, characters are usually omitted. The image
locks space, camera angle, prop state, light, palette, and continuity. Character
position, acting, and dialogue remain in the video prompt.

## 9. Action Beat Progression

The expert prompts are long because each action has a cause and result.

Future prompt writing should use this chain:

```text
start frame anchor
micro-stillness
external disturbance or story trigger
first physical reaction
camera adjustment
second reaction or decision
line delivery / sound accent
end-frame emotional state
```

This prevents empty dragging because every few seconds something changes:

```text
new sound
new gaze
new danger
new prop state
new camera emphasis
new decision
```

## 10. Actor Performance Method

Write performance like a director, not like a summary.

Use:

```text
breath
jaw tension
eye focus
shoulder drop
hand hesitation
half-step back
tiny glance
delayed reaction
voice texture
pause before line
```

Avoid:

```text
he is sad
she is nervous
they are shocked
```

Convert emotion into visible behavior.

For `陆沉舟`, this is especially important:

```text
He is not a silent cool decoration.
He should lead the scene through gaze, timing, blocking, restraint, and decisive speech.
When he speaks, the scene should move.
```

## 11. Dialogue And Voice Layer

Dialogue must remain understandable and character-specific.

Prompt must include:

```text
speaker name / voice anchor when available
exact dialogue if source dialogue exists
speaking speed
breath state
emotional pressure
whether the line is on-screen or off-screen
how environmental sound sits under the line
```

Do not shorten source dialogue without approval. Do not make all lines 3-5
characters. Short lines are useful only when the scene already carries enough
visual information.

## 12. Sound Design Layer

The expert references are strong because sound is treated as story pressure.

For our prompts, define:

```text
BGM: none / white-noise bed / low drone / sparse music
base environment sound
continuous background pressure
foreground action sound
dialogue priority
special sound cue
```

Sound should carry continuity. If a sound starts in one shot, keep or release it
intentionally in the next shot.

## 13. Platform Compression Method

A full Seedance / Jimeng prompt can be detailed. A Kling or short platform prompt
may need a compressed version.

Keep the same core in both:

```text
reference anchors
one camera purpose
one action chain
one sound bed
one end state
hard negatives
```

Compressed prompt must not remove:

```text
character lock
prop state
color lock
location continuity
dialogue speaker
forbidden reveal timing
```

## 14. Negative Prompt / Failure Prevention

Every video prompt should include practical failure prevention, selected from the
actual CUT risk:

```text
do not change character face / outfit / age / silhouette
do not introduce unapproved props
do not reveal documents early
do not split one location into two unrelated places
do not add fantasy glow unless source requires it
do not add BGM if the scene uses only environment sound
do not move locked characters unless the CUT says so
do not swap speaker or dialogue
```

Negatives must be specific. Generic negatives are weaker.

## 15. Our New Video Prompt Template

Use this template for final platform prompts:

```markdown
[STYLE LOCK]
<film texture, aspect ratio, palette, lighting, camera temperament, BGM/sound policy>

[REFERENCE LOCK]
Character refs:
Location refs:
Prop refs:
Color ref:
Voice refs:

[SOURCE LOCK]
Episode / CUT:
Previous CUT connection:
Must happen:
Must not happen:
Dialogue source:

[SHOT DESIGN]
Duration:
Shot size:
Camera:
Frame start:
Spatial layout:
Foreground / midground / background:

[ACTION FLOW]
0-?s:
?-?s:
End frame:

[ACTING / VOICE]
Speaker:
Line:
Delivery:
Non-speaking reactions:

[PROP / REVEAL]
Visible props:
Hidden props:
Reveal timing:

[SOUND]
Base bed:
Foreground sounds:
Dialogue mix:
No BGM / BGM:

[CONTINUITY]
Color:
Location:
Character position:
Object state:
Next CUT handoff:

[FORBIDDEN]
<exact failures to prevent>

[PLATFORM]
<Jimeng / Seedance / Kling format line>
```

## 16. Split Image Method After This Update

For split storyboard / reference images:

```text
Use color, not black-and-white, after the color script is approved.
Do not include characters by default.
Create background / prop / camera-angle references according to the full 분진.
Use one master background if the location stays stable.
Use angle sets only when camera changes need separate references.
Use prop insert images only for props that affect reveal timing or continuity.
```

Character acting and blocking belong in the video prompt unless the user requests
a character storyboard board.

## 17. Self Check Before Final Video Prompt

```text
[ ] Did I read the actual 분진 source first?
[ ] Did I preserve story, dialogue, and character canon?
[ ] Did I use the approved color script / color reference?
[ ] Did I decide BG / PROP split before video prompt?
[ ] Did I extract method only from the expert prompt?
[ ] Did I write one clear camera purpose for the CUT?
[ ] Did I write visible actor behavior instead of abstract emotion?
[ ] Did I lock sound design and dialogue priority?
[ ] Did I include exact forbidden failures?
[ ] Did I keep the end frame useful for the next CUT?
```

If any answer is no, do not generate the final video prompt yet.
