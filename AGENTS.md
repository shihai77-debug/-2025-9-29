# AGENTS.md｜《棺中檀色》EP20 提示词工作规则

本仓库用于管理《棺中檀色》EP20 分镜、导演参考图、角色锁定、storyboard reference board、clean keyframe、即梦 / Seedance 视频提示词规则。

当用户写 `@GitHub`、`GitHub 기준`、`Codex 기준`、`저장소 기준`、`CUT-XX 프롬`、`approved board 영상 프롬` 时，必须优先读取本仓库规则，不得凭记忆生成。

---

## 1. 必读文件顺序

EP20 CUT storyboard / clean keyframe / 视频提示词必须按以下顺序读取：

1. `outputs/episode20_final_cut_source_index.md`
   - 唯一权威来源：CUT 原文对白 / BGM / SFX / 时长 / 角色 / 场景 / 道具约束。
   - 对白、BGM、SFX 必须逐字使用，不得创作、改写、增删、重排。

2. `outputs/episode20_master_prompt_rules.md`
   - EP20 通用画面、角色、背景、道具、禁忌规则。

3. `outputs/episode20_jimeng_video_prompt_contract.md`
   - 即梦 / Seedance 视频提示词输出格式与校验规则。

4. `outputs/smart_prompt_execution_protocol.md`
   - 智能执行协议：先提取source，再读board，再风险诊断，再决定拍法，最后写prompt并自修。
   - 禁止机械复制分镜；必须像source-locked director一样执行。

5. `outputs/cinematic_shot_grammar_rules.md`
   - 电影化镜头拆分规则：master shot / dialogue shot / reaction shot / cutaway / action node / speaking node。
   - 用于判断是否延长、拆节点、改成中近景、使用 clean keyframe。

6. `outputs/director_intelligence_layer_rules.md`
   - 导演判断层：先诊断风险，再决定是否延长、拆分、改景别、增加反应镜头或cutaway。
   - 故事、对白、事件顺序锁定；拍法可以更聪明。

7. `outputs/stable_character_video_prompt_template.md`
   - 当人物混脸、角色不稳、多人同框、道具/动物/假人容易错时使用。

8. `outputs/exact_face_style_mode_rules.md`
   - 当用户要求脸和风格尽量准确时使用：face lock image -> style lock -> clean keyframe -> video prompt。

9. `outputs/faceless_style_reference_mode_rules.md`
   - 当 storyboard / reference board 的人脸反复出错时使用。
   - 规则：脸部可以出现，但只保留脸部外轮廓、头部方向、发型轮廓，不画清楚眼睛、鼻子、嘴巴。
   - 角色身份通过三面图对应的发型、服装、体型、姿态、道具、位置来锁定。

10. `outputs/character_positioning_image_usage_rules.md`
   - 当用户上传“无五官定位图 / 角色定位图 / 스케치定位图”时使用。
   - 角色定位图不是最终画面素材，也不是复制粘贴素材。
   - 只用于锁定人物身份、发型、服装、体型、姿态、轮廓和方向。

11. `outputs/character_positioning_prompt_snippets.md`
   - 角色定位图提示词片段库。
   - 用于在分镜分割图 / storyboard reference board / 演技参考图 prompt 顶部快速插入定位图规则和失败防止句。

12. 用户上传的批准 storyboard reference board
   - 只参考构图、站位、动线、镜头节奏、道具位置、空间连续。
   - 不参考人物脸、服装细节、黑白画风、文字、箭头、编号、边框。

13. 用户上传的三面图 / 角色参考图
   - 人物脸、发型、服装、体型、年龄感、气质、轮廓的最高优先级。

---

## 2. Source Priority

