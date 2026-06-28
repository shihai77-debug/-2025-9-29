# Smart Prompt Execution Protocol｜智能执行协议

This file is mandatory for storyboard prompts, clean keyframe prompts, Jimeng prompts, Seedance prompts, and any prompt extracted from an approved board.

The goal is not to obey text mechanically. The goal is to execute the source intelligently while preserving locked story content.

## Viewer-First Director Mindset

Before deciding to split, extend, hold, or change camera execution, think like a director serving the audience.

Ask these questions first:

```text
Will viewers understand where to look?
Will viewers feel the character's emotion, not just receive information?
Does this split make the scene more immersive, or does it chop the emotion apart?
Would a real director hold this silence instead of cutting?
Would a real director protect the actor's face for this line?
Would a real director move to hands/props/environment because the clue matters more than the face?
Does the supporting actor need a reaction beat so the scene feels alive?
Does the audio help the line land, or is it filling space?
Is this beat useful silence, or dead air that will make viewers leave?
If the draft storyboard is messy, what is the cleanest cinematic way to preserve the story?
Can viewers understand where each character starts, moves, stops, and looks?
```

Do not over-split.

```text
Split only when the shot function changes, the acting needs protection, the face will break, the dialogue is too dense, the action fights the line, the movement cannot be held clearly, or the story needs a reaction/cutaway.
Hold the shot when silence, grief, pressure, eye contact, or spatial tension is the point.
Use camera movement inside one shot when the same emotional beat continues and only the viewpoint changes.
```

Every CUT must choose one execution verdict before prompt writing:

```text
1. Keep and hold: original shot works; protect timing, acting, position continuity.
2. Smart adjustment: same CUT, improved shot size/camera/audio/acting/movement clarity.
3. Split or extend: original execution will likely fail; use multiple nodes or longer duration.
4. Compress / merge / replace: original beat has value but wastes rhythm or is visually weak.
5. Pass proposal: original beat has no dialogue, no emotion, no new information, no prop/position/continuity value; ask user approval before skipping.
```

The standard is not "more detailed prompts". The standard is:

```text
Would the viewer want to keep watching?
Would the actor feel alive?
Would the edit feel intentional?
Would the sound let the dialogue breathe?
Would the character movement make spatial sense?
```

## Execution Order

Before writing the final prompt, complete this order:

```text
1. Source extraction
   Read exact CUT dialogue, speaker, BGM, SFX, environment sound, duration, props, emotional direction, character movement requirements, and continuity anchors from outputs/episode20_final_cut_source_index.md.

2. Board extraction
   Read only blocking, screen position, camera path, prop placement, movement direction, spatial continuity, and timing structure from the approved storyboard board.
   Do not read board labels as dialogue.
   Do not use board faces/outfits as final character appearance.

3. Reference lock
   Use turnaround sheets / role references for face, hair, outfit, body, silhouette, age, and temperament.
   Use @沈泊川角色参考图, never @Shen角色参考图.

4. Risk diagnosis
   Check dialogue density, face stability, 3+ character risk, action plus speech conflict, prop handoff risk, audio balance, wooden supporting-actor risk, duplicate-character risk, identity-confusion risk, position drift, missing movement path, dead air, weak empty beats, rhythm damage, and unnecessary shots.

5. Flow pacing diagnosis
   Decide whether each weak/silent beat should be KEEP, COMPRESS, MERGE, REPLACE, or PASS_PROPOSAL according to outputs/flow_pacing_edit_decision_rules.md.

6. Dialogue timing fit audit
   For every spoken line, compare assigned seconds against natural speech length, breath, pause, lip-sync, listener reaction, and simultaneous action.
   If unsafe, do not keep the literal timing; extend, split nodes, use cutaway support, or recommend separate dubbing/TTS.

7. Movement position continuity audit
   For every visible character, compare start position, end position, screen percentage, depth layer, body direction, gaze direction, movement path, locked status, and next-node continuity.
   If unsafe, do not keep vague blocking; add 人物位置连续表, 人物移动表, 镜头与人物运动关系, or split the shot.

8. Storyboard-video timing bridge
   Separate storyboard panel / visual beat duration, source CUT duration, and final video node duration.
   If they differ, state KEEP_SOURCE / COMPRESS / EXTEND / SPLIT_NODES / MERGE / REPLACE / PASS_PROPOSAL before writing the prompt.

9. Filming decision
   Decide whether to keep original duration, compress, merge, propose pass/skip with user approval, extend duration, split into multiple video nodes, use master/dialogue/reaction/cutaway, use faceless/blocking master, or request missing source material.

10. Prompt writing
   Write the final prompt only after the filming decision.
   Preserve story, but optimize filming execution.

11. Self-repair
   If any dialogue, BGM, SFX, character count, prop state, continuity anchor, actor delivery, timing fit, timing bridge, movement path, position table, face stability, flow pacing, or audio mix layer is missing, fix the prompt before output.
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
character start/end position clarity.
movement path clarity.
breath before dialogue.
mid-line pause.
listener reaction.
prop cutaway.
audio ducking and transition.
compressing weak movement.
merging repeated beats.
replacing weak empty shots with useful cutaways.
pass/skip proposal after user approval.
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
position drift or teleporting.
missing start/end position.
missing movement path.
camera movement confused with character movement.
locked characters frozen without micro acting.
identity confusion.
dead air with no emotion/story/continuity value.
empty shot that breaks rhythm or atmosphere.
unsafe dialogue timing.
storyboard seconds treated as final video seconds without bridge judgment.
```

