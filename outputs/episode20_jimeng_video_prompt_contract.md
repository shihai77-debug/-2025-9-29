# EP20 Jimeng Video Prompt Contract｜第20集即梦视频提示词契约

本文件规定当用户要求“@GitHub CUT-XX 批准板 기준 지멍 영상 프롬”时，最终回复必须如何生成。

---

## 1. 读取顺序

生成提示词前必须读取：

```text
1. outputs/episode20_final_cut_source_index.md
2. outputs/episode20_master_prompt_rules.md
3. 用户上传或指定的批准 storyboard reference board
```

其中 `episode20_final_cut_source_index.md` 是对白 / BGM / SFX 的唯一来源。

---

## 2. 输出语言与格式

最终给用户的是**可直接复制到即梦 / Seedance 2.0 的中文视频提示词**。

推荐格式：

```text
【即梦 / Seedance 2.0 图生视频提示词】

参考素材：...

严格遵循...

场景...

角色...

时间分割...

对白...

BGM...

SFX...

画质稳定...

【负面提示】...

总时长：X秒
```

不要输出“等待用户自己粘贴台词”的占位符。  
如果 source index 里有原文台词，必须直接写进提示词。  
如果 source index 里写 BGM / SFX 为“无”，必须直接写“无背景音乐 / 无音效 / 无环境声”。

---

## 3. 对白契约

```text
对白必须来自 outputs/episode20_final_cut_source_index.md。
对白只出现一次。
不得改写。
不得新增。
不得删减。
不得重排。
不得拆成多段。
不得显示字幕。
```

大声提醒：

```text
storyboard board 上的英文标签不是台词。
CASE BRIEFING 不是台词。
NO HANDOFF 不是台词。
DOCS WITH SHEN 不是台词。
```

---

## 4. BGM / SFX 契约

```text
BGM 必须来自 source index。
SFX 必须来自 source index。
如果 source index 写“无”，最终提示词不得添加任何声音。
不得私自补风声、纸张声、摩托车声、衣料摩擦声、环境声。
```

---

## 5. 批准 board 契约

批准 storyboard reference board 只参考：

```text
构图
站位
动线
镜头节奏
时间分割
道具位置
空间关系
```

不参考：

```text
黑白画风
文字
箭头
编号
边框
临时人物外形
英文注释
```

---

## 6. CUT-02 即梦提示词必须包含的内容

当生成 CUT-02 时，必须包含：

```text
参考素材：@陆沉舟三面图、@黑七狐狸参考图、@檀缺三面图、@韩知玄三面图、@Shen角色参考图、@第20集CUT-02批准 storyboard reference board。

本CUT只出现五个角色：陆沉舟、黑七、檀缺、韩知玄、Shen。
中央女性是檀缺，不是白清檀。
黑七必须是小型黑色狐狸。
韩知玄胸前是“镇灵司”，不是“辑灵司”。
Shen文件只在自己手中，不递给任何人。
```

时间分割：

```text
总时长11秒。
0-5秒：Shen打开背包，取出文件。
5-11秒：Shen手持文件进行案情说明，文件不交接。
```

对白必须直接使用 source index 中 CUT-02 的原文：

```text
【Shen】委托人只说，让我把这份情况带给你们。文件不外借。
```

BGM / SFX：

```text
BGM：无
SFX：无
```

---

## 7. CUT-02 最终提示词校验表

生成前逐项检查：

```text
[ ] 使用@檀缺三面图，不使用白清檀参考。
[ ] 只出现陆沉舟、黑七、檀缺、韩知玄、Shen。
[ ] 黑七是小型黑色狐狸，不是狼/狗/人。
[ ] 韩知玄是镇灵司，不是辑灵司。
[ ] Shen文件不交接。
[ ] 对白已直接写入提示词，不是占位符。
[ ] 对白只出现一次。
[ ] BGM写无。
[ ] SFX写无。
[ ] 没有私自添加环境声。
[ ] Board只当构图/动线参考。
[ ] 最终画面是高质量彩色真人电影画面。
```

---

## 8. 如果源文件读取失败

如果 `outputs/episode20_final_cut_source_index.md` 读取失败：

```text
不要创作台词。
不要给带占位符的最终提示词。
先告诉用户 source index 读取失败，并要求确认路径或重新上传文件。
```
