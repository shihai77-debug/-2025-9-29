# AGENTS.md｜《棺中檀色》EP20 提示词工作规则

本仓库用于管理《棺中檀色》/《黑棺里的女人》分镜、导演参考图、角色锁定、视频生成提示词规则。

当用户在对话中写 `@GitHub`、`GitHub 기준`、`Codex 기준`、`저장소 기준` 时，必须优先读取本仓库中的对应文件，而不是凭记忆生成。

---

## 1. EP20 最高优先级文件

EP20 CUT 视频提示词必须按以下优先级执行：

1. `outputs/episode20_final_cut_source_index.md`  
   - 唯一权威来源：CUT 原文对白 / BGM / SFX / 时长 / 角色 / 场景 / 道具约束。
   - 对白、BGM、SFX 必须逐字使用，不得创作、改写、增删、重排。

2. `outputs/episode20_master_prompt_rules.md`  
   - EP20 通用画面、角色、背景、道具、禁忌规则。

3. `outputs/episode20_jimeng_video_prompt_contract.md`  
   - 即梦 / Seedance 视频提示词输出格式与校验规则。

4. 用户上传的批准 storyboard reference board  
   - 只参考构图、站位、动线、镜头节奏、道具位置。
   - 不参考黑白画风、文字、箭头、编号、边框。

---

## 2. 绝对禁止

- 禁止根据 storyboard board 上的英文注释自行编写台词。
- 禁止把 board 的 `CASE BRIEFING`、`NO HANDOFF`、`DOCS WITH SHEN` 当成最终台词。
- 禁止把参考图上的文字、箭头、编号、边框生成到最终视频。
- 禁止在源文件没有 BGM / SFX 时自行添加风声、纸声、摩托车声或音乐。
- 禁止把 `檀缺` 写成 `白清檀`。
- 禁止把 `黑七` 生成成黑狼、狗、人、怪物。
- 禁止把 `韩知玄` 胸前标识写成 `辑灵司`；必须是 `镇灵司`。

---

## 3. 源文件缺失时的处理

如果用户要求“必须使用 `outputs/episode20_final_cut_source_index.md` 的 CUT 原文”，但文件不存在或读取失败：

1. 不得创作台词。
2. 不得用记忆补台词。
3. 必须先告知用户源文件缺失。
4. 只有用户提供原文或允许补写时，才能继续生成。

---

## 4. EP20 CUT-02 当前固定点

CUT-02 批准板是 Shen 打开背包取出文件并进行案情说明的镜头。

固定要求：

```text
角色：陆沉舟 / 黑七 / 檀缺 / 韩知玄 / Shen
中央女性：檀缺，不是白清檀
背景：BG A，昆仑余波后的冷灰旷野 + 远处淡淡现代城市剪影
动作：Shen 打开背包，取出文件，文件只在 Shen 手中
限制：NO HANDOFF，文件不交给任何人
镜头：CAM HOLD，0-5秒 + 5-11秒
```

CUT-02 的最终对白、BGM、SFX 只能从 `outputs/episode20_final_cut_source_index.md` 读取。
