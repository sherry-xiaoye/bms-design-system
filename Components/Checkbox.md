# Checkbox

## 1.1 用途

用于多选、批量选择、表格行选择和部分选中场景。

## 1.2 视觉规范

- 组件：`Checkbox`
- `Normol`: 图标使用 `Icon/Checkbox`, `Icon/Brand`, `Icon/Inverse`，文字：`Body/文本`,`Text/Primary`
- `Selected`: 图标使用 `Icon/Checkbox-Selected`, `Icon/Brand`, `Icon/Inverse`，文字：`Body/文本`,`Text/Primary`
- `Disabled`: 图标使用 `Icon/Checkbox`, `Border/Disabled`, `Background/Disabled Subtle`，文字：`Body/文本`,`Text/Disabled`
- `SelectDisabled`:图标使用 `Icon/Checkbox-Selected`, `Border/Disabled`,`Background/Disabled Subtle`, `Background/Disabled`，文字：`Body/文本`,`Text/Disabled`
- `Selectpart`: 图标使用 `Icon/Checkbox-Selectpart`, `Icon/Brand`, `Icon/Inverse`，文字：`Body/文本`,`Text/Primary`
- 颜色：禁止自定义色值
- 图标：`Size/16*16`

## 1.3 状态规范

- default：`Normol`
- selected：`Selected`
- disabled：`Disabled`
- selected disabled：`SelectDisabled`
- indeterminate：`Selectpart`


## 1.4 交互规则

- 支持多项选择。
- 表格全选场景需支持半选状态。
- 禁用状态不可点击。
- 点击文字或勾选框均可切换状态，具体点击热区待定。

## 1.5 业务场景示例

- 场景 1：【表格业务】中的【行选择 / 批量操作】
- 场景 2：【筛选业务】中的【多条件选择】

## 1.6 前端适配点

- `checked` 映射选中状态
- `indeterminate` 映射 `Selectpart`
- `disabled` 映射禁用状态
- 组件名建议：`Checkbox` / `CheckboxGroup`

## 1.7 AI 生成约束

- 必须使用系统 `Checkbox`。
- 禁止用图标或 div 模拟复选框。
- 必须保留半选状态。
- 禁止新增未在 Figma 出现的状态、尺寸、颜色、圆角、阴影。
