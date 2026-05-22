# Guidelines

本文件定义全局设计与生成规则，适用于页面模板、组件使用、视觉约束和 AI 生成自检。

## 1. 设计原则

管理端或业务系统的核心任务通常是查询、录入、配置、审批和监控。界面应服务于业务效率，不做营销化、装饰化表达。

### 1.1 信息优先

- 页面结构必须服务于业务信息，不以视觉装饰为主。
- 表格、表单、筛选、详情、弹窗和图表是核心界面模式。
- 重要信息优先展示，次要信息弱化处理。
- 数据列表、详情字段、表单项必须保持可扫描、可比较、可回溯。

### 1.2 操作清晰

- 每个页面只保留必要主操作。
- 主操作使用 `Button` 的 Primary 类型。
- 次要操作使用 `Button` 的 Default 类型。
- 表格行内操作优先使用 Text Button。
- 删除、停用、作废、提交审批等高危操作必须二次确认。
- 异步操作必须包含 loading、success、error 反馈。

### 1.3 视觉克制

- 页面背景优先使用 `Background/Disabled Subtle` 或页面模板中已确认背景 Token。
- 内容容器背景使用 `Background/Default`。
- 表格表头背景使用 `Background/TableHeader`。
- 表格线使用 `Border/Table`。
- 主文本使用 `Text/Primary`，次级说明使用 `Text/Secondary`。
- 图标颜色必须使用 `Icon/*` Token。
- 禁止大面积渐变、装饰插画、光斑、背景图和强阴影。
- 禁止将管理端页面设计成官网、营销页、活动页或数据大屏风格，除非 Figma 或具体产品需求已确认。

## 2. 页面结构规则

管理端页面默认先遵循以下壳结构：

```text
AppHeader
Sidebar-Left
Body
```

Body 内部必须匹配 `Patterns/` 中对应页面模板：

- `TablePage.md`
- `FormPage.md`
- `DetailPage.md`
- `DashboardPage.md`

不得随意调整页面模板结构。页面模板中未确认的尺寸、间距、圆角、阴影必须写 `待定`。

## 3. 组件使用规则

- 优先使用 `Components/` 中已定义的系统组件。
- 禁止重复创建 Button、Input、Select、Table、Dialog、Pagination、Feedback 等基础组件。
- 禁止用 `div` / `span` 模拟按钮、输入框、选择器、表格、弹窗等基础组件。
- 下拉选择、级联选择、日期选择、时间选择、日期时间选择统一使用 `SelectAndPickers.md` 中的组件规范。
- 加载中统一使用 `Feedback.md` 中的 `Loading` 规范。
- 空数据、无搜索结果、无权限或异常页面优先使用 `Default.md` 或 `Feedback.md` 中的 `Default-Image / Empty` 规范。
- 组件状态必须使用 Figma 已确认状态；未确认状态写 `待定`，不得自行新增。

## 4. Token 使用规则

- 颜色必须优先使用 Semantic Token，其次 Primitive Token。
- 间距必须使用 `Spacing/*` Token。
- 圆角必须优先使用 Semantic Radius Token，其次 Primitive Radius Token。
- 表单控件圆角使用 `Radius/Form`。
- 卡片圆角使用 `Radius/Card Small` 或 `Radius/Card Larger`。
- 小型控件或紧凑元素使用 `Radius/Smallest`。
- 图标和固定宽高元素优先使用 Semantic Size Token。
- 字体、字号、字重、行高必须以 Figma Text Styles 或 `Typography.md` 为准。
- 阴影必须使用 Figma 已确认 Effect Style；未确认写 `待定`。
- 禁止自定义色值、伪造 Token、修改 Token 名称。
- 禁止硬编码未经 Figma 或 Token 确认的尺寸、圆角、间距、阴影。

## 5. 状态完整性

列表、表格、详情、图表、表单提交必须考虑：

- loading
- empty
- error
- disabled
- permission denied（如业务存在权限）

所有异步提交必须考虑：

- loading
- success feedback
- error feedback
- 防重复提交

表单类页面必须考虑：

- required 必填
- validation error 校验错误
- disabled 禁用
- readonly 只读
- submit loading 提交中

## 6. 交互规则

- 查询条件变更后的触发方式以页面模板或业务规则为准；未确认写 `待定`。
- 表格分页、排序、筛选必须保持状态可回显。
- 超长文本优先使用截断和 Tooltip，具体截断规则未确认时写 `待定`。
- 高危操作必须通过 Dialog 或 Popover Confirm 二次确认，具体组件以 Figma 已确认规范为准。
- 表单提交失败必须展示明确错误反馈，字段错误优先内联展示。
- 页面跳转、返回、保存后停留或跳转规则未确认时写 `待定`。

## 7. 禁止事项

- 禁止新增未在 Figma 出现的组件、状态、尺寸、颜色、圆角和阴影。
- 禁止使用 Figma Token 之外的颜色值。
- 禁止为单个页面临时新增 spacing / radius / size Token。
- 禁止页面区块层层套卡片。
- 禁止用大标题、Hero、装饰背景制造营销页效果。
- 禁止把表格行内操作做成大按钮堆叠。
- 禁止忽略 empty / loading / error 状态。
- 禁止把未确认内容写成确定规则。

## 8. AI 生成约束

- 生成页面前必须先读取 `README.md`、对应 `Patterns/*.md`、相关 `Components/*.md`、`Foundations/*.md`。
- 页面必须优先匹配 `Patterns/` 中的页面模板。
- 组件必须优先使用系统组件和 Figma 已确认变体。
- 所有颜色、字号、行高、圆角、间距、阴影必须来自 Figma 或 Token。
- 无法确认的值必须写 `待定`。
- 禁止编造 Token 名称、组件名、状态名和交互规则。
- 生成结果必须依据 `Guidelines/AI_Output_Checklist.md` 自检。
