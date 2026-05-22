# DashboardPage

## 1.1 用途

用于展示关键指标、趋势图表、分布数据、排行榜和辅助明细信息。

适合经营分析、设备监控、订单统计、任务概览等需要快速查看整体状态的页面。

## 1.2 页面结构

```text
BMS-Header
Sidebar-Left
Body
  Optional Filter-Bar
  Metric Cards
  Chart Grid
  Detail Table / Rank List
```

## 1.3 视觉规范

- 页面壳：
  - Header：`56px`
  - Sidebar：`180px`
  - Body：`x=180`, `y=56`
  - Body padding：`20px`
  - Body 背景颜色遵循 `Guidelines/Layout.md`，必须使用 `Background/Default`
- 颜色：
  - 内容容器背景优先使用 `Background/Default`
  - 图表颜色使用 `Charts/*`
  - 文本颜色使用 `Text/*`
- 字体：
  - 大指标：`Chart/大字号`
  - 图表主指标：`Chart/主要文本`
  - 区块标题：`Heading/页面内容的标题`
  - 辅助说明：`Body/次文本`
- 间距：使用 `Spacing/*` Token，未确认写 `待定`
- 圆角：使用 `Radius/*` Token，未确认写 `待定`
- 阴影：使用 Figma 已确认 Effect Style；未确认写 `待定`

## 1.4 组件使用

- 指标卡片：`Card`
- 标题：`Title`
- 筛选项：`Input`；`Select.md` 中的 `Select`, `DatePicker`, `DateTimePicker`
- 图表：使用 Figma 中确认的图表样式和 `Charts/*` Token
- 明细表格：`Table`
- 状态标签：`Tag`
- 加载：`Feedback` 中的 `Loading`
- 空状态：`Default`

## 1.5 状态规范

- loading：页面首次加载、图表加载、指标加载必须覆盖。
- empty：无指标、无图表数据、无明细数据时必须展示。
- error：接口失败时展示错误反馈和重试入口。
- disabled：筛选条件不可用时使用禁用状态。
- selected：图表选中、筛选选中样式待定。
- hover：卡片或图表 hover 样式以 Figma 为准，未确认写 `待定`。

## 1.6 交互规则

- 筛选条件变化后刷新指标和图表。
- 图表 tooltip 使用系统样式，禁止自定义浮层。
- 指标卡片如可点击，必须有明确 hover / active 样式；未确认则不做点击。
- 图表必须包含清晰的标题、单位、图例或说明。
- 不得生成装饰型数据大屏。
- 不得使用营销式视觉、背景图、大面积渐变或装饰性光效。

## 1.7 AI 生成约束

- 必须使用 BMS 后台页面结构。
- 禁止使用大面积渐变、背景图、装饰图形。
- 禁止自定义图表颜色，必须使用 `Charts/*` Token。
- 必须包含 loading / empty / error 状态。
- 禁止新增未在 Figma 或 Token 中确认的颜色、圆角、阴影、状态。
- 未确认的尺寸、间距、圆角、阴影必须写 `待定`。
