# FormPage

## 1.1 用途

用于新建、编辑、配置、审批填写等需要用户提交结构化信息的页面。

适合基础信息维护、业务单据创建、复杂配置、多步骤流程等场景。

## 1.2 页面结构

```text
BMS-Header
Sidebar-Left
Body
  Title
  Optional Step
  Form Container
    Form Items
    Upload / Select / Input / Date Controls
  Footer Button-Group
```

## 1.3 视觉规范

- 页面壳：
  - Header：`56px`
  - Sidebar：`180px`
  - Body：`x=180`, `y=56`
  - Body padding：`20px`
  - Body 背景颜色遵循 `Guidelines/Layout.md`，必须使用 `Background/Default`
- 颜色：
  - 表单容器背景优先使用 `Background/Default`
  - 表单文本使用 `Text/Primary`
  - 辅助说明使用 `Text/Secondary`
  - 错误信息使用 `Text/Error`
- 字体：
  - 页面标题：`Heading/主页面和弹窗的标题`
  - 表单区块标题：`Heading/页面内容的标题`
  - 表单标签 / 内容：`Body/文本`
- 表单字段宽度：以 Figma / Token 为准，未确认写 `待定`
- 标签宽度：以 Figma / Token 为准，未确认写 `待定`
- 间距：使用 `Spacing/*` Token，未确认写 `待定`
- 圆角：使用 `Radius/*` Token，未确认写 `待定`
- 阴影：使用 Figma 已确认 Effect Style；未确认写 `待定`

## 1.4 组件使用

- 页面标题：`Title`
- 多步骤：`Step-Item`
- 文本输入：`Input`
- 模糊搜索：`Input` + `Input-Dropdown-Single`
- 选择器：`Select.md` 中的 `Select`, `Cascader`
- 日期时间：`Select.md` 中的 `DatePicker`, `TimePicker`, `DateTimePicker`
- 数值：`Stepper`
- 开关：`Switch`
- 上传：`Upload`
- 底部操作：`Button`, `Button-Group`
- 反馈：`Alert`, `Toast`, `Notification`

## 1.5 状态规范

- default：默认填写状态。
- hover：控件按组件 hover 状态展示。
- active / focus：输入和选择控件按 active / focus 状态展示。
- blur：输入和选择控件按 Figma 对应失焦状态展示。
- disabled：不可编辑字段必须使用组件禁用状态。
- error：校验失败时必须以内联错误提示展示。
- loading：提交中按钮进入 loading，页面必要时展示 loading。
- success：提交成功后展示成功反馈或跳转，规则待定。

## 1.6 交互规则

- 必填字段必须展示必填标识。
- 禁止只用 placeholder 作为字段标签。
- 表单提交前必须校验必填、格式、范围和业务规则。
- 复杂表单使用页面承载，不放入 Dialog。
- 底部操作区通常包含取消和主提交按钮。
- 主提交按钮只能有一个。
- 上传失败、接口失败、校验失败必须有明确反馈。
- 多步骤表单必须展示当前步骤、已完成步骤和未完成步骤。

## 1.7 AI 生成约束

- 必须使用系统表单组件，不得用 div 模拟输入、选择、上传。
- 必须包含 default / hover / active / blur / disabled / error / loading 中适用状态。
- 禁止自定义表单控件样式。
- 禁止新增未在 Figma 或 Token 中确认的颜色、圆角、阴影、状态。
- 未确认的字段宽度、间距、圆角、阴影必须写 `待定`。
