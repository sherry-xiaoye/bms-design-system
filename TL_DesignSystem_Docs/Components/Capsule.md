# Capsule

## 1.1 用途

Capsule 用于轻量级分类切换、状态筛选和局部视图切换。适用于列表页、卡片列表页、数据分组视图等需要在少量互斥选项之间切换的场景。

Capsule 不用于表单下拉选择；表单选择应使用 `SelectAndPickers`。Capsule 不用于纯状态展示；状态展示应使用 `Tag`。

## 1.2 视觉规范

### 组件与结构

- 组件：`Capsule`
- 子项：`Capsule-Item`
- 结构：由多个 `Capsule-Item` 横向组成。
- Figma 当前确认示例：三项组合，第一项选中。
- 中间项支持通过 `Slot` 扩展。

### 尺寸

| 项目 | 规范 | 来源 |
|---|---:|---|
| 组件参考宽度 | `222px` | Figma |
| 组件高度 | `36px` | Figma |
| 单项高度 | `36px` | Figma |
| 单项横向内边距 | `19px` | Figma |
| 单项纵向内边距 | `9px` | Figma |
| 圆角 | `Radius/Card Small` | Token |
| 边框 | `1px` | Figma |

### 颜色 Token

- 选中项背景：`Background/Brand`
- 选中项文字：`Text/Inverse`
- 未选中项背景：`Background/Default`
- 未选中项文字：`Text/Primary`
- 未选中项边框：`Border/Default`
- 禁用态颜色：`待定`
- Hover 态颜色：`待定`

### 字体

| 文本 | 字体样式 | 颜色 |
|---|---|---|
| 选中项文字 | `Body/文本`，12px / 18px，Regular | `Text/Inverse` |
| 未选中项文字 | `Body/文本`，12px / 18px，Regular | `Text/Primary` |

### 圆角规则

- 第一项：左上、左下圆角使用 `Radius/Card Small`。
- 中间项：不设置外侧圆角。
- 最后一项：右上、右下圆角使用 `Radius/Card Small`。
- 单项 Capsule：四角均使用 `Radius/Card Small`，是否允许单项使用需由业务确认。

## 1.3 状态规范

- default 默认状态：
  - 未选中项使用 `Background/Default`、`Border/Default`、`Text/Primary`。

- selected 选中状态：
  - 选中项使用 `Background/Brand`、`Text/Inverse`。
  - 同一组 Capsule 中只能有一个 selected 项。

- hover 悬浮状态：
  - Figma 当前节点未确认，写 `待定`。

- active / focus 激活状态：
  - 键盘聚焦、点击激活样式未确认，写 `待定`。

- blur 失焦状态：
  - 失焦后保留当前 selected 项。
  - 独立 Blur 样式未确认，写 `待定`。

- disabled 禁用状态：
  - Figma 当前节点未确认，写 `待定`。

- error 错误状态：
  - Capsule 不承载错误态；如业务需要错误反馈，应在外层区域展示提示。

- loading 加载状态：
  - Figma 当前节点未确认，写 `待定`。

## 1.4 交互规则

- 点击未选中项后，该项变为 selected，原 selected 项恢复 default。
- Capsule 为单选切换控件，不用于多选。
- 切换 Capsule 后是否立即刷新列表，由页面业务规则决定。
- 在列表页中，Capsule 常作为状态 / 分类筛选条件。
- 在 `CardListPage` 中，Capsule 可单独使用，也可与 `Search`、`Filter-Bar` 组合使用。
- Capsule 选项文案应为短文本，不应放入长句、说明文案或复杂图文内容。
- Capsule 不应承载危险操作、提交操作或页面级主操作。

## 1.5 业务场景示例

- 场景 1：【卡片列表页】中的【状态分类切换】
- 场景 2：【列表页】中的【对象类型筛选】

## 1.6 前端适配点

### Props / Variant 映射

| Props | Figma 映射 | 说明 |
|---|---|---|
| `options` | `Capsule-Item` 列表 | 选项集合 |
| `value` | `selected` 项 | 当前选中值 |
| `defaultValue` | 默认 selected 项 | 初始选中值 |
| `disabled` | disabled 状态 | Figma 未确认样式，使用前需确认 |
| `onChange` | 点击切换 | 切换选项后的回调 |

### 数据回显规则

- 根据 `value` 匹配对应选项，并展示为 selected。
- 如果 `value` 不在 `options` 中，展示规则为 `待定`。
- 如果无默认值，默认选中第一项或不选中需由业务确认。

### 样式类名 / 组件名规范

- 建议代码组件名：`Capsule`
- 子项组件名：`CapsuleItem`
- Figma 原始名称：`Capsule`、`Capsule-Item`

## 1.7 AI 生成约束

- 必须使用 Figma 中确认的 `Capsule` 与 `Capsule-Item` 结构。
- 必须使用系统 Token，不得自定义颜色、圆角、边框和字号。
- 禁止用 `Button`、`Tag`、`Radio` 或普通 `div/span` 模拟 Capsule。
- 禁止新增 Figma 未确认的尺寸、状态、圆角、阴影和交互。
- 未确认的 hover、focus、disabled、loading 样式必须写为 `待定`。
