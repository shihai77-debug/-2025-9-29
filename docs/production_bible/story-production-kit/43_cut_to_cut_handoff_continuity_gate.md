# CUT To CUT Handoff Continuity Gate

Purpose: preserve the most important lesson from the expert video prompts:
shots must connect through visible, audible, emotional, and spatial handoff.

A good CUT is not isolated. Its ending must prepare the next CUT's beginning.

Works with:

```text
39_expert_video_prompt_method_extraction.md
40_video_prompt_scene_input_card.md
42_blocking_coordinate_character_position_gate.md
```

## 1. Core Rule

Before writing final split storyboard, reference image prompts, or video prompts,
identify how each CUT connects to the next CUT.

Every CUT should define:

```text
previous CUT incoming state
current CUT start frame
current CUT end frame
next CUT handoff
sound bridge
object state continuity
character gaze / body direction continuity
camera direction continuity
emotional pressure continuity
```

Do not treat CUTs as separate pretty shots.

## 2. Expert Prompt Lesson

The expert prompts connect cuts through:

```text
HARD CUT after an action beat
sound continuing under the next shot
same low-frequency rumble across shots
same environmental chaos continuing in the background
same direction of gaze into the next POV shot
same prop handed from one person to another
same wet hair / dripping water / body state after an action
same color card across the whole sequence
same geography from wide shot into close-up
reaction shot answering the previous action
end-frame composition becoming next start-frame logic
```

The method is not just camera style. It is cause-and-effect continuity.

## 3. Handoff Types

Use one or more of these when splitting CUTs:

```text
visual handoff = same object, gesture, gaze, position, light, or composition continues
sound handoff = same rumble, wind, engine, footsteps, BGM, silence, or off-screen cue continues
action handoff = one action triggers the next shot
emotion handoff = one character reaction becomes the next shot's focus
space handoff = wide geography becomes close-up or POV while preserving direction
prop handoff = object state changes and carries into next CUT
threat handoff = unseen danger continues through sound / shadow / pressure
dialogue handoff = last line creates next shot's response, silence, or question
```

## 4. Required CUT Handoff Card

Before final video prompts, create this for every CUT:

```markdown
## CUT Handoff Card

- CUT:
- Previous CUT ending:
- Start frame:
- End frame:
- Next CUT starts from:
- Visual handoff:
- Sound handoff:
- Action / emotion handoff:
- Prop state handoff:
- Character position handoff:
- Camera direction handoff:
- Risk if disconnected:
```

This card can be compact, but it cannot be skipped for final prompts.

## 5. Start Frame / End Frame Lock

Each final video prompt must know:

```text
what the first frame inherits
what the last frame leaves behind
```

Use this format inside video prompts:

```markdown
[HANDOFF]
Previous CUT leaves: ...
Start frame inherits: ...
End frame locks: ...
Next CUT receives: ...
Sound bridge: ...
```

If a generated video has a usable first or last frame, name it as:

```text
First frame reference locks opening composition only.
Last frame reference locks ending composition only.
```

Do not let first / last frame references change story, character identity,
dialogue, or reveal timing.

## 6. Sound Bridge Rule

Sound is often the strongest cut connector.

Track:

```text
continuous environment bed
BGM enter / stop / return
low-frequency pressure
silence cut
ear-ringing
engine / footsteps / wind / door rumble
voiceover continuing into next shot
```

If a sound stops, it must stop for a reason. If a sound continues, mark it as a
sound bridge.

Never infer silence from a visually quiet shot.

## 7. Emotion Bridge Rule

The next CUT should usually answer one of these:

```text
Who reacts to the previous line?
Who understands the danger?
Who refuses the action?
Who becomes afraid?
Who takes control?
What question has just been created?
```

Avoid cutting to a new angle only because it looks nice. Cut because the story
pressure moves.

## 8. Space Bridge Rule

When changing shot size or angle, preserve geography.

Required checks:

```text
left / right relationship remains stable
entrance / exit direction remains stable
character distance remains plausible
prop position remains consistent
background does not become a different place
camera axis does not flip unless intentional and explained
```

If the next shot changes from wide to close-up, specify what part of the wide
shot the close-up comes from.

## 9. Prop / Hidden Reveal Bridge Rule

For mystery scenes, track object visibility across CUTs.

Use:

```text
visible now
hidden now
revealed in later CUT
must not appear yet
state after action
```

If a document, bag, door gap, talisman, formation mark, blood stain, footprint,
or other clue carries across cuts, the handoff must name it.

## 10. Dialogue Bridge Rule

Dialogue is not only text. It creates the next shot.

For every line, ask:

```text
Does the next shot show the listener's reaction?
Does the next shot show the evidence behind the line?
Does the next shot show silence after the line?
Does the next shot show the consequence of the line?
```

If none of these happen, the cut may feel disconnected.

## 11. When A CUT Has No Clear Handoff

If the source CUT lacks a clear next connection, do not invent plot. Create a
filming-only bridge:

```text
held sound
continuing gaze
same prop state
same body position
same camera direction
empty frame after exit
reaction silence
```

Mark it as:

```text
AUTO HANDOFF / filming continuity only
```

Do not add new story information without user approval.

## 12. EP21 Application Note

EP21 should use handoffs such as:

```text
CUT-01 door impact sound -> CUT-02 SHEN hand stopped before opening
CUT-02 wrist stop -> CUT-03 LU crouches to inspect the door / floor marks
CUT-04 formation truth -> CUT-05 HEIQI detects cleaned dead energy
CUT-08 cannot break -> CUT-09 explanation of why breaking loses the culprit
CUT-12 LU controls one seam -> CUT-13 HEIQI challenges whether he can control it
CUT-16 truth targets SHEN -> CUT-17 SHEN silent fear close-up
CUT-19 group exits -> CUT-20 empty iron door receives the hook
```

## 13. Self Check

Before final video prompt output:

```text
[ ] Did every CUT have a previous ending and next handoff?
[ ] Did I define start frame and end frame for each video node?
[ ] Did I preserve sound continuity or intentionally stop it?
[ ] Did I preserve spatial direction and character position?
[ ] Did I track prop / hidden reveal state across cuts?
[ ] Did dialogue lead to listener reaction, evidence, silence, or consequence?
[ ] Did I avoid adding new plot while creating AUTO HANDOFF?
```
