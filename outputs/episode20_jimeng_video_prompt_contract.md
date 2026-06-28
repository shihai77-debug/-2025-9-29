# EP20 Jimeng / Seedance Video Prompt Contract｜第20集视频提示词契约

Use this contract every time the user asks for a Jimeng / Seedance video prompt from a CUT, storyboard board, clean keyframe, approved board, or GitHub source.

The goal is not to copy the draft mechanically. The goal is to preserve locked story content while producing a video prompt that can actually generate stable, watchable footage.

## Mandatory Read Order

Before writing the prompt, read these files from the current working branch:

```text
outputs/episode20_final_cut_source_index.md
outputs/episode20_master_prompt_rules.md
outputs/smart_prompt_execution_protocol.md
outputs/cinematic_shot_grammar_rules.md
outputs/director_intelligence_layer_rules.md
outputs/flow_pacing_edit_decision_rules.md
outputs/dialogue_timing_fit_audit_rules.md
outputs/movement_position_continuity_audit_rules.md
outputs/faceless_style_reference_mode_rules.md
outputs/exact_face_style_mode_rules.md
outputs/stable_character_video_prompt_template.md
outputs/character_positioning_image_usage_rules.md
outputs/character_positioning_prompt_snippets.md
outputs/legacy_prompt_files_do_not_use.md
```

If the user provides a final CUT text in the current request, that pasted final CUT text overrides weaker storyboard labels.

## Source Priority

```text
Dialogue / BGM / SFX / timing / emotion / voice = final CUT source index.
Framing / blocking / camera path / prop placement / spatial continuity = approved storyboard board.
Character start/end screen position / movement path / no-teleport check = movement position continuity audit rules.
Face / hair / outfit / body / silhouette / identity = character turnaround sheets / role reference images.
Shot splitting = cinematic shot grammar.
Director diagnosis = director intelligence layer.
Flow damage / dead air / compress-merge-replace-pass proposal = flow pacing edit decision rules.
Dialogue timing fit / extension / split-node decision = dialogue timing fit audit rules.
Final I2V source image = clean 16:9 keyframe, not labeled storyboard board.
```

Do not generate a video prompt from an image alone if the source CUT text is available or required.

## Storyboard Board Limit

Approved storyboard boards are planning references only.

```text
Use storyboard board for blocking, camera, props, movement direction, and continuity.
Do not use storyboard board face, temporary outfit, black-white style, labels, arrows, panel borders, or written notes as final video appearance.
Do not feed a crowded labeled storyboard board directly as the final image-to-video source when face accuracy matters.
Use or create a clean 16:9 color keyframe for final I2V.
```

Every video prompt that references a board must include:

```text
注意：批准 storyboard reference board 只用于站位、构图、动线、镜头、道具状态和连续空间关系；不要参考该board里的人脸、五官、发型细节、服装细节或人物气质。所有角色外貌必须严格以各自三面图/角色参考图为准。
```

## Legacy File Warning

Old derived prompt packs may contain outdated terms such as `Shen`, `SHEN`, `motorcycle outfit`, `black leather biker`, `CASE BRIEFING`, `DOCS WITH SHEN`, or English storyboard labels.

```text
Old derived prompt files are not source of truth.
If an old file says Shen or SHEN, treat it only as an alias for 沈泊川.
Output must use 沈泊川 and @沈泊川角色参考图.
Do not output @Shen角色参考图.
Do not revive old black leather biker identity for 沈泊川.
```

## Character Locks

Use exact speaker/role tags:

```text
@陆沉舟
@黑七
@檀缺
@韩知玄
@沈泊川
```

Per-character identity anchors:

