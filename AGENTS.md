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

4. `outputs/cinematic_shot_grammar_rules.md`
   - 电影化镜头拆分规则：master shot / dialogue shot / reaction shot / cutaway / action node / speaking node。
   - 用于判断是否延长、拆节点、改成中近景、使用 clean keyframe。

5. `outputs/stable_character_video_prompt_template.md`
   - 当人物混脸、角色不稳、多人同框、道具/动物/假人容易错时使用。

6. `outputs/exact_face_style_mode_rules.md`
   - 当用户要求脸和风格尽量准确时使用：face lock image -> style lock -> clean keyframe -> video prompt。

7. `outputs/faceless_style_reference_mode_rules.md`
   - 当 storyboard / reference board 的人脸反复出错时使用。
   - 规则：脸部可以出现，但只保留脸部外轮廓、头部方向、发型轮廓，不画清楚眼睛、鼻子、嘴巴。
   - 角色身份通过三面图对应的发型、服装、体型、姿态、道具、位置来锁定。

8. 用户上传的批准 storyboard reference board
   - 只参考构图、站位、动线、镜头节奏、道具位置、空间连续。
   - 不参考人物脸、服装细节、黑白画风、文字、箭头、编号、边框。

9. 用户上传的三面图 / 角色参考图
   - 人物脸、发型、服装、体型、年龄感、气质、轮廓的最高优先级。

---

## 2. Source Priority

```text
对白 / BGM / SFX / 情绪 / 声音 / 时长 = source index 优先。
构图 / 站位 / 动线 / 镜头 / 道具空间 = 批准board参考。
人物脸 / 发型 / 服装 / 体型 / 气质 = 三面图/角色参考图优先。
镜头拆分 / 是否master、dialogue、reaction、cutaway = cinematic shot grammar 优先。
最终视频源图 = clean keyframe 优先，不直接用带字board。
脸部不稳定时的分镜参考图 = faceless style reference mode 优先。
```

禁止把批准board里的人脸、服装、临时画法当成最终角色外貌。
禁止把 storyboard board 里没有写声音理解成无对白、无BGM、无SFX。

---

## 3. 绝对禁止

```text
禁止创作对白。
禁止改写对白。
禁止删减对白。
禁止把 board 的 CASE BRIEFING / NO HANDOFF / DOCS WITH SHEN 当成台词。
禁止把 board 没写声音理解成无对白/无BGM/无SFX。
禁止把参考图上的文字、箭头、编号、边框生成到最终视频。
禁止把檀缺写成白清檀。
禁止把黑七生成成黑狼、狗、人、怪物。
禁止把韩知玄胸前标识写成“辑灵司”；必须是“镇灵司”。
禁止把多人远景 + 长台词 + 复杂动作硬塞进一个视频节点。
禁止在 faceless style reference board 中画清楚眼睛、鼻子、嘴巴。
```

---

## 4. 人物数量与混淆自检

每次输出视频提示词前必须做角色审计。

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

## 5. 电影化镜头拆分默认规则

默认使用真实拍摄逻辑，不机械地把一个CUT拆成A/B。

必须先判断镜头功能：

```text
镜头功能判断：
- 本CUT原始功能：
- 是否三人以上同框：
- 是否包含长台词：
- 是否包含复杂动作：
- 是否需要精确脸：
- 风险判断：
- 建议拆分：
```

常用拆分：

```text
master shot：建立空间、关系、站位、群体沉默，不承载长台词。
dialogue shot：重要台词，1-2人中近景，保护脸、口型、演员表演。
reaction shot：听者反应，眼神、呼吸、手部、肩颈微动，承接情绪。
cutaway：手、资料、背包、头盔、摩托、门、积灰、街角，用来承载线索和声音。
action node：走位、入场、开包、取物、停车、转身。
speaking node：稳定说话，脸清楚，少运动，保护口型。
```

必须拆开的情况：

```text
三人以上同框 + 长台词。
复杂动作 + 长台词。
远景小脸 + 要求口型。
入场动作 + 情绪近景。
道具操作 + 信息量很大的说明台词。
脸已经不稳 + 重要台词。
```

优先拆成：

```text
master shot -> dialogue shot -> reaction shot -> cutaway
```

或：

```text
action node -> speaking node -> reaction/cutaway
```

这不是降低质量，是电影化剪辑语法，目的是提高脸部稳定、台词听感、演员表演和画面完成度。

---

## 6. Faceless Style Reference Mode｜无五官风格定位参考图

当 storyboard / 分割参考图的人脸反复生成错误时，不要强迫模型画清楚五官。

正确做法：

```text
脸部可以出现，但只保留脸部外轮廓、头部方向、发型轮廓。
不要画清楚眼睛、鼻子、嘴巴。
人物身份通过三面图对应的发型、服装、体型、姿态、道具、画面位置锁定。
背景空间可以清楚，人物线条和明暗要更轻，低对比、半写实导演参考图风格。
```

