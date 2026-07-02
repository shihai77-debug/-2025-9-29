# Repository Agent Rules

This repository is the official production source for the AI short drama
`《棺中檀色》`. Use it for novel work, storyboard/CUT splitting, storyboard
reference boards, clean keyframes, Jimeng/Seedance prompts, continuity checks,
and production self-updates.

Do not treat this file as a replacement for the full rule set. It is the entry
point that tells an agent what to read and how to avoid damaging canon.

## First Read Order

Before writing or splitting any episode, first read the relevant source files
from the current branch.

```text
AGENTS.md
docs/production_bible/00_read_order.md
docs/production_bible/README.md
docs/production_bible/self_update_protocol.md
docs/production_bible/story-production-kit/00_start_here_execution_guide.md
01_세계관_최종설정.md
02_캐릭터_최종설정.md
06_폐기설정_충돌방지.md
07_소설작성_규칙.md
```

For story quality, pacing, dialogue, and director logic, read these when the
task touches novel, storyboard, or video production:

```text
docs/production_bible/story-production-kit/01_reference_video_style_bible.md
docs/production_bible/story-production-kit/03_novel_to_storyboard_workflow.md
docs/production_bible/story-production-kit/09_story_continuity_and_dialogue_rules.md
docs/production_bible/story-production-kit/10_director_actor_camera_simulation_workflow.md
docs/production_bible/story-production-kit/13_dialogue_character_emotion_story_rules.md
docs/production_bible/story-production-kit/14_three_second_hook_and_character_entry_rules.md
docs/production_bible/story-production-kit/20_anti_drag_story_pacing_rules.md
docs/production_bible/story-production-kit/21_cut_editing_authority_rules.md
docs/production_bible/story-production-kit/24_dialogue_freshness_and_non_template_rules.md
docs/production_bible/story-production-kit/25_dialogue_clarity_and_global_quality_gate.md
docs/production_bible/story-production-kit/26_canon_character_priority_over_reference_video.md
docs/production_bible/story-production-kit/27_novel_ai_short_drama_gold_standard.md
docs/production_bible/story-production-kit/29_story_density_no_drag_execution_gate.md
docs/production_bible/story-production-kit/31_creative_preflight_audience_story_gate.md
docs/production_bible/story-production-kit/32_director_actor_camera_storyboard_execution_gate.md
docs/production_bible/story-production-kit/33_cultural_aesthetic_sensibility_gate.md
docs/production_bible/story-production-kit/34_lu_protagonist_voice_scene_leadership_gate.md
docs/production_bible/story-production-kit/35_dialogue_stage_necessity_gate.md
docs/production_bible/story-production-kit/36_color_script_reference_image_gate.md
docs/production_bible/story-production-kit/37_colored_background_prop_split_gate.md
docs/production_bible/story-production-kit/38_reference_prompt_rebuild_camera_video_gate.md
docs/production_bible/story-production-kit/39_expert_video_prompt_method_extraction.md
docs/production_bible/story-production-kit/40_video_prompt_scene_input_card.md
docs/production_bible/story-production-kit/41_max_quality_image_dialogue_voice_and_legacy_cleanup.md
docs/production_bible/story-production-kit/42_blocking_coordinate_character_position_gate.md
```

For EP20 / CUT / Jimeng / Seedance / prompt extraction tasks, read:

```text
outputs/episode20_final_cut_source_index.md
outputs/episode20_master_prompt_rules.md
outputs/episode20_jimeng_video_prompt_contract.md
outputs/smart_prompt_execution_protocol.md
outputs/cinematic_shot_grammar_rules.md
outputs/director_intelligence_layer_rules.md
outputs/flow_pacing_edit_decision_rules.md
outputs/dialogue_timing_fit_audit_rules.md
outputs/movement_position_continuity_audit_rules.md
outputs/storyboard_video_timing_bridge_rules.md
outputs/faceless_style_reference_mode_rules.md
outputs/exact_face_style_mode_rules.md
outputs/stable_character_video_prompt_template.md
outputs/character_positioning_image_usage_rules.md
outputs/character_positioning_prompt_snippets.md
outputs/legacy_prompt_files_do_not_use.md
voice_dialogue_video_prompt_reference.md
jimeng_dialogue_voice_prompt_reference.md
docs/production_bible/story-production-kit/jimeng_dialogue_voice_prompt_reference.md
```

