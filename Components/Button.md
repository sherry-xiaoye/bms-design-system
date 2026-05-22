# Button

## 使用场景

用于页面主操作、次操作、行内操作和危险操作。

## 允许变体

- 以 Figma 中已确认的组件属性和 Variant 为准。

## 尺寸与视觉

- 组件：`Button`, `TextButton`, `Link`, `Button-Danger`, `Button-Group`
- 变体：`Size`, `Style`, `State`
- Size：`Large`, `Middle`, `Small`
- Style：`Primary`, `Secondary`, `General`
- State：`Default`, `Hover`, `Active`, `Disabled`
- 颜色：优先使用 `Background/Brand`, `Text/Inverse`, `Border/Default`, `Text/brand`
- 高度：Large `36`，Middle `30`，Small `24`
- 圆角：`8`
- 左右内边距：`16`

## 状态

- default：默认可点击状态。
- hover：使用 Figma hover 变体。
- active：使用 Figma active 变体。
- disabled：不可点击，使用禁用文本和边框 Token。
- error：仅 `Button-Danger` 表达危险语义。

## 交互规则

- 同一区域只允许一个 Primary。
- 删除、作废、停用等危险动作使用 `Button-Danger`。
- 表格行内操作优先使用 `TextButton` 或 `Link`。

### Button-Group 组合规则

`Button-Group` 用于多个按钮在同一区域内成组出现，适用于弹窗底部、固定底部操作区、结果页面、Filter Bar、卡片操作区等场景。

| Alignment | Count | 按钮顺序 | 使用说明 |
|---|---:|---|---|
| `Left` | `Two` | `Primary + General` | 左侧主操作优先展示 |
| `Left` | `Three` | `Primary + General + General` | 左侧主操作 + 两个次级操作 |
| `Left` | `Four` | `Primary + General + General + General` | 左侧多操作场景，需控制使用频率 |
| `Right` | `Two` | `General + Primary` | 右侧确认类操作，主操作靠右 |
| `Right` | `Three` | `General + General + Primary` | 右侧三按钮操作组，主操作固定在最右侧 |


业务场景示例：

- 场景 1：【列表页】中的【查询 / 新增 / 导出】。
- 场景 2：【弹窗】中的【取消 / 确认】。

## 前端适配

- `size` 映射 `Large | Middle | Small`
- `style` 映射 `Primary | Secondary | General`
- `state` 映射 `Default | Hover | Active | Disabled`
- 危险按钮必须独立映射到 `Button-Danger`

## 禁止事项

- 禁止使用 Figma 未确认的组件、状态、尺寸、颜色、圆角和阴影。
- 禁止自定义 Token 或硬编码未经确认的样式。

## AI 生成约束

- 必须使用 Figma 中已有 Button 变体。
- 禁止自定义颜色、圆角、尺寸。
- 禁止使用阴影。
- 禁止新增未确认的 loading / error 按钮样式。