这个模式只用于：

```text
storyboard reference board。
shot blocking board。
multi-character master shot reference。
action path / camera path planning。
continuity anchor image。
```

不要作为唯一来源用于：

```text
最终台词特写。
最终口型同步。
精确面部表演。
重要dialogue shot。
```

表演仍然必须存在，但通过身体完成：

```text
用头部角度、肩颈紧张、手部停顿、身体重心、呼吸姿态表现情绪，不依赖清晰五官表情。
```

推荐片段：

```text
启用无五官风格定位参考图模式：人物脸部可以出现，但只保留脸部外轮廓、头部方向和发型轮廓，不画清楚眼睛、鼻子、嘴巴。人物身份通过三面图对应的发型、服装、体型、姿态、道具和画面位置锁定。背景空间可以更清楚，人物线条和明暗更轻，低对比、半写实导演参考图风格，不要照片级面部细节。所有人物仍然要有演员式身体表演，用头部角度、肩颈、手部、呼吸姿态和身体重心表现情绪。
```

负面提示：

```text
清晰五官，详细眼睛，详细鼻子，详细嘴巴，漂亮随机脸，换脸，混脸，五官闪烁，脸部融化，照片级人脸，过度写实人脸，人物重黑，人物抢过背景，模糊到无法识别服装和发型，丢失发型轮廓，丢失服装轮廓，角色身份不明。
```

---

## 7. Clean Keyframe Rule

批准 storyboard board 是导演参考图，不是最终图生视频源图。

如果用户要稳定脸和人物身份，必须建议或生成 clean keyframe：

```text
16:9彩色真人电影画面。
无文字、无箭头、无标签、无分镜边框。
人物脸严格来自三面图，不来自storyboard board。
说话者/动作主体脸部足够大，五官清晰稳定。
无重复人物，无额外路人，角色数量正确。
```

带文字、箭头、分格、远景小脸的 storyboard board 只做 blocking / camera / prop / continuity 参考，不能直接当最终脸部参考。

如果 storyboard reference board 启用了 faceless style reference mode，最终视频提示词必须说明：该图只参考站位、动线、身体表演和空间关系；最终人物脸仍以三面图/角色参考图为准。

---

## 8. CUT-02 固定纠错

CUT-02 批准板是沈泊川打开背包取出资料并说明委托。

CUT-02 不能使用错误对白：

```text
“委托人只说，让我把这份情况带给你们。文件不外借。”
```

CUT-02 必须使用 source index 的两段沈泊川原文对白。

CUT-02 原始分镜为11秒，但若让视频模型同时生成语音和口型，必须使用15秒安全版，避免强行压缩语速导致口型和脸崩坏。更稳的方案是拆成 action node + speaking node。

---

## 9. 源文件缺失时

如果 `outputs/episode20_final_cut_source_index.md` 缺失或读取失败：

1. 不得创作台词。
2. 不得用记忆补台词。
3. 必须先告知用户 source index 缺失。
4. 只有用户提供原文或允许补写时，才能继续生成。

---

## 10. 台词时长与演员式读法

每次生成任意 CUT 视频提示词前，必须先做台词密度检查。不能把长台词硬塞进原分镜秒数里。

台词承载规则：

```text
无台词CUT：保持原时长，只检查动作和镜头。
短句：至少1.5-3秒，并保留开口前吸气和句尾停顿。
中等句：至少3-6秒，并保留自然断句。
长句：至少6-10秒，必须写出停顿点、重音词、气息转换。
信息量很大的长台词：至少8-12秒；如果仍然拥挤，必须延长CUT或拆成两个视频节点。
```

每个 CUT 输出前必须明确写出其中一种判断：

```text
原时长可承载台词，不需要延长。
台词偏密，建议延长到 X 秒。
台词过密，建议拆成 CUT-XX-A / CUT-XX-B 两个视频节点。
本CUT无台词，不需要台词时长调整。
```

演员式读法必须写完整，不允许只写“平稳朗读”或“正常语气”：

```text
声线基准：角色固定声线，不突然变高变低。
音量连续性：承接上一CUT音量基准，不忽大忽小。
语速：根据情绪微调，不能为了赶时间加速。
气息：开口前短吸气，长句中间自然换气。
外层情绪：观众能直接听见的情绪。
内层情绪：角色压在台词下面的心理状态。
重音词：必须点出2-4个关键词。
停顿点：必须标出自然停顿位置。
尾音处理：收住、放轻、压低、断开，按情绪选择。
口型与视线：说话时看谁，是否移开视线。
身体配合：手、肩、呼吸、眼神配合台词。
```

表演原则：

```text
人物像演员在现场表演，不像读稿。
情绪通过呼吸、停顿、语速、重音、眼神和手部细节表达。
禁止突然拔高音量制造情绪。
禁止全程一个调子念完。
禁止长台词无停顿。
禁止跨CUT同一角色声音忽大忽小。
```

