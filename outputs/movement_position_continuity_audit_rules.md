# Movement Position Continuity Audit Rules｜人物位置 / 动线连续性强制检查

This file is mandatory for storyboard boards, clean keyframes, Jimeng prompts, Seedance prompts, and any prompt extracted from an approved board.

The agent must not wait for the user to point out that characters drift, teleport, stand like wooden props, or fail to move when the CUT requires movement.

## Core Rule

Background continuity is not enough. Every visible character must have a stable screen position, depth layer, body direction, gaze direction, and movement status.

```text
背景连续不等于人物连续。
人物连续必须同时锁定：起点位置、终点位置、屏幕百分比、前中后景层级、身体朝向、视线方向、动作状态、允许微反应、禁止动作。
```

## Required Position Table

Every storyboard prompt, clean keyframe prompt, and video prompt must include a compact position table when any character appears.

```text
人物位置连续表：
角色｜起点屏幕位置｜终点屏幕位置｜景深层级｜身体朝向｜视线方向｜状态锁定
```

Use screen percentages whenever possible.

```text
0% = far left, 50% = center, 100% = far right.
景深层级 = foreground / midground / background.
高度状态 = low / seated / standing / elevated.
```

Example:

```text
人物位置连续表：
陆沉舟｜x20% 前景低位坐姿｜x20% 前景低位坐姿｜前景｜身体朝右，头微低｜看向结界消散方向｜位置锁定，只允许呼吸和眼神微动
黑七｜x12% 前景低位趴伏｜x12% 前景低位趴伏｜前景｜身体朝右｜耳朵微动，看向沈泊川｜位置锁定，只允许耳朵/尾巴/呼吸微反应
沈泊川｜x95% 右侧骑摩托入画｜x78% 右侧停稳站立｜中前景｜身体朝左｜扫视四人｜移动角色，必须有入画路径和停稳终点
```

## Required Movement Table

If anyone moves, include a movement table.

```text
人物移动表：
角色｜是否移动｜起点｜路径｜终点｜速度/步数｜镜头关系｜禁止事项
```

For locked characters:

```text
人物移动表：
陆沉舟｜不移动｜坐姿位置锁定｜无行走路径｜保持原位｜只允许呼吸、手指、眼神微反应｜镜头可移动但他不跟随移动｜禁止起身、换边、靠近沈泊川
```

For moving characters:

```text
人物移动表：
沈泊川｜移动｜画面右侧边缘x95%｜骑摩托从右向左缓慢进入，沿碎石地面弧线靠近｜x78%右侧停稳，摘头盔｜慢速，真实刹停｜镜头横移跟随他，最后落幅到沈泊川｜禁止瞬移、换车、提前摘头盔、资料外露
```

If nobody moves:

```text
人物移动表：本节点无人物大位移；所有角色位置锁定，只允许眼神、呼吸、肩颈、手指等微反应。
```

## Camera And Character Separation

Never confuse camera movement with character movement.

```text
镜头运动 = camera path.
人物运动 = character path.
镜头横移、推进、摇移，不代表人物自动移动。
人物位置锁定时，即使镜头跟拍或推近，角色在场景中的世界位置仍不变。
```

Required wording:

```text
镜头运动：从A构图到B构图，速度、方向、焦点、落幅明确。
人物运动：谁移动、从哪里到哪里、经过什么路径、最后停在哪里明确。
镜头与人物运动关系：镜头跟随谁；谁保持世界位置不变；谁只做微反应。
```

## Continuity Anchor

Every video node must state how its endpoint connects to the next node.

```text
continuity anchor：
上一节点终点：
本节点起点：
本节点终点：
下一节点起点：
```

If a character moves offscreen between CUTs, state it explicitly.

```text
画面外动作说明：该角色在CUT间画面外完成起身/转身/移动，下一CUT以新位置登场。
```

## Failure Triggers

If any of these appear, the prompt is unsafe and must be repaired before output:

```text
character positions described only as "in frame", "beside them", "nearby", or "on the side".
movement direction missing.
start/end position missing.
camera movement written but character movement unspecified.
same character jumps from left to right without path.
background characters change order between panels or nodes.
listener who should be locked walks away.
moving subject does not move despite source requiring entry, stop, turn, walk, handoff, or prop action.
supporting actors are frozen without micro acting.
position lock is used as an excuse for dead acting.
```

## Mandatory Repair

When unsafe, repair with one or more of these actions:

```text
Add 人物位置连续表.
Add 人物移动表.
Use screen x% positions.
Lock non-moving characters.
Write start -> path -> end for moving characters.
Separate camera path from character path.
Add micro acting for locked listeners.
Use cutaway or closer shot if all positions cannot be preserved in one frame.
Split the CUT if movement plus dialogue makes the shot unstable.
```

## Output Requirement

Every Jimeng / Seedance video prompt must include:

```text
人物位置连续表：
人物移动表：
镜头与人物运动关系：
continuity anchor：
```

If the user asks for prompt only, long diagnosis may be hidden, but the final prompt must still contain concrete positions, movement paths, and camera-character separation.
