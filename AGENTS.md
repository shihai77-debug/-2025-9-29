# AGENTS.md｜《棺中檀色》EP20 提示词工作规则

本仓库用于管理《棺中檀色》EP20 分镜、导演参考图、角色锁定、storyboard reference board、clean keyframe、即梦 / Seedance 视频提示词规则。

当用户写 `@GitHub`、`GitHub 기준`、`Codex 기준`、`저장소 기준`、`CUT-XX 프롬`、`approved board 영상 프롬` 时，必须优先读取本仓库规则，不得凭记忆生成。

目标不是机械复制分镜，而是：故事不乱改，拍法要聪明，人物位置要连续，表演像真人，镜头能剪，声音能听，观众想继续看。

---

## 1. 必读文件顺序

EP20 CUT storyboard / clean keyframe / 视频提示词必须按以下顺序读取：

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
```

然后再读取：

```text
用户上传的最终CUT文本。
用户上传的批准 storyboard reference board。
用户上传的三面图 / 角色参考图 / 角色定位图。
```

如果用户在当前消息里贴了最终CUT文本，以用户贴出的最终CUT文本覆盖较弱的旧board标签。

---

## 2. Source Priority

```text
对白 / BGM / SFX / 环境音 / 情绪 / 声音 / 时长 = final CUT source index。
构图 / 站位 / 镜头 / 道具空间 = 批准board参考。
人物起点终点 / 动线 / 屏幕位置 / 防瞬移 = movement position continuity audit rules。
分镜图秒数 / 原文CUT秒数 / 最终视频节点秒数 = storyboard video timing bridge rules。
人物脸 / 发型 / 服装 / 体型 / 气质 = 三面图/角色参考图最高优先级。
智能执行顺序 / 自修流程 = smart prompt execution protocol。
镜头拆分 / master-dialogue-reaction-cutaway 判断 = cinematic shot grammar。
导演诊断 / 更聪明的拍法建议 = director intelligence layer。
节奏空镜 / 压缩合并 / 跳过建议 = flow pacing edit decision rules。
台词时长适配 / 延长 / 拆节点 / 后期配音判断 = dialogue timing fit audit rules。
最终视频源图 = clean keyframe，不直接用带字board。
脸部不稳定时的分镜参考图 = faceless style reference mode。
角色定位图 = 分镜草图 / storyboard board 的外形、发型、服装、体型、姿态、轮廓、方向参考。
```

禁止把 storyboard board 里没有写声音理解成无对白、无BGM、无SFX。
禁止把批准board里的人脸、服装、临时画法当成最终角色外貌。
禁止把背景连续当成人物位置连续。
禁止把分镜图面板秒数直接当成最终视频节点秒数，除非已经通过 timing bridge 明确标为 approved video duration。

---

## 3. Legacy Output Warning

旧派生prompt文件可能含有旧规则，例如：

```text
Shen
SHEN
Shen Bochuan
@Shen角色参考图
motorcycle outfit
black leather biker
CASE BRIEFING
DOCS WITH SHEN
LU POS LOCK
TAN POS LOCK
HAN POS LOCK
SHEN ENTER
英文storyboard标签
```

这些旧表达不是source of truth。

```text
遇到 Shen / SHEN 只当作沈泊川的旧alias。
最终输出必须写沈泊川、@沈泊川角色参考图。
禁止输出@Shen角色参考图。
禁止恢复旧黑皮骑手沈泊川。
禁止让旧derived prompt覆盖AGENTS、source index、master rules、smart protocol、director rules、flow pacing rules、timing audit rules、movement audit rules、timing bridge rules、current turnaround sheets。
```

---

## 4. 智能执行协议硬规则

每次输出 storyboard prompt、clean keyframe prompt、即梦 / Seedance 视频提示词前，必须按顺序执行：

```text
1. Source extraction：先从source index提取对白、说话人、BGM、SFX、环境音、时长、道具、情绪、continuity anchor。
2. Board extraction：只从批准board提取构图、站位、动线、镜头、道具位置、空间连续。
3. Reference lock：用三面图/角色参考图锁定脸、发型、服装、体型、气质。
4. Risk diagnosis：诊断台词密度、脸部稳定、3人以上风险、动作+台词冲突、道具交接、音频层级、配角木偶风险、重复人物、身份混淆、空镜拖节奏、人物位置漂移、缺少动线。
5. Flow pacing diagnosis：KEEP / COMPRESS / MERGE / REPLACE / PASS_PROPOSAL。
6. Dialogue timing fit audit：逐句检查自然语速、呼吸、停顿、口型、听者反应是否能放进指定秒数。
7. Movement position continuity audit：检查每个可见角色的起点、终点、屏幕百分比、景深层级、身体朝向、视线方向、移动路径、锁定状态、下一节点衔接。
8. Storyboard-video timing bridge：分清分镜图视觉节拍秒数、原文CUT秒数、最终视频节点秒数；如果不同，必须说明 KEEP_SOURCE / COMPRESS / EXTEND / SPLIT_NODES / MERGE / REPLACE / PASS_PROPOSAL。
9. Filming decision：决定是否原时长、延长、拆节点、master/dialogue/reaction/cutaway、faceless/blocking master、clean keyframe、cutaway support 或后期配音。
10. Prompt writing：再写最终提示词。
11. Self-repair：如果漏了对白、BGM、SFX、角色数量、道具状态、continuity anchor、演员式读法、音频层级、脸部稳定、节奏判断、台词时长适配、timing bridge、人物位置表或人物移动表，必须先修正再输出。
```

如果台词时长不适配，禁止继续输出原始危险时间轴；必须延长、拆节点、使用cutaway support，或建议后期配音/TTS。

如果人物位置或动线不适配，禁止输出模糊blocking；必须添加人物位置连续表、人物移动表、镜头与人物运动关系，必要时拆镜头。

如果分镜图秒数和原文CUT秒数不同，禁止直接二选一；必须输出或内部执行分镜-视频时间桥接表。

如果用户只要“프롬만”, 可以隐藏诊断，但仍必须应用诊断结果。

---

## 5. Movement Position Gate

每个 storyboard prompt、clean keyframe prompt、Jimeng / Seedance prompt 都必须明确：

```text
人物位置连续表：
角色｜起点屏幕位置｜终点屏幕位置｜景深层级｜身体朝向｜视线方向｜状态锁定