Instead, propose and execute a smarter filming plan.

## Movement Position Intelligence

Background continuity is not character continuity.

```text
Every visible character needs start position, end position, depth layer, body direction, gaze direction, movement status, allowed action, and forbidden action.
If a character is locked, they do not walk; only micro acting is allowed.
If a character moves, write start -> path -> end, speed, distance/steps, and whether camera follows them.
Camera path and character path are separate.
Previous node endpoint must equal next node startpoint unless the source explicitly says offscreen movement.
```

Mandatory output when movement/position matters:

```text
人物位置连续表：
人物移动表：
镜头与人物运动关系：
```

If these are missing from a video prompt, the prompt is incomplete.

## Timing Bridge Intelligence

Storyboard board seconds and final video node seconds are different layers.

```text
分镜图秒数 = visual beat / blocking reference time.
原文CUT秒数 = source story timing.
视频节点秒数 = final generation duration.
```

Mandatory output when a video prompt is made from a storyboard board:

```text
分镜-视频时间桥接表：
原文CUT时长：
分镜图标注时长：
分镜图秒数性质：visual beat only / approved video duration
台词自然表演所需时长：
最终视频节点时长：
采用原因：
是否改变原文时长：否 / 是，原因
```

If a board says 3-4s but the source says 6s, keep 6s unless compression is explicitly approved by flow pacing and dialogue timing audits.

## Flow And Pacing Intelligence

Do not keep a beat only because it exists in the draft.

```text
Keep useful silence.
Compress weak movement.
Merge repeated beats.
Replace weak empty shots with short cutaways.
Propose pass/skip only when the beat has no dialogue, no emotion, no new information, no prop/position change, and no continuity value.
```

Never pass/skip automatically.

## Multi-Character Rule

```text
At most two clear human faces per generated storyboard panel, clean keyframe, or video node.
3+ clear human faces = high face-break risk.
3+ characters may appear only in faceless/blocking master shots.
Important dialogue must move to a 1-person or 2-person dialogue shot.
Supporting characters must receive reaction shots or micro-reaction directions.
```

## Dialogue Timing Intelligence

Do not force long dialogue into a short clip.

```text
short line: 1.5-3 seconds plus breath/pause.
medium line: 3-6 seconds plus breath/pause.
long line: 6-10 seconds plus breath/pause.
information-heavy exposition: 8-12 seconds or split into multiple nodes.
two exposition lines in one CUT: usually 16-20 seconds or split into two nodes.
```

Mandatory behavior:

```text
If a line does not fit naturally, never output the unsafe original seconds.
Use EXTEND, SPLIT_NODES, CUTAWAY_SUPPORT, or VOICE_SEPARATE.
State 台词时长适配 in the final video prompt unless the user asks for prompt-only; even then, apply it silently.
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
[ ] I asked whether the shot should hold, adjust, split, extend, compress, merge, replace, or pass-propose.
[ ] I checked if the original duration can carry the dialogue.
[ ] I split or extended if needed.
[ ] I did not preserve unsafe original timing after finding dialogue overflow.
[ ] I separated storyboard visual beat seconds from source CUT duration and final video node duration.
[ ] I ran movement position continuity audit.
[ ] I included every visible character's start/end position and movement status.
[ ] I separated camera path from character path.
[ ] I prevented character teleporting, drifting, or order changes.
[ ] I gave locked characters micro acting instead of wooden stillness.
[ ] I did not over-split a silence/emotion/pressure beat.
[ ] I did not keep dead air just because it exists in the draft.
[ ] I kept max two clear human faces per generated node.
[ ] I prevented duplicate characters and lookalikes.
[ ] I prevented 檀缺/白清檀, 沈泊川/韩知玄, 陆沉舟/沈泊川 confusion.
[ ] I preserved prop state and handoff state.
[ ] I included actor-style delivery.
[ ] I included audio mix hierarchy.
[ ] I included continuity anchors.
[ ] I did not pass/skip anything without user approval.
```

## Output Behavior

If the user asks for diagnosis, show:

```text
导演诊断：
观众体验判断：
节奏判断：KEEP / COMPRESS / MERGE / REPLACE / PASS_PROPOSAL
台词时长适配：
分镜-视频时间桥接表：
人物位置连续判断：
风险点：
执行判定：keep and hold / smart adjustment / split or extend / compress / merge / replace / pass proposal
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
人物要站得住、动得清楚。
表演要像人。
镜头要能剪。
声音要能听。
观众要想继续看。
```
