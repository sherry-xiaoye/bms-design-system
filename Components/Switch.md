# Switch

## 1.1 用途

用于即时开关类设置，表达开启 / 关闭的二元状态。

## 1.2 视觉规范

- 组件：`Switch`
- Style：
  - `Large`：`48px x 24px`
  - `Small`：`40px x 20px`
- State：`Default`, `Disabled`
- Show：`On`, `Off`
- 颜色：`Icon/Success`,`Icon/Select-Disabled`,`Icon/Inverse`,`Icon/Thirdly`，禁止自定义色值

## 1.3 状态规范

- default：`State=Default`
- disabled：`State=Disabled`
- on：`Show=On`
- off：`Show=Off`

## 1.4 交互规则

- 点击后在 On / Off 之间切换。
- 用于即时生效配置时，应有成功或失败反馈，反馈样式为图标颜色变化。
- 禁用状态不可点击。

## 1.5 业务场景示例

- 场景 1：【配置业务】中的【启用 / 停用】
- 场景 2：【权限业务】中的【功能开关】

## 1.6 前端适配点

- `checked` 映射 `Show=On | Off`
- `size` 映射 `Large | Small`
- `disabled` 映射 `State=Disabled`
- 组件名建议：`Switch`

## 1.7 AI 生成约束

- 必须使用系统 `Switch`。
- 禁止用 Checkbox 或按钮模拟开关。
- 禁止新增未在 Figma 出现的尺寸、颜色、状态、圆角、阴影。
