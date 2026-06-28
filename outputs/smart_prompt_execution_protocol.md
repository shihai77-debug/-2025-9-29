# Smart Prompt Execution Protocol｜智能执行协议

This file is mandatory for storyboard prompts, clean keyframe prompts, Jimeng prompts, Seedance prompts, and any prompt extracted from an approved board.

The goal is not to obey text mechanically. The goal is to execute the source intelligently while preserving locked story content.

## Execution Order

Before writing the final prompt, complete this order:

```text
1. Source extraction
   Read exact CUT dialogue, speaker, BGM, SFX, environment sound, duration, props, emotional direction, and continuity anchors from outputs/episode20_final_cut_source_index.md.

2. Board extraction
   Read only blocking, screen position, camera path, prop placement, movement direction, spatial continuity, and timing structure from the approved storyboard board.
   Do not read board labels as dialogue.
   Do not use board faces/outfits as final character appearance.

3. Reference lock
   Use turnaround sheets / role references for face, hair, outfit, body, silhouette, age, and temperament.
   Use @沈泊川角色参考图, never @Shen角色参考图.

4. Risk diagnosis
   Check dialogue density, face stability, 3+ character risk, action plus speech conflict, prop handoff risk, audio balance, wooden supporting-actor risk, duplicate-character risk, and identity-confusion risk.

5. Filming decision
   Decide whether to keep original duration, extend duration, split into multiple video nodes, use master/dialogue/reaction/cutaway, use faceless/blocking master, or request missing source material.

6. Prompt writing
   Write the final prompt only after the filming decision.
   Preserve story, but optimize filming execution.

7. Self-repair
   If any dialogue, BGM, SFX, character count, prop state, continuity anchor, actor delivery, face stability, or audio mix layer is missing, fix the prompt before output.
```

## Locked Content

Never change:

```text
exact dialogue.
speaker.
event order.
character relationship.
character personality logic.
BGM / SFX / environment source.
key prop state.
continuity anchor.
```

## Director-Editable Execution

The director may optimize:

```text
video node count.
node duration.
shot size.
camera angle.
who is shown first and who reacts later.
master shot / dialogue shot / reaction shot / cutaway split.
action node versus speaking node split.
breath before dialogue.
mid-line pause.
listener reaction.
prop cutaway.
audio ducking and transition.
```

## Hard Intelligence Rule

If the literal CUT would create any of the following, do not output the literal prompt:

```text
rushed narration.
broken lip sync.
blurry or drifting faces.
duplicated characters.
3+ clear human faces in one generated frame.
wooden supporting actors.
action and exposition fighting each other.
BGM/SFX covering dialogue.
missing source dialogue or missing source audio.
prop continuity error.
identity confusion.
```

Instead, propose and execute a smarter filming plan.

## Multi-Character Rule

```text
At most two clear human faces per generated storyboard panel, clean keyframe, or video node.
3+ clear human faces = high face-break risk.
3+ characters may appear only in faceless/blocking master shots.
Important dialogue must move to a 1-person or 2-person dialogue shot.
Supporting characters must receive reaction shots or micro-reaction directions.
```

Recommended split:

```text
5 characters -> faceless master / 2-person action or dialogue / 2-person reaction / fox or prop cutaway.
4 characters -> faceless master / 2-person shot / 2-person reaction.
3 characters -> 2-person shot / 1-person reaction, or faceless 3-person master only.
```

## Dialogue Intelligence

Do not force long dialogue into a short clip.

```text
short line: 1.5-3 seconds plus breath/pause.
medium line: 3-6 seconds plus breath/pause.
long line: 6-10 seconds plus breath/pause.
information-heavy exposition: 8-12 seconds or split into multiple nodes.
```

Every spoken line must feel performed, not read:

```text
pre-line breath.
clear target gaze.
natural phrase grouping.
keyword emphasis.
mid-line pause.
tail sound control.
listener reaction after the line.
voice volume continuity across CUTs.
```

## Audio Intelligence

Use source audio only. Do not invent new music or effects.

```text
voice > core SFX > environment sound > BGM.
Dialogue segment: BGM ducks low.
Core SFX: synchronized to action, never covering first consonant or final tail sound.
Environment: low, continuous, spatial.
BGM: follows source index and transitions smoothly.
```

## Required Hidden Self-Check

Before final output, silently verify:

```text
[ ] I read the source index first.
[ ] I did not create or rewrite dialogue.
[ ] I did not delete BGM/SFX/environment from the source.
[ ] I did not treat board labels as dialogue.
[ ] I did not use board faces as appearance reference.
[ ] I ran director diagnosis.
[ ] I checked if the original duration can carry the dialogue.
[ ] I split or extended if needed.
[ ] I kept max two clear human faces per generated node.
[ ] I prevented duplicate characters and lookalikes.
[ ] I prevented 檀缺/白清檀, 沈泊川/韩知玄, 陆沉舟/沈泊川 confusion.
[ ] I preserved prop state and handoff state.
[ ] I included actor-style delivery.
[ ] I included audio mix hierarchy.
[ ] I included continuity anchors.
```

## Output Behavior

If the user asks for diagnosis, show:

```text
导演诊断：
风险点：
建议执行方式：
最终提示词：
```

If the user asks for prompt only, hide the diagnosis but still apply it.

Final rule:

```text
Do not be a prompt copier.
Be a source-locked director.
故事不乱改。
拍法要聪明。
表演要像人。
镜头要能剪。
声音要能听。
观众要想继续看。
```
