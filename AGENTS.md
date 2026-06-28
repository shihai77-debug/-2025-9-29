# AGENTS.md｜《棺中檀色》EP20 提示词工作规则

本仓库用于管理《棺中檀色》EP20 分镜、导演参考图、角色锁定、storyboard reference board、clean keyframe、即梦 / Seedance 视频提示词规则。

当用户写 `@GitHub`、`GitHub 기준`、`Codex 기준`、`저장소 기준`、`CUT-XX 프롬`、`approved board 영상 프롬` 时，必须优先读取本仓库规则，不得凭记忆生成。

目标不是机械复制分镜，而是：故事不乱改，拍法要聪明，表演像真人，镜头能剪，声音能听，观众想继续看。

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
outputs/faceless_style_reference_mode_rules.md
outputs/exact_face_style_mode_rules.md
outputs/stable_character_video_prompt_template.md
outputs/character_positioning_image_usage_rules.md
outputs/character_positioning_prompt_snippets.md
outputs/legacy_prompt_files_do_not_use.md
```

然后再读取：

```text
用户上传的批准 storyboard reference board。
用户上传的三面图 / 角色参考图 / 角色定位图。
```

如果用户在当前消息里贴了最终CUT文本，以用户贴出的最终CUT文本覆盖较弱的旧board标签。

---

## 2. Source Priority

```text
对白 / BGM / SFX / 环境音 / 情绪 / 声音 / 时长 = final CUT source index。
构图 / 站位 / 动线 / 镜头 / 道具空间 = 批准board参考。
人物脸 / 发型 / 服装 / 体型 / 气质 = 三面图/角色参考图最高优先级。
智能执行顺序 / 自修流程 = smart prompt execution protocol。
镜头拆分 / master-dialogue-reaction-cutaway 判断 = cinematic shot grammar。
导演诊断 / 更聪明的拍法建议 = director intelligence layer。
节奏空镜 / 压缩合并 / 跳过建议 = flow pacing edit decision rules。
最终视频源图 = clean keyframe，不直接用带字board。
脸部不稳定时的分镜参考图 = faceless style reference mode。
角色定位图 = 分镜草图 / storyboard board 的外形、发型、服装、体型、姿态、轮廓、方向参考。
```

禁止把批准board里的人脸、服装、临时画法当成最终角色外貌。
禁止把角色定位图当成最终画面素材、白底贴图、复制粘贴素材或最终视频人脸。
禁止把 storyboard board 里没有写声音理解成无对白、无BGM、无SFX。

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
禁止让旧derived prompt覆盖AGENTS、source index、master rules、smart protocol、director rules、flow pacing rules、current turnaround sheets。
```

---

## 4. 智能执行协议硬规则

每次输出 storyboard prompt、clean keyframe prompt、即梦 / Seedance 视频提示词前，必须按顺序执行：

```text
1. Source extraction：先从source index提取对白、说话人、BGM、SFX、环境音、时长、道具、情绪、continuity anchor。
2. Board extraction：只从批准board提取构图、站位、动线、镜头、道具位置、空间连续。
3. Reference lock：用三面图/角色参考图锁定脸、发型、服装、体型、气质。
4. Risk diagnosis：诊断台词密度、脸部稳定、3人以上风险、动作+台词冲突、道具交接、音频层级、配角木偶风险、重复人物、身份混淆、空镜拖节奏。
5. Flow pacing diagnosis：KEEP / COMPRESS / MERGE / REPLACE / PASS_PROPOSAL。
6. Filming decision：决定是否原时长、延长、拆节点、master/dialogue/reaction/cutaway、faceless/blocking master、clean keyframe。
7. Prompt writing：再写最终提示词。
8. Self-repair：如果漏了对白、BGM、SFX、角色数量、道具状态、continuity anchor、演员式读法、音频层级、脸部稳定或节奏判断，必须先修正再输出。
```

如果用户只要“프롬만”, 可以隐藏诊断，但仍必须应用诊断结果。

---

## 5. 导演判断层硬规则

```text
故事锁定，拍法灵活。
原文对白、说话人、事件顺序、人物关系、BGM、SFX、环境音、关键道具状态不能改。
为了最终视频质量，可以重新设计视频节点数量、时长、景别、角度、反应镜头、cutaway、动作/台词拆分和表演节奏。
```

必须诊断：

