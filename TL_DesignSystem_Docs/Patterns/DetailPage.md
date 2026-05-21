# DetailPage

## 1.1 用途

用于展示单个业务对象的完整信息、状态、关联数据和操作记录。

适合订单详情、设备详情、用户详情、任务详情、审批详情等页面。

## 1.2 页面结构

```text
BMS-Header
Sidebar-Left
Body
  Title / Status / Actions
  Summary
  Detail Sections
  Related Table
  Timeline / Operation Log
```

## 1.3 视觉规范

- 页面壳：
  - Header：`56px`
  - Sidebar：`180px`
  - Body：`x=180`, `y=56`
  - Body padding：`20px`
  - Body 背景颜色遵循 `Guidelines/Layout.md`，必须使用 `Background/Default`
- 颜色：
  - 内容背景优先使用 `Background/Default`
  - 主文本使用 `Text/Primary`
  - 次级文本使用 `Text/Secondary`
  - 状态颜色使用 `Tag` 或对应 Semantic Token
- 字体：
  - 页面标题：`Heading/主页面和弹窗的标题`
  - 区块标题：`Heading/页面内容的标题`
  - 字段内容：`Body/文本`
- 间距：使用 `Spacing/*` Token，未确认写 `待定`
- 圆角：使用 `Radius/*` Token，未确认写 `待定`
- 阴影：使用 Figma 已确认 Effect Style；未确认写 `待定`

## 1.4 组件使用

- 页面标题：`Title`
- 状态展示：`Tag`
- 信息分组：`Card`
- 关联数据：`Table`
- 操作记录：`Timeline`
- 操作按钮：`Button`, `Button-Danger`, `TextButton`, `Link`
- 确认操作：`Dialog`
- 反馈：`Toast`, `Notification`, `Alert`

## 1.5 状态规范

- loading：详情数据、关联表格、操作记录加载时必须覆盖。
- empty：关联数据为空、操作记录为空时必须展示。
- error：详情接口失败时展示错误反馈和重试入口。
- disabled：无权限或不可操作字段使用禁用状态。
- hover：按钮、表格行、可点击卡片按组件状态展示。
- selected：关联表格如支持选择，遵循 Table 选择规则。

## 1.6 交互规则

- 首屏必须展示业务对象身份、关键状态和主要操作。
- 危险操作必须使用 `Button-Danger` 并二次确认。
- 复杂编辑跳转表单页。
- 短字段编辑可使用 Dialog，是否适用以业务为准。
- 关联记录使用 Table，不使用自定义列表替代表格。
- 操作日志按时间倒序或业务确认顺序展示，排序规则待定。
- 禁止卡片嵌套卡片。

## 1.7 AI 生成约束

- 必须使用 BMS 后台页面结构。
- 禁止把详情页做成营销介绍页。
- 禁止卡片嵌套卡片。
- 必须包含 loading / empty / error 状态。
- 危险操作必须使用系统危险按钮和确认弹窗。
- 禁止新增未在 Figma 或 Token 中确认的颜色、圆角、阴影、状态。
- 未确认的尺寸、间距、圆角、阴影必须写 `待定`。
