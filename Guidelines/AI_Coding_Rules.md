# AI Coding Rules

本文件是给 Cursor、Claude Code、Windsurf 等 AI coding 工具读取的总入口规则。

## 1. 总原则

你在实现管理端或业务系统页面时，必须遵守以下规则：

- 优先使用项目已有组件，禁止重复创建 Button、Input、Select、Table、Dialog、Pagination、Feedback 中的 Loading 等基础组件。
- 所有颜色必须来自已确认 Token。
- 所有间距、字体、圆角、行高如果未在 Token 中确认，必须标注为“待定”或复用项目已有变量，不得伪造 Token。
- 禁止硬编码非 Token 色值，例如 `#1677ff`、`red`、`blue`、`rgba(...)`。
- 禁止创建营销风、官网风、活动页风、数据大屏风页面。
- 页面必须优先匹配 `Patterns` 中的页面生成契约。
- 生成代码后必须依据 `Guidelines/AI_Output_Checklist.md` 自检。

## 2. 标准页面结构

管理端页面默认先遵循以下壳结构：

```text
AppHeader
Sidebar-Left
Body
```

Body 内部必须继续匹配 `Patterns/` 中对应页面模板：

- `TablePage.md`
- `FormPage.md`
- `DetailPage.md`
- `DashboardPage.md`

不得随意调整页面模板结构。

## 3. 组件使用规则

- 按钮必须使用系统 Button。
- 输入框必须使用系统 Input。
- 下拉选择必须使用系统 Select。
- 日期、时间、日期时间选择必须使用 `SelectAndPickers.md` 中的 DatePicker / TimePicker / DateTimePicker。
- 表格必须使用系统 Table。
- 弹窗必须使用系统 Dialog。
- 分页必须使用系统 Pagination。
- 加载中必须使用 `Feedback.md` 中的 Loading 规范。
- 空数据必须按页面模板 empty 状态处理，并优先使用 `Default.md`。

## 4. 状态兜底规则

所有列表、表格、详情、图表模块必须考虑：

- loading 状态；
- empty 状态；
- error 状态；
- disabled 状态；
- permission denied 状态，如业务存在权限控制。

所有异步提交必须考虑：

- loading；
- success feedback；
- error feedback；
- 防重复提交。

## 5. 禁止生成的 UI 风格

- 禁止使用大面积渐变背景。
- 禁止使用营销页 Hero 布局。
- 禁止使用装饰性插画、光斑、背景图。
- 禁止使用未在 Token 中确认的圆角；卡片圆角必须使用 `Radius/Card Small` 或 `Radius/Card Larger`。
- 禁止使用大面积阴影制造悬浮卡片感。
- 禁止页面区块层层套卡片。
- 禁止使用过大的标题字号。
- 禁止将管理端页面做成官网、运营活动页或数据大屏风格。
- 禁止随意新增组件状态。
- 禁止忽略 empty / loading / error 状态。
- 禁止把表格行内操作做成大按钮堆叠。

## 6. 输出后自检

生成代码后必须检查：

- 是否存在硬编码颜色；
- 是否存在伪造 Token；
- 是否遗漏 loading / empty / error 状态；
- 是否违反页面模板结构；
- 是否重复创建已有系统组件；
- 是否使用 div / span 模拟按钮、输入框、选择器；
- 是否符合管理端或业务系统克制、高效、可扫描的视觉要求。