```text
对白 / BGM / SFX / 情绪 / 声音 / 时长 = source index 优先。
构图 / 站位 / 动线 / 镜头 / 道具空间 = 批准board参考。
人物脸 / 发型 / 服装 / 体型 / 气质 = 三面图/角色参考图优先。
智能执行顺序 / 自修流程 = smart prompt execution protocol 优先。
镜头拆分 / 是否master、dialogue、reaction、cutaway = cinematic shot grammar 优先。
导演诊断 / 更聪明的拍法建议 = director intelligence layer 优先。
最终视频源图 = clean keyframe 优先，不直接用带字board。
脸部不稳定时的分镜参考图 = faceless style reference mode 优先。
角色定位图 = 分镜草图 / 分镜分割图 / storyboard reference board 的外形、发型、服装、体型、姿态、轮廓、方向参考。
```

禁止把批准board里的人脸、服装、临时画法当成最终角色外貌。
禁止把角色定位图当成最终画面素材、白底贴图、复制粘贴素材或最终视频人脸。
禁止把 storyboard board 里没有写声音理解成无对白、无BGM、无SFX。

---

## 3. 智能执行协议硬规则

每次输出 storyboard prompt、clean keyframe prompt、即梦 / Seedance 视频提示词前，必须按顺序执行：

```text
1. Source extraction：先从source index提取对白、说话人、BGM、SFX、环境音、时长、道具、情绪、continuity anchor。
2. Board extraction：只从批准board提取构图、站位、动线、镜头、道具位置、空间连续。
3. Reference lock：用三面图/角色参考图锁定脸、发型、服装、体型、气质。
4. Risk diagnosis：诊断台词密度、脸部稳定、3人以上风险、动作+台词冲突、道具交接、音频层级、配角木偶风险。
5. Filming decision：决定是否原时长、延长、拆节点、使用master/dialogue/reaction/cutaway、使用faceless/blocking master。
6. Prompt writing：再写最终提示词。
7. Self-repair：如果漏了对白、BGM、SFX、角色数量、道具状态、continuity anchor、演员式读法或音频层级，必须先修正再输出。
```

禁止机械复制分镜。必须像 source-locked director：故事不乱改，拍法要聪明。

---

## 4. 导演判断层硬规则

不要机械复制分镜。每次输出 storyboard prompt、clean keyframe prompt、即梦 / Seedance 视频提示词前，必须先做导演诊断。

```text
故事锁定，拍法灵活。
原文对白、说话人、事件顺序、人物关系、BGM、SFX、环境音、关键道具状态不能改。
但可以为了最终视频质量，重新设计视频节点数量、时长、景别、角度、反应镜头、cutaway、动作/台词拆分和表演节奏。
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
```

如果用户只要“프롬만”, 可以隐藏诊断，但仍必须应用诊断结果。

---

## 5. 多人脸稳定规则

硬规则：

```text
一个生成用 storyboard panel、clean keyframe、video node 里最多两个清晰真人脸。
3人以上清晰脸同框 = 高脸崩风险。
3人以上只允许作为faceless/blocking master shot，不承载精确脸和长台词。
```

推荐拆法：

```text
5 characters -> 2-person dialogue/action shot + 2-person reaction shot + fox/prop/environment cutaway.
4 characters -> 2-person shot + 2-person shot.
3 characters -> 2-person shot + 1-person reaction, or a faceless 3-person master shot.
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

## 6. 绝对禁止

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
禁止把多人远景 + 长台词 + 复杂动作硬塞进一个视频节点。
禁止在 faceless style reference board 中画清楚眼睛、鼻子、嘴巴。
```

---

## 7. 角色锁定

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

混淆禁止：

```text
陆沉舟不能变成沈泊川或韩知玄。
沈泊川不能变成韩知玄。
韩知玄不能变成沈泊川。
檀缺不能变成白清檀，不能穿白衣，不能变成古风女王。
黑七只能是一只小型黑色狐狸，不能变成人、狗、狼、黑狼，不能出现第二只狐狸。
背景中不能出现长得像主角的额外人物。
```

---