## Source Priority

Use this priority order whenever rules or files appear to conflict:

```text
1. User's latest instruction in the current chat.
2. Exact episode/CUT source index or existing shot sequence source.
3. Worldbuilding and character bible.
4. Contract / anti-conflict / banned-setting files.
5. Story-production-kit rules.
6. Prompt platform rules and accumulated failure notes.
7. Reference-video style analysis as a support layer only.
```

Reference videos and style-analysis files are emotional, pacing, hook, and
dialogue-rhythm references. They never override canon, character identity,
relationships, story order, reveal order, or confirmed dialogue.

## Existing Shot Sequence Rule

When the user says the storyboard split, shot sequence, `분진`, `CUT`, or
episode material is already in Codex/GitHub, search the repository before asking
for a novel manuscript.

Search by episode and production keywords such as:

```text
EP21, 21화, 第二十一集, 第21集, CUT, shot sequence, storyboard, 분진, 老宅
```

If an existing shot sequence or source index is found, treat that file as the
source for video splitting and prompt work. A novel manuscript is only required
when rewriting or newly drafting story prose.

If the source cannot be found, report the searched paths and keywords before
asking the user to paste material. Do not invent episode content.

## Color Script Reference Image Rule

Before final storyboard splitting, storyboard reference board generation,
clean keyframe prompting, or Jimeng / Seedance prompting, confirm the approved
episode or CUT color script.

```text
No approved color script = do not proceed to final split storyboard / image prompt / video prompt.
```

The color script must be created from the actual 분진 / shot sequence source and
episode theme, not from production-bible theory alone. After approval, all later
storyboard, image, video, and CapCut outputs must follow the approved palette,
lighting, contrast, saturation, and atmosphere.

After the color script is approved, create one accurate color reference image
for the episode or CUT block. This image is a required video-production
reference. Do not redesign characters, outfits, faces, props, or location logic
while creating it.

If a later prompt needs a color change, show:

```text
Original color script / Required change / Story reason / Continuity risk
```

Wait for user approval before changing the color standard.

## Colored Background / Prop Split Rule

After the color script is approved, split reference images should be colored
background / prop / camera-angle references by default, not black-and-white
character storyboard boards.

Read the full 분진 / shot sequence first, then decide whether the scene needs:

```text
MASTER BACKGROUND
ANGLE SET
PROP INSERT SET
HYBRID
```

Do not include characters in split reference images by default. Keep character
movement, body position, acting, and dialogue inside the video prompt. Use
background / prop split images to lock space, camera angle, object state,
lighting, color script, and continuity.

All background / prop split images must follow the approved color script and
must not create a new location, new palette, or disconnected background unless
the source explicitly changes location.

## Reference Prompt Rebuild Camera / Video Rule

Previous camera and video shooting method notes are legacy support only when the
user provides a new high-quality reference prompt source. Do not use old camera
or video filming methods as final authority if they conflict with the new
reference-prompt rebuild workflow.

Outside expert prompts may teach method only:

```text
prompt structure
camera instruction grammar
motion wording
background / prop control
color and lighting continuity
AI stability wording
platform compression style
```

Do not copy outside:

```text
story
characters
dialogue
worldbuilding
palette
scene content
relationships
event order
```

The rebuilt camera / video method must be based on the user's new reference
prompt material plus our actual 분진 source, approved color script, approved BG /
PROP references, canon character rules, and platform rules. It becomes official
only after user approval.

## Expert Video Prompt Method Rule

The user-approved expert prompt method is stored in:

```text
docs/production_bible/story-production-kit/39_expert_video_prompt_method_extraction.md
```

For final video prompts, use that file as the working method after reading the
actual 분진 source, approved color script, and approved BG / PROP references.

Required prompt layers:

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

This method is about production grammar only. It does not permit copying outside
story, characters, dialogue, worldview, palette, or scene content.

## Video Prompt Scene Input Card Rule

Before final video prompts, use:

```text
docs/production_bible/story-production-kit/40_video_prompt_scene_input_card.md
```

