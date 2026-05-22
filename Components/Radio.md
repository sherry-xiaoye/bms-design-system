# Radio

## 1.1 用途

用于少量互斥选项选择。适合选项数量小于等于6个、需要直接展示全部选项的业务场景。

## 1.2 视觉规范

- 组件：`Radio`
- `Normol`: 图标使用 `Icon/Radio`, `Icon/Secondary`, `Icon/Inverse`，文字：`Body/文本`,`Text/Primary`
- `Selected`: 图标使用 `Icon/RadioSelect`, `Icon/Brand`, `Icon/Inverse`，文字：`Body/文本`,`Text/Primary``
- `Disabled`: 图标使用 `Icon/Radio`, `Border/Disabled`, `Background/Disabled Subtle`，文字：`Body/文本`,`Text/Disabled`
- `SelectDisabled`:图标使用 `Icon/RadioSelect`, `Icon/Disabled`,`Icon/Inverse`, `Background/Disabled`，文字：`Body/文本`,`Text/Disabled`
- 颜色：禁止自定义色值

## 1.3 状态规范

- default：`Default`
- disabled：`Disabled`
- selected：`Selected`
- selected disabled：`SelectedDisabled`


## 1.4 交互规则

- 同一组内只能选择一个选项。
- 点击选项或文字区域后切换选中项。
- 禁用状态不可点击。

## 1.5 业务场景示例

- 场景 1：【筛选业务】中的【状态单选】
- 场景 2：【表单业务】中的【类型选择】

## 1.6 前端适配点

- `value` 映射当前选中值
- `options` 映射选项列表
- `disabled` 映射禁用状态
- 组件名建议：`Radio` / `RadioGroup`

## 1.7 AI 生成约束

- 必须使用系统 `Radio`。
- 禁止用按钮或标签模拟单选。
- 禁止新增未在 Figma 出现的状态、尺寸、颜色、圆角、阴影。