```text
陆沉舟：男性，黑色皮夹克/黑色内搭/黑色长裤，沉郁疲惫，严格参考@陆沉舟三面图。
黑七：一只小型黑色狐狸，黑色皮毛，尖耳，细长狐狸嘴，蓬松长尾，严格参考@黑七狐狸参考图；不是狗、狼、人。
檀缺：女性，深色现代日常装，冷静克制，严格参考@檀缺三面图；不是白清檀，不穿白衣。
韩知玄：男性，黑色长款镇灵司制服，公务式克制，严格参考@韩知玄三面图；不是沈泊川。
沈泊川：男性，年轻清洁服务公司老板/现场负责人，灰绿或深灰工作衬衫外套、深灰T恤、棕色工装裤、棕色工作靴、卡其色实用背包/工具包，市井敏锐但不油滑，严格参考@沈泊川角色参考图；不是韩知玄，不是陆沉舟，不是黑皮骑手。
```

## Character Count And Face Stability

```text
CUT-01 to CUT-07: only 陆沉舟, 黑七, 檀缺, 韩知玄, 沈泊川. Each appears once.
CUT-08 to CUT-15: 韩知玄 has exited. Only 陆沉舟, 黑七, 檀缺, 沈泊川. Each appears once.
```

For generated images, clean keyframes, and video nodes:

```text
At most two clear human faces per generated frame or video node.
3+ clear human faces in one generated frame = high face-break risk.
3+ characters may appear only in faceless/blocking master shots.
Important dialogue must move to a 1-person or 2-person dialogue shot.
```

## Smart Execution Order

Before writing the final video prompt:

```text
1. Source extraction: exact dialogue, speaker, BGM, SFX, environment, timing, props, emotion, continuity anchors.
2. Board extraction: only blocking, camera, prop placement, movement direction, spatial continuity.
3. Reference lock: turnaround sheets for face/hair/outfit/body/silhouette/identity.
4. Risk diagnosis: dialogue density, face stability, 3+ character risk, action plus speech conflict, prop handoff risk, audio balance, wooden supporting-actor risk, duplicate-character risk, identity-confusion risk, position drift risk.
5. Flow pacing diagnosis: KEEP / COMPRESS / MERGE / REPLACE / PASS_PROPOSAL for weak/silent beats.
6. Dialogue timing fit audit: verify every spoken line fits its assigned seconds with natural speech, breath, pause, lip-sync, and listener reaction.
7. Movement position continuity audit: verify every visible character's start position, end position, screen percentage, depth layer, body direction, gaze direction, movement path, locked status, and next-node continuity.
8. Filming decision: keep, compress, merge, replace cutaway, pass proposal, extend, split, master/dialogue/reaction/cutaway, faceless master, clean keyframe, or separate dubbing.
9. Prompt writing.
10. Self-repair: missing dialogue, BGM/SFX, character count, prop state, continuity, timing fit, movement path, position table, face stability, actor delivery, audio mix, or pacing must be fixed before output.
```

## Flow Pacing Rule

Classify weak or silent beats:

```text
KEEP：承载情绪、悬念、反应、空间、道具或continuity。
COMPRESS：动作/移动有用但时长过长。
MERGE：与前后CUT重复，可自然合并。
REPLACE：原镜头弱，但需要用手、资料、门、灰尘、风声等cutaway保留连接。
PASS_PROPOSAL：无对白、无情绪、无信息、无位置/道具变化、无continuity价值，建议跳过但必须用户确认。
```

Never pass/skip automatically.

## Dialogue Timing Fit Rule

Never invent, rewrite, summarize, shorten, merge, or replace dialogue.

Dialogue feasibility:

```text
short line: 1.5-3 seconds plus breath/pause.
medium line: 3-6 seconds plus breath/pause.
long line: 6-10 seconds plus breath/pause.
information-heavy exposition: 8-12 seconds or split into multiple nodes.
two exposition lines in one CUT: usually 16-20 seconds, or split into two video nodes.
```

Every video prompt with dialogue must include:

```text
台词时长适配：
原分镜时长：
自然表演所需时长：
判断：可用 / 不可用
处理：原时长 / 延长到X秒 / 拆成X个视频节点 / 建议后期配音
```