If a scene lacks essential input, actively request it instead of guessing.
Essential inputs include:

```text
approved color reference
character references / 三面图
location reference
plot-critical prop reference
exact dialogue source
platform target
duration target
hidden-prop / reveal timing
previous / next CUT continuity
```

If the user wants to continue without a missing item, mark it as:

```text
ASSUMED / NEEDS USER APPROVAL
```

## Max Quality Image / Auto Voice / Legacy Cleanup Rule

For production image, dialogue voice, and old material cleanup, use:

```text
docs/production_bible/story-production-kit/41_max_quality_image_dialogue_voice_and_legacy_cleanup.md
```

Production reference images should use the maximum available image quality in the
current tool or platform. High quality must not redesign canon, character faces,
outfits, props, or approved color logic.

When 分镜 or video prompts contain dialogue but lack AI-readable delivery notes,
add `AUTO VOICE DIRECTION` without rewriting the line. Voice direction may add:

```text
tone
speed
volume
breath
pause
emphasis
listener reaction
sound mix priority
```

Legacy camera / video materials may only be archived or deleted after 3
consecutive approved episode-production cycles using the new 39 / 40 / 41 method,
or after explicit user approval. Never delete character references / 三面图,
worldbuilding, source manuscripts, confirmed 分镜, approved visual references, or
contract / banned-setting files.

## Blocking Coordinate / Character Position Rule

For character position, coordinates, movement paths, and reference-image handoff,
use:

```text
docs/production_bible/story-production-kit/42_blocking_coordinate_character_position_gate.md
```

If a 分镜 already has coordinate / blocking rules, preserve them as the highest
filming-space source. If a 分镜 lacks coordinates, create an `AUTO BLOCKING MAP`
after reading the full 分镜, not only one CUT. Mark inferred positions as:

```text
ASSUMED / NEEDS USER APPROVAL
```

Before final video prompts, create a compact `CUT Blocking Card`, decide image
needs after reading the full scene, and label each selected image by what it
locks. Final video prompts must include a `REFERENCE LOCK` section when images
are selected.

## Dialogue Preservation Rule

Dialogue must be copied from the source when the source provides dialogue.

```text
Do not invent dialogue.
Do not rewrite dialogue.
Do not summarize dialogue.
Do not shorten dialogue.
Do not merge or replace dialogue.
Do not move a line to another speaker.
```

If a line is too dense for the time budget, first propose:

```text
CUT split
duration extension
reaction shot
cutaway
separate speaking node
voiceover / TTS planning
```

Only change wording after user approval, and show:

```text
Original / Proposed / Reason
```

## Voice Prompt Reference Rule

```text
voice_dialogue_video_prompt_reference.md = general voice / lip-sync / dialogue-reading reference.
jimeng_dialogue_voice_prompt_reference.md = Jimeng-specific compact dialogue voice prompt reference.
docs/production_bible/story-production-kit/jimeng_dialogue_voice_prompt_reference.md = production-bible mirror for Jimeng voice prompting.
```

These files are performance-format references only. They do not grant permission
to shorten, rewrite, replace, or simplify confirmed dialogue.

Original dialogue meaning must be preserved. Lu Chenzhou / 陆沉舟 is not a
short-line notification machine. He may speak as much as needed to lead the
scene, explain the necessary rule, stop danger, and move the story while staying
in character.

## Dialogue Stage Gate

Before writing or revising dialogue, lock the scene action first:

```text
1. Who is in danger now?
2. Who must speak first, and why?
3. Who should act or stay silent instead of speaking?
4. Would the scene fail to move if this line were removed?
```

Delete or convert any line that exists only to deliver information. Do not fall
into the mechanical order:

```text
Shen asks -> Hei Qi senses -> Tan Que corrects -> Lu summarizes
```

Use character need, danger, action, and emotional pressure to decide speech
order.

## Director Judgment Rule

Storyboard/CUT work is not free rewriting. Director judgment may adjust filming
structure, not source meaning.

Allowed director decisions:

```text
split a dense CUT into A/B/C video nodes
extend timing when dialogue cannot breathe
insert reaction shot or cutaway
choose master shot / dialogue shot / reaction shot / action node
mark face-risk and use faceless blocking board
compress dead air while preserving meaning
report filming risks before changing anything
```

