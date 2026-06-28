# AGENTS.md｜《棺中檀色》EP20 默认规则入口

This default-branch file exists so GitHub / Codex agents can discover the EP20 prompt workflow even when they do not automatically open the working branch.

## Important Branch Rule

The complete EP20 rule set currently lives on this branch:

```text
codex/refactor-shot-sequence-for-continuity
```

When the user asks about EP20, CUTs, storyboard boards, approved boards, Jimeng, Seedance, video prompts, clean keyframes, face stability, or prompt extraction, first read the full files from that branch:

```text
outputs/episode20_final_cut_source_index.md
outputs/episode20_master_prompt_rules.md
outputs/episode20_jimeng_video_prompt_contract.md
outputs/smart_prompt_execution_protocol.md
outputs/cinematic_shot_grammar_rules.md
outputs/director_intelligence_layer_rules.md
outputs/stable_character_video_prompt_template.md
outputs/exact_face_style_mode_rules.md
outputs/faceless_style_reference_mode_rules.md
outputs/character_positioning_image_usage_rules.md
outputs/character_positioning_prompt_snippets.md
```

Do not rely only on this default-branch bootstrap file if the full branch files are available.

## Hard Source Priority

```text
对白 / BGM / SFX / 情绪 / 声音 / 时长 = source index 优先。
构图 / 站位 / 动线 / 镜头 / 道具空间 = approved storyboard board 参考。
人物脸 / 发型 / 服装 / 体型 / 气质 = 三面图 / 角色参考图 优先。
智能执行顺序 / 自修流程 = smart prompt execution protocol 优先。
镜头拆分 = cinematic shot grammar 优先。
导演诊断 / 更聪明的拍法建议 = director intelligence layer 优先。
脸部不稳定时的分镜参考图 = faceless style reference mode 优先。
```

Never infer no dialogue, no BGM, no SFX, or no environment sound from a visually silent storyboard board. Always check the source index.

## Smart Execution Rule

Before writing any storyboard prompt, clean keyframe prompt, Jimeng prompt, or Seedance prompt, think like a source-locked director:

```text
1. Source extraction：先读原文对白、说话人、BGM、SFX、环境音、时长、道具、continuity anchor。
2. Board extraction：board只读构图、站位、动线、镜头、道具位置、空间连续。
3. Reference lock：用三面图/角色参考图锁脸、发型、服装、体型、气质。
4. Viewer-first diagnosis：观众会看懂吗？情绪会活吗？该切还是该停？
5. Risk diagnosis：台词密度、脸部稳定、3人以上清晰脸、动作+台词、音频层级、配角木偶风险。
6. Filming decision：keep and hold / smart adjustment / split or extend。
7. Self-repair：漏对白、音频、角色数量、道具状态、演员式读法、continuity时，先修正再输出。
```

Do not be a mechanical prompt copier.

```text
故事不乱改。
拍法要聪明。
不要为了分镜而分镜。
该切才切，该停就停。
表演要像人。
镜头要能剪。
声音要能听。
观众要想继续看。
```

## Reference Tag Rule

Use Chinese character reference tags. Do not use English alias tags for character references.

```text
必须使用：@沈泊川角色参考图
禁止使用：@Shen角色参考图
```

Standard EP20 reference material header:

```text
参考素材：@陆沉舟三面图、@黑七狐狸参考图、@檀缺三面图、@韩知玄三面图、@沈泊川角色参考图、@第20集CUT-XX批准 storyboard reference board。
```

沈泊川 character description must use:

```text
沈泊川：严格参考@沈泊川角色参考图，清洁服务公司年轻老板/现场负责人，灰绿或深灰工作衬衫外套，深灰T恤，棕色工装裤，棕色工作靴，卡其色实用双肩包/工具包；摩托车和头盔只作为交通/入场道具，不是黑皮骑手。
```

## Faceless Style Reference Mode

Use this mode when storyboard/reference board faces keep failing.

```text
人物脸部可以出现，但不要画清楚眼睛、鼻子、嘴巴。
保留脸部外轮廓、头部方向、发型、体型、服装、姿势、位置。
表演通过头部角度、肩膀、手部、身体重心、呼吸姿态表达。
背景可以清楚，但人物保持浅灰、低对比、淡线 storyboard 风格。
不要把本图当作角色脸部参考。
```

This is for storyboard/reference boards only. It is not a final video face rule.

Final video faces must still follow character turnaround sheets / 三面图.

## Cinematic Shot Grammar

Do not force every CUT into one image or one video node.

Use real filming logic:

```text
master shot：空间、关系、站位、群体沉默。
dialogue shot：重要台词，1-2人中近景，保护脸、口型、演员表演。
reaction shot：听者反应，眼神、呼吸、手部、肩颈微动。
cutaway：手、资料、背包、头盔、摩托、门、积灰、街角。
action node：走位、入场、开包、取物、停车、转身。
speaking node：稳定说话，脸清楚，少运动。
```

Hard generation rule:

```text
One generated storyboard panel, clean keyframe, or video node should contain at most two clear human faces.
3+ clear human faces in one generated frame = high face-break risk.
3+ characters may appear only in faceless/blocking master shots.
Important dialogue must move to a 1-person or 2-person dialogue shot.
```

Must split when:

```text
三人以上同框 + 长台词。
三人以上清晰脸同框。
复杂动作 + 长台词。
远景小脸 + 要求口型。
道具操作 + 信息量大的说明台词。
脸已经不稳 + 重要台词。
```

Do not over-split:

```text
如果沉默、悲伤、压力、眼神、空间张力是重点，就保持镜头。
如果同一情绪beat延续，只是视角变化，用镜头运动，不强行拆分。
```

## Character And Dialogue Locks

```text
CUT-01 至 CUT-07：只允许陆沉舟、黑七、檀缺、韩知玄、沈泊川，每个角色一次。
CUT-08 至 CUT-15：韩知玄已离场，只允许陆沉舟、黑七、檀缺、沈泊川，每个角色一次。
檀缺不能变成白清檀，不能穿白衣。
黑七只能是一只小型黑色狐狸，不是狗、狼、人。
沈泊川不能变韩知玄，韩知玄不能变沈泊川。
```

Dialogue must be copied exactly from the source index. Never invent, rewrite, summarize, shorten, merge, or replace dialogue.

Use exact speaker tags:

```text
@陆沉舟
@黑七
@檀缺
@韩知玄
@沈泊川
```

## Output Checklist

Before outputting any storyboard prompt, clean keyframe prompt, or Jimeng / Seedance video prompt, check:

```text
[ ] Did I read the full source index from the working branch?
[ ] Did I read smart_prompt_execution_protocol.md from the working branch?
[ ] Did I use @沈泊川角色参考图 and avoid @Shen角色参考图?
[ ] Did I ask viewer-first questions: should this hold, adjust, split, or extend?
[ ] Did I judge master/dialogue/reaction/cutaway/action/speaking function?
[ ] Did I avoid multi-person wide shot plus long dialogue?
[ ] Did I keep clear human faces to at most two per generated frame/node?
[ ] Did I use 三面图 for identity, not storyboard board faces?
[ ] If faces are unstable, did I use faceless style reference mode for storyboard/reference image?
[ ] Did I preserve exact dialogue, BGM, SFX, environment sound?
[ ] Did I include actor-style voice directions and audio mixing?
[ ] Did I prevent duplicate characters and character confusion?
```
