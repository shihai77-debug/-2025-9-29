# Legacy Prompt Files Warning｜旧提示词文件使用警告

This repository contains old derived prompt packs from earlier experiments.

They may contain outdated terms such as:

```text
Shen
SHEN
Shen Bochuan
motorcycle outfit
black leather biker
CASE BRIEFING
DOCS WITH SHEN
English storyboard labels
old CUT-01 / CUT-02 prompt drafts
```

These files are not source of truth.

## Current Source Of Truth

Use only this active chain unless the user explicitly names an old file:

```text
AGENTS.md
outputs/episode20_final_cut_source_index.md
outputs/episode20_master_prompt_rules.md
outputs/episode20_jimeng_video_prompt_contract.md
outputs/smart_prompt_execution_protocol.md
outputs/cinematic_shot_grammar_rules.md
outputs/director_intelligence_layer_rules.md
outputs/flow_pacing_edit_decision_rules.md
outputs/faceless_style_reference_mode_rules.md
outputs/exact_face_style_mode_rules.md
outputs/stable_character_video_prompt_template.md
outputs/character_positioning_image_usage_rules.md
outputs/character_positioning_prompt_snippets.md
references/turnarounds/
```

## Alias Rule

```text
If an old file says Shen or SHEN, treat it only as an alias for 沈泊川.
Output must use 沈泊川 and @沈泊川角色参考图.
Do not output @Shen角色参考图.
Do not revive old black leather biker identity for 沈泊川.
```

## Practical Rule

```text
Old prompt packs may be read only for historical comparison.
They must not override current character identity, source dialogue, BGM/SFX, shot grammar, flow pacing, or clean keyframe rules.
```