If the timing is unsafe, the final prompt must not keep the unsafe original timing. It must extend, split into nodes, use cutaway support, or recommend separate dubbing/TTS.

Known risk:

```text
CUT-10 has two professional analysis lines. A literal 10-second single video with both lines is unsafe.
Default repair: CUT-10A 10 seconds + CUT-10B 8 seconds, or one extended stable 18-second clip.
If the platform limit is 15 seconds, do not force both lines into one clip; split into CUT-10A and CUT-10B.
```

## Movement Position Continuity Rule

Background continuity is not enough. Every video prompt must include concrete character continuity.

```text
人物位置连续表：
角色｜起点屏幕位置｜终点屏幕位置｜景深层级｜身体朝向｜视线方向｜状态锁定

人物移动表：
角色｜是否移动｜起点｜路径｜终点｜速度/步数｜镜头关系｜禁止事项

镜头与人物运动关系：
镜头怎么动；谁跟随镜头；谁保持世界位置不动；谁只允许微反应。
```

Hard rule:

```text
镜头运动不等于人物运动。
位置锁定不等于木头人；锁定角色必须有眼神、呼吸、肩颈、手指、重心等微反应。
移动角色必须写 start -> path -> end。
上一节点终点必须等于下一节点起点，除非source明确说明画面外移动。
```

If the movement is vague, the prompt is invalid and must be repaired before output.

## Dialogue And Audio Rules

Every spoken line must include:

```text
开始-结束秒 @角色名：
“原文台词”
声线基准：
音量连续性：
语速：
气息：
外层情绪：
内层情绪：
重音词：
停顿点：
尾音处理：
口型与视线：
身体配合：
```

Audio hierarchy:

```text
人声 > 核心音效 > 环境音 > BGM。
人声：清晰居前，音量稳定。
核心音效：贴合动作点，不提前、不拖后，不盖人声。
环境音：低层持续，保持场景空间连续。
BGM：按source index使用；对白段自动下压。
```

## Required Output Sections

A Jimeng / Seedance video prompt must include these sections:

```text
导演诊断：
节奏判断：KEEP / COMPRESS / MERGE / REPLACE / PASS_PROPOSAL
台词时长适配：
台词时长判断：
脸部稳定判断：
人物位置连续表：
人物移动表：
镜头与人物运动关系：
参考素材：
画面性质：
角色锁定：
场景与连续性：
总时长与镜头：
镜头路径：
时间轴表演：
台词与声音输入：
声音设计：
脸部与身份稳定：
道具状态：
continuity anchor：
负面提示：
```

If the user asks for prompt only, diagnosis may be hidden, but timing fit and movement continuity must still be applied. Do not silently pass/skip any beat without user approval.

## Final Self-Check

```text
[ ] Source index read first.
[ ] Exact dialogue preserved.
[ ] BGM/SFX/environment preserved.
[ ] Board used only for blocking, not appearance.
[ ] Legacy files did not override current rules.
[ ] Character count locked.
[ ] Max two clear human faces per generated node.
[ ] Clean keyframe recommended when face accuracy matters.
[ ] Every spoken line was checked against its assigned seconds.
[ ] Unsafe timing was extended, split, supported by cutaway, or moved to separate dubbing.
[ ] Long dialogue not forced into a short moving shot.
[ ] Movement position continuity audit was applied.
[ ] 人物位置连续表, 人物移动表, and 镜头与人物运动关系 are present.
[ ] Camera movement is separated from character movement.
[ ] No character teleports, drifts, changes order, or freezes without micro acting.
[ ] Actor-style delivery included.
[ ] Audio hierarchy included.
[ ] Flow pacing decision made.
[ ] No pass/skip without approval.
[ ] No Shen/Han, Tan/白清檀, Lu/沈泊川, Hei Qi dog/wolf/human errors.
```