## 8. 电影化镜头拆分默认规则

默认使用真实拍摄逻辑，不机械地把一个CUT拆成A/B。

必须先判断镜头功能：

```text
master shot / dialogue shot / reaction shot / cutaway / action node / speaking node
```

必须拆分的情况：

```text
three or more characters in wide shot + long dialogue.
three or more clear human faces in one generated frame.
complex action + long dialogue.
distant small face + lip sync required.
prop operation + information-heavy line.
unstable generated face + important line.
```

---

## 9. Faceless Style Reference Mode

当 storyboard/reference image 人脸反复失败时使用。

```text
Faces may appear, but only as face outline, head direction, and hairstyle silhouette.
Do not draw clear eyes, nose, or mouth.
Keep hairstyle, outfit, body shape, posture, props, screen position, and movement direction exact.
Background can be clear.
Characters should be lighter, lower contrast, pale-line storyboard style.
Acting must show through head angle, shoulders, hands, body weight, and breathing posture.
The image is not a final face reference.
Final video faces still follow the turnaround sheets.
```

---

## 10. Clean Keyframe Rule

批准 storyboard board 是导演参考图，不是最终 I2V 源图。

```text
Use storyboard board for blocking, camera, props, continuity.
Use clean 16:9 color keyframe for final I2V when face stability matters.
Clean keyframe has no labels, no arrows, no panel borders, no storyboard text.
Speaker/action subject must be large enough for stable face and mouth.
```

---

## 11. Dialogue And Audio

Dialogue must be copied exactly from `outputs/episode20_final_cut_source_index.md`.

Never invent, rewrite, summarize, shorten, merge, or replace dialogue.

Every spoken line must include:

```text
声线基准
音量连续性
语速
气息
外层情绪
内层情绪
重音词
停顿点
尾音处理
口型与视线
身体配合
```

Volume priority:

```text
voice > core SFX > environment sound > BGM
```

Do not crush long dialogue into a short duration. Extend or split into video nodes.

台词像人说，不像读稿：必须有开口前吸气、自然断句、关键词重音、句尾处理、听者反应或空气停顿。

---

## 12. Storyboard 标签语言规则

Storyboard reference board 可以使用短标签、箭头、编号，但必须使用中文角色全名或中文短标签，禁止使用英文简称。

必须使用：

```text
陆沉舟
黑七
檀缺
韩知玄
沈泊川
陆沉舟位置锁定
黑七位置锁定
檀缺位置锁定
韩知玄位置锁定
沈泊川入场
沈泊川停下
无沈泊川
头盔戴着
头盔摘下
背包关闭
无资料
背景连续
固定全景
摩托车入场
```

禁止使用：

```text
LU
TAN
HAN
SHEN
HEIQI
LU POS LOCK
TAN POS LOCK
HAN POS LOCK
SHEN ENTER
HEIQI POS LOCK
```

Clean keyframe 与最终视频画面禁止出现任何标签、文字、箭头、编号或分镜边框。

---

## 13. Final Self-Check

Before outputting any storyboard prompt, clean keyframe prompt, or Jimeng / Seedance video prompt:

```text
[ ] Did I read source index first?
[ ] Did I follow smart prompt execution protocol?
[ ] Did I run director diagnosis before writing the prompt?
[ ] Did I preserve exact dialogue, BGM, SFX, and environment sound?
[ ] Did I judge master/dialogue/reaction/cutaway/action/speaking function?
[ ] Did I avoid multi-person wide shot plus long dialogue?
[ ] Did I keep clear human faces to at most two per generated image/video node?
[ ] Did I use turnaround sheets for identity?
[ ] If faces are unstable, did I use faceless style reference mode?
[ ] Did I keep character count and prevent duplicate/confused characters?
[ ] Did I include actor-style delivery and audio mixing?
[ ] Did I keep storyboard labels Chinese and remove labels from final clean keyframes?
```