人物移动表：
角色｜是否移动｜起点｜路径｜终点｜速度/步数｜镜头关系｜禁止事项

镜头与人物运动关系：
镜头怎么动；谁跟随镜头；谁保持世界位置不动；谁只允许微反应。
```

硬规则：

```text
背景连续不等于人物连续。
镜头运动不等于人物运动。
位置锁定不等于木头人；锁定角色必须有眼神、呼吸、肩颈、手指、重心等微反应。
移动角色必须写 start -> path -> end。
上一节点终点必须等于下一节点起点，除非source明确说明画面外移动。
```

禁止：

```text
只写“在旁边 / 在画面里 / 靠近 / 远处”。
只写“镜头跟随”但不写人物从哪里到哪里。
同一角色无路径从左跳到右。
背景人物每格顺序乱换。
该静止的人突然走动。
该移动的人没有移动。
```

---

## 6. Timing Bridge Gate

每个从 storyboard board 转成视频提示词的任务都必须明确：

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

硬规则：

```text
分镜图秒数 = 动作节奏 / 构图参考，不自动等于视频节点秒数。
原文CUT秒数 = source story timing。
最终视频节点秒数 = source index + 台词适配 + 节奏判断 + 本次批准执行方案。
3-4秒分镜beat不能无说明覆盖6秒原文CUT。
6秒原文CUT也不能无说明覆盖已经批准的3-4秒压缩执行。
长台词、BGM/SFX、重要表演需要6秒时，不能缩成3-4秒。
```

当分镜和视频秒数冲突时，必须输出或内部执行：

```text
时间冲突修正：
分镜图秒数：
原文秒数：
最终视频秒数：
判断：KEEP_SOURCE / COMPRESS / EXTEND / SPLIT_NODES / MERGE / REPLACE / PASS_PROPOSAL
原因：
```

---

## 7. 导演判断层硬规则

```text
故事锁定，拍法灵活。
原文对白、说话人、事件顺序、人物关系、BGM、SFX、环境音、关键道具状态不能改。
为了最终视频质量，可以重新设计视频节点数量、时长、景别、角度、反应镜头、cutaway、动作/台词拆分、人物动线和表演节奏。
```

必须诊断：

```text
本CUT剧情核心是什么？
最大失败风险是什么：脸、台词、时间、动作、镜头、声音、情绪、位置？
是否长台词塞进短秒数？
是否3人以上清晰脸同框？
是否动作和大段台词同时发生？
人物是否需要移动？从哪里到哪里？
哪些人物必须锁定但保持微反应？
分镜图秒数和视频节点秒数是否冲突？
是否需要延长或拆成多个视频节点？
是否需要master shot / dialogue shot / reaction shot / cutaway？
```

---

## 8. Dialogue Timing Fit Gate

每次有对白时必须输出或内部执行：

```text
台词时长适配：
原分镜时长：
自然表演所需时长：
判断：可用 / 不可用
处理：原时长 / 延长到X秒 / 拆成X个视频节点 / 建议后期配音
```

Known risk:

```text
CUT-10有两段专业判断台词。原10秒单视频不适合自然表演。
默认处理：CUT-10A 7秒 + CUT-10B 8秒，或延长到15-16秒。
```

---

## 9. 多人脸稳定规则

```text
一个生成用 storyboard panel、clean keyframe、video node 里最多两个清晰真人脸。
3人以上清晰脸同框 = 高脸崩风险。
3人以上只允许作为faceless/blocking master shot，不承载精确脸和长台词。
重要对白必须放到1人或2人dialogue shot。
```

推荐拆法：

```text
5 characters -> faceless master / 2-person dialogue/action shot / 2-person reaction shot / fox or prop cutaway。
4 characters -> faceless master / 2-person shot / 2-person reaction。
3 characters -> 2-person shot / 1-person reaction，或 faceless 3-person master。
```

---

## 10. 角色锁定

固定语音/角色标签必须使用：

```text
@陆沉舟
@黑七
@檀缺
@韩知玄
@沈泊川
```

参考素材标签规则：

```text
必须使用 @沈泊川角色参考图。
禁止使用 @Shen角色参考图。
```

角色身份：

```text
陆沉舟 = black leather jacket, black T-shirt, dark pants, black boots, tired but stable.
黑七 = exactly one small black fox, not dog, wolf, human, monster, or second fox.
檀缺 = dark modern daily outfit, dark cardigan/jacket, dark top, black skirt, not 白清檀, not white clothes.
韩知玄 = black long 镇灵司 uniform, official restraint, not 沈泊川.
沈泊川 = young cleaning-service company boss / on-site lead, gray-olive work shirt jacket, dark gray T-shirt, brown cargo work pants, brown work boots, khaki practical backpack/tool bag, can use motorcycle/helmet only as transport props, not a black-leather biker, not 韩知玄.
```

CUT-01 至 CUT-07：只允许陆沉舟、黑七、檀缺、韩知玄、沈泊川，每个角色只出现一次。
CUT-08 至 CUT-15：只允许陆沉舟、黑七、檀缺、沈泊川，韩知玄已经离场。

---

## 11. Storyboard / Clean Keyframe

Storyboard reference board：

```text
只用于导演参考、位置、镜头、动作、道具、continuity。
可以有中文短标签、箭头、位置锁定、镜头方向、迷你位置图。
3人以上默认使用无五官定位风格：只保留脸部轮廓、头部方向、发型轮廓，不画清楚眼睛鼻子嘴巴。
```

Clean keyframe：

```text
最终I2V源图必须是16:9彩色真人电影画面。
无文字、无箭头、无标签、无边框。
人物脸来自三面图/角色参考图，不来自storyboard board。
说话者/动作主体脸部足够大，最多两个清晰真人脸。
```

---

## 12. 声音与表演

每句对白必须包含：

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

音量优先级：

```text
人声 > 核心音效 > 环境音 > BGM
```

表演规则：

```text
不要像朗读稿。
不要用突然大声表现情绪。
情绪通过呼吸、停顿、语速、重音、眼神、手部动作表现。
位置锁定 = 屏幕/世界位置不乱动，不等于身体和表情冻结。
配角也要有听戏反应：眼神、呼吸、肩颈、手指、身体重心。
```

---

## 13. Final Self-Check

输出前必须检查：

```text
[ ] Did I read source index first?
[ ] Did I read smart / cinematic / director / flow / timing / movement / timing bridge / positioning / legacy rules?
[ ] Did I preserve exact dialogue, BGM, SFX, environment sound?
[ ] Did I run director diagnosis, flow pacing diagnosis, dialogue timing fit audit, movement position continuity audit, and storyboard-video timing bridge?
[ ] Did I avoid unsafe original timing after finding dialogue overflow?
[ ] Did I separate storyboard visual beat seconds from source CUT duration and final video node duration?
[ ] Did I include 人物位置连续表, 人物移动表, and 镜头与人物运动关系?
[ ] Did I separate camera path from character path?
[ ] Did I prevent character teleporting, drifting, or changing order between nodes?
[ ] Did I give locked characters micro acting instead of wooden stillness?
[ ] Did I avoid 3+ clear human faces with long dialogue?
[ ] Did I use turnaround sheets / role references for identity?
[ ] Is 沈泊川 the current cleaning-service company boss, not old black leather biker?
[ ] Did I use storyboard board only for blocking/camera/props/continuity?
[ ] Did I use clean keyframe for final I2V source when face stability matters?
[ ] Did I include actor-style breath, pause, listening reaction, and audio mix?
[ ] Did I prevent duplicate characters, mixed faces, extra people, and 黑七 dog/wolf errors?
```

---

## 14. Production Bible / Supporting Style Layer

This repository now also contains a higher-level production bible for novel, storyboard, prompt, video, and CapCut workflow:

```text
docs/production_bible/00_read_order.md
docs/production_bible/self_update_protocol.md
docs/production_bible/story-production-kit/
```

Hard rule:

```text
Existing AGENTS / source index / master prompt rules / character settings / prohibition files remain higher priority.
The story-production-kit files are a supporting style and quality-control layer only.
They improve emotional retention, first-three-second hooks, dialogue rhythm, anti-drag pacing, episode continuity, AI video adaptation, and CapCut planning.
They must not overwrite canon, character identity, character voice, relationship logic, reveal order, or existing contract rules.
```

Before future novel, storyboard, image prompt, video prompt, or CapCut work, read:

```text
docs/production_bible/00_read_order.md
docs/production_bible/story-production-kit/26_canon_character_priority_over_reference_video.md
docs/production_bible/story-production-kit/27_novel_ai_short_drama_gold_standard.md
docs/production_bible/story-production-kit/29_story_density_no_drag_execution_gate.md
docs/production_bible/story-production-kit/30_bad_example_quarantine_and_style_do_not_copy.md
docs/production_bible/story-production-kit/25_dialogue_clarity_and_global_quality_gate.md
docs/production_bible/story-production-kit/24_dialogue_freshness_and_non_template_rules.md
```
