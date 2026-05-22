# Dialog

## 1.1 用途

用于确认、短表单、提示、危险操作二次确认等需要阻断当前流程的场景。

## 1.2 视觉规范

- 组件：`Dialog`
- Style：`Primary`, `Lightweight`
- 结构：Header / Body / Footer
- 标题：`Heading/主页面和弹窗的标题`
- 内容：`Body/弹窗内容`
- 背景：`Background/Default`
- 遮罩：`Background/Mask`
- 圆角：`Radius/Card Large`

## 1.3 状态规范

- default：正常打开。
- hover：内部按钮遵循 Button hover。
- active / focus：焦点限制在弹窗内部。
- disabled：提交中可禁用操作按钮。
- error：表单或提交错误以内联提示展示。

## 1.4 交互规则

- 关闭图标使用 Figma `Icon/Close`。
- 点击关闭图标，Dialog消失。
- Footer 通常包含取消和确认。
- 危险确认使用 `Button-Danger`。
- 键盘焦点应被限制在 Dialog 内。

## 1.5 业务场景示例

- 场景 1：【列表页】中的【删除确认】。
- 场景 2：【详情页】中的【短字段编辑】。

## 1.6 前端适配点

- `open` 控制显示。
- `title` 映射 Header。
- `footer` 映射 Button-Group。
- `onConfirm`, `onCancel`, `onClose` 映射交互事件。

## 1.7 AI 生成约束

- 必须使用系统 Dialog。
- 禁止自定义遮罩、阴影、圆角。
- 禁止把多步骤表单塞进弹窗。