```text
本CUT剧情核心是什么？
最大失败风险是什么：脸、台词、时间、动作、镜头、声音、情绪？
是否长台词塞进短秒数？
是否3人以上清晰脸同框？
是否动作和大段台词同时发生？
是否需要延长或拆成多个视频节点？
是否需要master shot / dialogue shot / reaction shot / cutaway？
是否存在无意义空白、拖慢节奏、重复反应、弱空镜？
```

---

## 6. Flow Pacing Gate

无对白或弱镜头不能盲目保留。必须分类：

```text
KEEP：承载情绪、悬念、反应、空间、道具或continuity。
COMPRESS：动作/移动有用但时长过长。
MERGE：与前后CUT重复，可自然合并。
REPLACE：原镜头弱，但需要用手、资料、门、灰尘、风声等cutaway保留连接。
PASS_PROPOSAL：无对白、无情绪、无信息、无位置/道具变化、无continuity价值，建议跳过但必须用户确认。
```

不得自动跳过或删除source内容。PASS必须先说明原因、说明转移哪些continuity anchor，并等用户确认。

---

## 7. 多人脸稳定规则

硬规则：

```text
一个生成用 storyboard panel、clean keyframe、video node 里最多两个清晰真人脸。
3人以上清晰脸同框 = 高脸崩风险。
3人以上只允许作为faceless/blocking master shot，不承载精确脸和长台词。
重要对白必须放到1人或2人dialogue shot。
```

推荐拆法：

```text
5 characters -> 2-person dialogue/action shot + 2-person reaction shot + fox/prop/environment cutaway。
4 characters -> 2-person shot + 2-person shot。
3 characters -> 2-person shot + 1-person reaction，或 faceless 3-person master。
```

多人同场必须靠 continuity anchor 保持关系：

```text
same background direction.
same prop state.
same eye-line direction.
same screen geography.
same audio bed.
same BGM/SFX continuation.
```

---

## 8. 角色锁定

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

CUT-01 至 CUT-07：

```text
只允许五个角色：陆沉舟、黑七、檀缺、韩知玄、沈泊川。
每个角色只出现一次。
禁止第二个陆沉舟、第二个沈泊川、第二个韩知玄、第二个檀缺、第二只黑七。
```

CUT-08 至 CUT-15：

```text
只允许四个角色：陆沉舟、黑七、檀缺、沈泊川。
韩知玄已经离场，不再出现。
每个角色只出现一次。
```

---

## 9. Storyboard / Clean Keyframe

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

## 10. 声音与表演

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
位置锁定 = 屏幕位置不乱动，不等于身体和表情冻结。
配角也要有听戏反应：眼神、呼吸、肩颈、手指、身体重心。
```

---

## 11. 绝对禁止

```text
禁止创作对白。
禁止改写对白。
禁止删减对白。
禁止把 board 的 CASE BRIEFING / NO HANDOFF / DOCS WITH SHEN 当成台词。
禁止把 board 没写声音理解成无对白/无BGM/无SFX。
禁止把参考图上的文字、箭头、编号、边框生成到最终视频。
禁止把角色定位图的白底背景复制进分镜画面。
禁止把角色定位图直接贴进画面。
禁止把檀缺写成白清檀。
禁止把黑七生成成黑狼、狗、人、怪物。
禁止把韩知玄胸前标识写成“辑灵司”；必须是“镇灵司”。
禁止把沈泊川写回旧黑皮骑手或@Shen角色参考图。
禁止把多人远景 + 长台词 + 复杂动作硬塞进一个视频节点。
禁止在 faceless style reference board 中画清楚眼睛、鼻子、嘴巴。
```

---

## 12. Final Self-Check

输出前必须检查：

```text
[ ] Did I read source index first?
[ ] Did I read smart / cinematic / director / flow / positioning / legacy rules?
[ ] Did I preserve exact dialogue, BGM, SFX, environment sound?
[ ] Did I run director diagnosis and flow pacing diagnosis?
[ ] Did I avoid 3+ clear human faces with long dialogue?
[ ] Did I use turnaround sheets / role references for identity?
[ ] Is 沈泊川 the current cleaning-service company boss, not old black leather biker?
[ ] Did I use storyboard board only for blocking/camera/props/continuity?
[ ] Did I use clean keyframe for final I2V source when face stability matters?
[ ] Did I include camera path: start / move / adjust / land?
[ ] Did I include actor-style breath, pause, listening reaction, and audio mix?
[ ] Did I prevent duplicate characters, mixed faces, extra people, and 黑七 dog/wolf errors?
```