---

## 11. 演员脸部稳定与防抖规则

视频提示词前必须先判断是否存在脸部风险：

```text
说话者脸太小：必须生成 clean keyframe 或改成中近景。
说话者在远景中讲长台词：必须延长、拆节点，或改成稳定中近景。
镜头横移/跟随同时讲长台词：必须拆成“动作节点”和“说话节点”。
多人同框且脸很小：只能作为站位参考，不能要求精准口型和稳定表情。
直接使用黑白分镜board做I2V：必须提示脸部漂移风险，建议先做clean keyframe。
```

演员脸部稳定锁必须写入最终视频提示词：

```text
演员脸部稳定锁：所有人物脸部严格以三面图/角色参考图为准，不参考storyboard board中的临时脸。说话者脸部清晰、五官稳定、身份不变；同一角色在整个CUT中保持同一张脸、同一发型、同一年龄感、同一气质。禁止脸部漂移、五官闪烁、换脸、混脸、脸部融化、背景复制主角脸。
```

如果用户要求“脸和风格尽量准确”，必须启用 `outputs/exact_face_style_mode_rules.md`：

```text
face lock image -> style lock image -> clean keyframe -> Jimeng / Seedance video prompt
```

重要台词镜头不能靠模糊脸解决。模糊、侧脸、背影、软焦只适合远景、过渡、无台词 master shot 或背景人物。

Faceless style reference mode 不是“最终脸模糊”。它只是不让 storyboard/reference board 画坏五官。最终视频仍由三面图/角色参考图锁脸。

---

## 12. 音频混音与BGM/SFX平衡规则

音频不能只写“有BGM/有音效”。每个CUT必须检查对白、核心音效、环境音、BGM之间的层级是否平衡。原则是听感清楚、空间真实、情绪连续，不允许某一层声音突然压住其他层。

源文件优先：

```text
BGM/SFX/环境音必须来自source index。
如果source index写无音乐，不得新增BGM。
如果source index写无SFX，不得自行创作SFX。
如果source index有环境音或核心音效，不得删除。
```

每个CUT输出前必须写音频混音判断：

```text
音频混音判断：本CUT有对白，人声必须最前，BGM/SFX全部下压。
音频混音判断：本CUT无对白，环境音和核心音效负责空间感，BGM只做低层情绪铺底。
音频混音判断：source index写无音乐，本CUT只保留对白/音效/环境音，不新增BGM。
音频混音判断：上一CUT声音需要淡出/承接，本CUT必须写明渐入、渐弱或留白。
```

相对音量参考只用于提示词表达，不是硬性分贝：

```text
人声：100，永远清晰居前。
核心音效：50-70，关键瞬间可短暂到75，但不能盖住人声。
环境音：18-30，持续铺底，不能抢戏。
BGM对白段：8-18，必须ducking下压，不盖住口型和台词。
BGM无对白段：18-35，按情绪轻推，不能突然煽情。
静默/余韵段：保留空气感，不要把所有声音填满。
```

---

## 13. Storyboard 标签语言规则

Storyboard reference board 可以有短标签、箭头、编号，但必须使用中文角色全名或中文短标签，禁止使用英文简称。

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
镜头横移跟随
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

原因：英文简称会削弱角色身份绑定，容易造成檀缺/白清檀、沈泊川/韩知玄、陆沉舟/沈泊川混淆。

Clean keyframe 与最终视频画面禁止出现任何标签、文字、箭头、编号或分镜边框。

---

## 14. 输出前自检

最终输出 storyboard prompt / clean keyframe prompt / Jimeng video prompt 前必须自检：

```text
[ ] 是否读取 source index，而不是只看图片？
[ ] 是否读取 cinematic shot grammar，并判断 master/dialogue/reaction/cutaway？
[ ] 是否避免多人远景 + 长台词？
[ ] 重要台词是否安排稳定中近景 dialogue shot？
[ ] 动作和说话是否必要时拆开？
[ ] 是否使用三面图锁脸，而不是 storyboard board 临时脸？
[ ] 如脸部生成不稳，storyboard/reference board 是否启用无五官风格定位参考图模式？
[ ] faceless style board 是否保留脸部外轮廓、头部方向、发型、服装、体型、姿态和位置？
[ ] faceless style board 是否禁止清楚眼睛、鼻子、嘴巴？
[ ] 是否写入演员脸部稳定锁？
[ ] 是否检查角色数量和人物混淆？
[ ] 是否保留 source index 的对白、BGM、SFX、环境音？
[ ] 是否有 @角色名 声音标签？
[ ] 是否写出台词时长判断和演员式读法？
[ ] 是否写出音频混音判断和音量优先级？
[ ] storyboard board 是否使用中文标签而不是英文简称？
[ ] clean keyframe / final video 是否无文字、无箭头、无分镜框？
```
