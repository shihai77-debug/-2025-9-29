# EP20 Master Prompt Rules｜第20集视频提示词总规则

本文件用于 EP20 所有 CUT 的 storyboard reference board、clean keyframe、即梦 / Seedance 视频提示词。
若与 `outputs/episode20_final_cut_source_index.md` 冲突，以 source index 为准。

目标不是机械复制分镜，而是在不改故事、不改对白、不改事件顺序的前提下，用更像导演的方式把镜头、表演、声音、人物位置和剪辑做稳定。

---

## 1. Source Priority

每个 CUT 必须先读取：

```text
outputs/episode20_final_cut_source_index.md
outputs/dialogue_timing_fit_audit_rules.md
outputs/movement_position_continuity_audit_rules.md
outputs/smart_prompt_execution_protocol.md
```

优先级：

```text
对白 / BGM / SFX / 环境音 / 情绪 / 声音 / 时长 = final CUT source index。
构图 / 站位 / 镜头 / 道具空间 = 批准 storyboard board。
台词字数 / 安全语速 / 最低安全时长 = dialogue timing fit audit rules。
人物起点终点 / 动线 / 屏幕位置 / 防瞬移 = movement position continuity audit rules。
人物脸 / 发型 / 服装 / 体型 / 气质 = 三面图 / 角色参考图。
最终视频源图 = clean keyframe，不直接用带字 board。
```

执行规则：

```text
对白必须逐字使用。
BGM必须逐字使用。
SFX和环境音必须按source使用。
不得创作、改写、增删、重排对白。
不得因为storyboard board没写声音就删除对白、BGM、SFX或环境音。
不得把背景连续当成人物连续。
长台词不能硬塞进短秒数；必须延长、拆节点，或建议画面与配音分离。
```

---

## 2. Smart Execution Order

每次输出 storyboard prompt、clean keyframe prompt、即梦 / Seedance 视频提示词前，必须按以下顺序执行：

```text
1. Source extraction：从source index提取对白、说话人、BGM、SFX、环境音、时长、道具、情绪、continuity anchor。
2. Board extraction：只从批准board提取构图、站位、动线、镜头、道具位置、空间连续。
3. Reference lock：用三面图/角色参考图锁定脸、发型、服装、体型、年龄感、气质。
4. Risk diagnosis：诊断台词密度、脸部稳定、3人以上同框、动作+台词冲突、道具交接、音频层级、配角木偶风险、空镜拖节奏、人物位置漂移、缺少动线。
5. Flow pacing diagnosis：KEEP / COMPRESS / MERGE / REPLACE / PASS_PROPOSAL。
6. Dialogue timing fit audit：计算台词字数、安全语速、停顿/气口、动作占用、最低安全时长。
7. Movement position continuity audit：检查每个可见角色的起点、终点、屏幕百分比、景深层级、身体朝向、视线方向、移动路径、锁定状态、下一节点衔接。
8. Filming decision：决定原时长、延长、拆节点、master/dialogue/reaction/cutaway、faceless master、clean keyframe、cutaway support 或后期配音。
9. Prompt writing：再写最终提示词。
10. Self-repair：输出前补齐对白、BGM/SFX、角色数量、道具状态、continuity、演员式读法、音频层级、脸部稳定、台词时长适配、人物位置表、人物移动表。
```

禁止机械复制分镜。必须像 source-locked director：故事不乱改，拍法要聪明。

---

## 3. Character Locks

最终输出必须使用中文角色名和中文语音标签，不使用英文缩写当最终角色名。

```text
LU -> 陆沉舟
HEIQI -> 黑七
TAN -> 檀缺
HAN -> 韩知玄
SHEN -> 沈泊川
```

角色外貌：

```text
陆沉舟：严格参考@陆沉舟三面图。黑色短款皮夹克，黑色T恤，深色长裤，黑色靴子，年轻男性，黑色短发，疲惫但稳定。禁止变成沈泊川、韩知玄、镇灵司制服。
黑七：严格参考@黑七狐狸参考图。必须是一只小型黑色狐狸，不是黑狼、狗、猫、人、怪物，不出现第二只狐狸。
檀缺：严格参考@檀缺三面图。深色现代日常装，冷静克制。不是白清檀，不穿白衣，不穿黑色古风长裙。
韩知玄：严格参考@韩知玄三面图。黑色短发，黑色长款镇灵司制服外套，胸前“镇灵司”标识。不要写成“辑灵司”。不要变成沈泊川。
沈泊川：严格参考@沈泊川角色参考图。20多岁清洁服务公司年轻老板 / 现场负责人 / 青年委托人。灰绿或深灰工作衬衫外套，深灰T恤，棕色工装裤，棕色工作靴，卡其色实用双肩包/工具包。摩托车和头盔只作为交通/入场道具。禁止使用@Shen角色参考图。不是陆沉舟黑色皮夹克男主风，不是韩知玄镇灵司制服，不是黑皮骑手重装。
```

人物数量：

```text
CUT-01 至 CUT-07：只允许五个角色：陆沉舟、黑七、檀缺、韩知玄、沈泊川。每个角色只出现一次。
CUT-08 至 CUT-15：只允许四个角色：陆沉舟、黑七、檀缺、沈泊川。韩知玄已经离场，不再出现。
```

---

## 4. Face Stability And Split Rule

```text
一个 storyboard panel、clean keyframe、video node 最多两个清晰真人脸。
3人以上清晰脸同框 = 高脸崩风险。
3人以上只允许作为faceless/blocking master shot，不承载精确脸和长台词。
重要对白必须放到1人或2人dialogue shot。
```

推荐拆法：

