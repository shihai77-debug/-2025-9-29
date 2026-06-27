# Faceless Style Reference Mode｜无五官风格定位参考图规则

This mode is for storyboard reference boards and intermediate planning images when exact face generation is unstable.

It is not a final video face rule. It is a safer reference-image mode that keeps character identity through silhouette, hairstyle, outfit, body proportion, posture, screen position, and movement direction while avoiding broken facial details.

## Core Rule

```text
脸可以出现，但不要画清楚眼睛、鼻子、嘴巴等五官细节。
保留脸部外轮廓、头部方向、发型、发量、刘海、侧脸角度、下颌线大轮廓。
人物身份通过发型、服装、身形、姿态、位置、道具和标签来锁定。
```

## Use When

Use this mode when:

- generated faces drift, shake, melt, or mix characters.
- storyboard boards produce wrong faces even with turnaround sheets.
- the image is used mainly for blocking, actor position, camera path, props, and continuity.
- Jimeng / Seedance will still receive character turnaround sheets in the final video prompt.

## Allowed

- face outline.
- head shape.
- hair silhouette.
- hairstyle from turnaround sheet.
- side/back/three-quarter head direction.
- soft face plane with no detailed eyes, nose, or mouth.
- light sketch-like person rendering.
- clear outfit, body proportion, posture, and position.

## Not Allowed

- detailed eyes.
- detailed nose.
- detailed mouth.
- expressive realistic face close-up.
- different face from turnaround sheet.
- random beautiful face.
- face copied from another character.
- blurred blob body with no hairstyle or costume identity.

## Character Identity Lock

Even without facial features, character identity must remain clear.

Use the turnaround sheets for:

- hairstyle and hair volume.
- hair length and silhouette.
- outfit cut, coat length, skirt/pants shape, boots, bag, uniform marks.
- body proportion and height relationship.
- temperament through posture.
- recurring props.

For EP20:

```text
陆沉舟：黑色皮夹克、黑T、黑裤、黑靴，疲惫坐姿或冷静风水师姿态，头发凌乱但轮廓固定。
黑七：一只小型黑色狐狸，狐狸身体轮廓清楚，不是狗，不是狼，不是人。
檀缺：深色现代日常装，深色开衫/外套、深色上衣、黑色裙装，安静克制，不穿白衣。
韩知玄：黑色长款镇灵司制服，公务式站姿，胸前“镇灵司”标识可简化但身份明确。
沈泊川：黑色皮夹克、黑裤、黑靴、黑色背包、摩托车相关动作，青年市井感。
```

## Image Style

```text
背景可以相对清楚、空间关系明确。
人物线条和明暗要更轻，不要像最终照片一样重。
人物可用浅灰、低对比、半写实草图感处理。
衣服轮廓、发型轮廓、道具轮廓必须清楚。
脸部只画轮廓，不画清楚五官。
整体仍是导演参考图，不是最终彩色视频帧。
```

## Acting Rule

Faceless style does not mean no acting.

```text
用头部角度、肩颈紧张、手部停顿、身体重心、呼吸姿态表现情绪，不依赖清晰五官表情。
```

## Prompt Snippet

```text
启用无五官风格定位参考图模式：人物脸部可以出现，但只保留脸部外轮廓、头部方向和发型轮廓，不画清楚眼睛、鼻子、嘴巴。人物身份通过三面图对应的发型、服装、体型、姿态、道具和画面位置锁定。背景空间可以更清楚，人物线条和明暗更轻，低对比、半写实导演参考图风格，不要照片级面部细节。所有人物仍然要有演员式身体表演，用头部角度、肩颈、手部、呼吸姿态和身体重心表现情绪。
```

Negative prompt:

```text
清晰五官，详细眼睛，详细鼻子，详细嘴巴，漂亮随机脸，换脸，混脸，五官闪烁，脸部融化，照片级人脸，过度写实人脸，人物重黑，人物抢过背景，模糊到无法识别服装和发型，丢失发型轮廓，丢失服装轮廓，角色身份不明。
```

## Final Video Prompt Reminder

When using this reference board for Jimeng / Seedance:

- state that the board is only for blocking and position.
- state that final faces must follow the character turnaround sheets.
- if exact face is needed, use exact face/style mode.
- if the shot is a master shot or action node, the faceless reference board is acceptable.
- if the shot is a dialogue shot, use a clean keyframe with speaker face large enough.
