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
[ ] Did I lock worldbuilding, character identity, and banned settings?
[ ] Did I diagnose first-3-second hook and story drag?
[ ] Did I check whether the dialogue is actor-readable within the time budget?
[ ] If timing is dense, did I prefer split/extend/reaction/cutaway over shortening?
[ ] Did I avoid the mechanical role-order dialogue pattern?
[ ] Did I prevent extra characters, duplicated people, and HEIQI form drift?
[ ] Did I separate director judgment from content rewriting?
```