```text
5 characters -> faceless/blocking master + 2-person dialogue/action shot + 2-person reaction shot + fox/prop/environment cutaway。
4 characters -> faceless/blocking master + 2-person shot + 2-person reaction。
3 characters -> 2-person shot + 1-person reaction，或 faceless 3-person master。
```

---

## 5. Dialogue Timing Gate

大段台词必须先算时间，不许凭感觉塞秒数。

```text
台词时长适配：
角色：
原台词：
台词字数：
安全语速：
裸读所需：
停顿/气口：
动作占用：
听者反应/尾音：
最低安全时长：
原分镜窗口：
判断：可用 / 不可用
处理：原时长 / 延长到X秒 / 拆成X个视频节点 / 建议后期配音
```

判断标准：

```text
short line: 1.5-3s plus breath/reaction.
medium line: 3-6s plus breath/reaction.
long line: 6-10s plus breath/reaction.
information-heavy exposition: 8-12s or split.
two exposition lines in one CUT: usually 16-20s, or two separate video nodes.
```

语速预算：

```text
normal dramatic Mandarin dialogue: 4.0-4.8 Chinese characters per second.
exposition / professional analysis / clue explanation: 3.6-4.2 Chinese characters per second.
emotional, restrained, or weighty delivery: 3.2-4.0 Chinese characters per second.
rushed upper limit: 5.0 Chinese characters per second, but avoid this for final video prompts.
```

CUT-10 硬规则：

```text
CUT-10 原10秒单视频不可用。
CUT-10A：10秒，第一句43字，最低安全9.5-10秒。
CUT-10B：8秒，第二句29字，最低安全7.5-8秒。
如果平台限制15秒，不要把两句硬塞进15秒；必须拆成10A/10B。
```

---

## 6. Movement Position Gate

背景连续不等于人物连续。每个 storyboard board / clean keyframe / 视频 prompt 必须写清楚人物位置与动线。

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
镜头运动不等于人物运动。
位置锁定不等于木头人。
锁定角色必须有眼神、呼吸、肩颈、手指、重心等微反应。
移动角色必须写 start -> path -> end。
上一节点终点必须等于下一节点起点，除非source明确说明画面外移动。
```

禁止：

```text
只写“在旁边 / 在后方 / 在画面里”。
同一角色无路径地从左跳到右。
应该锁定的听者突然走动。
source要求入场/停下/转身，但prompt没有人物移动路径。
镜头移动被误写成人物移动。
```

---

## 7. Storyboard Board And Clean Keyframe

批准 storyboard board 只用于：

```text
构图、人物站位、动线、镜头节奏、时间分割、道具位置、空间关系、continuity anchor。
```

禁止用于：

```text
最终画风、角色脸、角色发型细节、角色服装细节、角色体型、角色气质、文字、箭头、编号、边框、英文标签、临时注释、对白创作、BGM创作、SFX创作。
```

最终 clean keyframe：

```text
16:9彩色真人电影画面。
无文字、无箭头、无标签、无分镜边框。
人物脸严格来自三面图，不来自storyboard board。
说话者/动作主体脸部足够大，五官清晰稳定。
一个画面最多两个清晰真人脸。
无重复人物，无额外路人，角色数量正确。
```

---

## 8. Camera Path Rule

如果只是摄像机移动，人物动作/情绪/道具/地点没有变化，不要硬拆多个面板。用镜头路径说明。

```text
镜头路径：
1. 起点：固定全景，说明镜头位置、方向、景别。
2. 移动：说明横移/推进/摇镜方向、速度、保留哪些人物位置。
3. 调整：说明如何接住动作主体，不切角、不跳焦。
4. 落幅：说明最终落到谁、什么景别、保留哪些空间关系。
```

禁止：

```text
只写“镜头移动”。
只写“跟拍”。
镜头移动中人物世界位置不明。
镜头路径和人物路径混在一起。
```

---

## 9. Acting And Audio

所有人物都要像演员一样表演。

```text
主角通过台词、呼吸、视线、手部、身体紧张表达情绪。
配角不能像木头人；即使位置锁定，也要有听戏反应。
位置锁定 = 屏幕位置不乱动，不等于身体和表情冻结。
情绪不用突然变大声表达，用语速、呼吸、停顿、尾音、眼神、手部动作表达。
```

每句对白必须包含：

```text
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
人声 > 核心音效 > 环境音 > BGM。
对白段BGM必须下压，不盖人声。
核心音效必须和动作点同步，不盖台词开头和尾音。
同一地点环境音保持连续，不突然变大或断裂。
```

---

## 10. Final Self-Check

输出前必须自检：

```text
[ ] 是否先读source index？
[ ] 是否保留原文对白、BGM、SFX、环境音？
[ ] 是否跑过导演诊断、节奏判断、台词时长适配、人物位置动线检查？
[ ] 是否计算了台词字数、安全语速、最低安全时长？
[ ] 如果台词过密，是否延长、拆节点、cutaway support 或建议后期配音？
[ ] 是否有 人物位置连续表 / 人物移动表 / 镜头与人物运动关系？
[ ] 是否分清镜头运动和人物运动？
[ ] 是否避免3人以上清晰脸 + 长对白？
[ ] 是否使用三面图/角色参考图锁定身份？
[ ] 沈泊川是否使用最新清洁服务公司老板参考，不是旧黑皮骑手？
[ ] 是否把storyboard board只当站位/镜头/道具参考？
[ ] 是否用clean keyframe作为最终I2V源图？
[ ] 是否有镜头路径、起点、移动、调整、落幅？
[ ] 是否有演员式表演、呼吸、停顿、听者反应？
[ ] 是否有人声 > 核心音效 > 环境音 > BGM？
[ ] 是否禁止重复人物、混脸、额外路人、黑七变狗狼人？
```
