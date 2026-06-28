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

8. `outputs/character_positioning_image_usage_rules.md`
   - 当用户上传“无五官定位图 / 角色定位图 / 스케치定位图”时使用。
   - 角色定位图不是最终画面素材，也不是复制粘贴素材。
   - 只用于锁定人物身份、发型、服装、体型、姿态、轮廓和方向。
   - 多人画面超过 2 个清晰人脸时，不画清楚五官，用发型、服装、身形、姿态、道具和位置区分角色。

9. `outputs/character_positioning_prompt_snippets.md`
   - 角色定位图提示词片段库。
   - 用于在分镜分割图 / storyboard reference board / 演技参考图 prompt 顶部快速插入定位图规则和失败防止句。

10. 用户上传的批准 storyboard reference board
   - 只参考构图、站位、动线、镜头节奏、道具位置、空间连续。
   - 不参考人物脸、服装细节、黑白画风、文字、箭头、编号、边框。

11. 用户上传的三面图 / 角色参考图
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
角色定位图 = 分镜草图 / 分镜分割图 / storyboard reference board 的外形、发型、服装、体型、姿态、轮廓、方向参考。
```

禁止把批准board里的人脸、服装、临时画法当成最终角色外貌。
禁止把角色定位图当成最终画面素材、白底贴图、复制粘贴素材或最终视频人脸。
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
禁止把角色定位图的白底背景复制进分镜画面。
禁止把角色定位图直接贴进画面。
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
master shot / dialogue shot / reaction shot / cutaway / action node / speaking node
```