Not allowed without user approval:

```text
change event order
change speaker
change relationship logic
remove a source line
replace source dialogue with a "better" line
turn a quiet acting beat into a different plot point
```

## Audio Source Rule

Never infer silence from a visually quiet storyboard board.

Always check source for:

```text
dialogue
BGM
SFX
environment sound
off-screen sound
motorcycle / footsteps / wind / city ambience
```

If audio is missing from source, report it as missing. Do not silently invent or
delete it.

## Character Locks

Use these labels consistently:

```text
LU = 陆沉舟
SHEN = 沈泊川
HAN = 韩知玄
TAN = 檀缺
HEIQI = 黑七
```

Core locks:

```text
陆沉舟: modern black leather jacket, black T-shirt, dark pants, boots. Scene leader and field judge.
沈泊川: cleaning-company boss / realistic young man / motorcycle entry when source requires it. Must not look like 韩知玄.
韩知玄: 镇灵司 uniform and public-duty restraint. Must not look like 陆沉舟.
檀缺: dark modern daily outfit unless source says otherwise. Must not become 白清檀.
黑七: always a small black fox body. Never human, wolf, dog, cat, or fox-boy.
白清檀: black clothing / queen identity when present. Never turn her into a white-robed ghost.
```

All characters must follow the turnaround sheets / 三面图 when image or video
work uses visual references. Do not redesign faces, hair, outfits, body
proportions, age, temperament, or silhouette.

## Cinematic Shot Grammar

Do not force every scene into one image or one generated video node.

Use real filming logic:

```text
master shot = geography, silence, group blocking
dialogue shot = one or two speakers, clear face and voice
reaction shot = emotional answer without changing source line
cutaway = prop, door, bag, footprint, wind, city, animal, document state
action node = body movement or camera movement, not both at once
speaking node = dialogue timing and lip-sync stability
```

Hard generation rule:

```text
At most two clear human faces in one generated frame.
3+ clear human faces = high face-break risk.
3+ characters may appear in faceless/blocking master shots only.
Important dialogue should move to one-person or two-person dialogue shots.
```

## Faceless Style Reference Mode

Use `outputs/faceless_style_reference_mode_rules.md` when storyboard/reference
board faces keep failing. It is for blocking, position, camera path, continuity,
and actor movement. It is not a final video face rule.

Final video faces still follow character turnaround sheets / 三面图.

## Output Checklist

Before outputting any storyboard prompt, clean keyframe prompt, or Jimeng /
Seedance prompt, check:

```text
[ ] Did I read the episode/CUT source or existing shot sequence first?
[ ] Did I search the repo before asking for a novel manuscript?
[ ] Did I preserve event order, speaker, dialogue meaning, BGM/SFX/environment sound?
[ ] Did I create or follow the approved color script and color reference image?
[ ] Did I use maximum available quality for production reference images?
[ ] Did I decide background / prop split mode and keep characters out of split images by default?
[ ] Did I preserve existing coordinate rules or create AUTO BLOCKING MAP when missing?
[ ] Did every final CUT have a CUT Blocking Card?
[ ] Did I label selected images by lock role and include REFERENCE LOCK in video prompts?
[ ] Did I use new reference-prompt-derived camera/video method instead of old legacy method when applicable?
[ ] Did I apply the 39 expert video prompt layer order for final video prompts?
[ ] Did I use the 40 scene input card and request missing essential references?
[ ] Did I add AUTO VOICE DIRECTION when source dialogue lacks AI-readable delivery notes?
[ ] Did I keep dialogue clear above SFX / BGM?
[ ] Did I avoid deleting legacy files before 3 approved cycles or user approval?
[ ] Did I lock worldbuilding, character identity, and banned settings?
[ ] Did I diagnose first-3-second hook and story drag?
[ ] Did I check whether the dialogue is actor-readable within the time budget?
[ ] If timing is dense, did I prefer split/extend/reaction/cutaway over shortening?
[ ] Did I avoid the mechanical role-order dialogue pattern?
[ ] Did I prevent extra characters, duplicated people, and HEIQI form drift?
[ ] Did I separate director judgment from content rewriting?
```
