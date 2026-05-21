# Layout

本文件定义管理端或业务系统页面的全局布局规则。页面级结构以 `Patterns/` 中的页面模板为准，本文件只约束通用布局壳、内容区组织方式和禁止事项。

## 1. 标准页面布局

管理端页面默认使用以下布局壳：

```text
AppHeader
Sidebar-Left
Body
```

已确认尺寸：

| 区域 | 尺寸 / 位置 | 说明 |
|---|---:|---|
| `AppHeader` | `56px` | 顶部导航高度 |
| `Sidebar-Left` | `180px` | 左侧导航宽度 |
| `Body` | `x=180`, `y=56` | 主内容区域起点 |
| `Body padding` | `20px` | 主内容区内边距 |
| `Body background` | `Background/Default` | 主内容区背景色 |

Body 区域遵循 `Foundations/Grid.md` 中的 8 栅格与 Breakpoint 规则。
`AppHeader` 的内部结构、尺寸和交互规则见 `Components/AppHeader.md`。

## 2. 页面内容结构

Body 内部必须根据页面类型匹配对应 Pattern：

- `TablePage.md`
- `FormPage.md`
- `DetailPage.md`
- `DashboardPage.md`

通用内容组织规则：

- 页面标题使用 `Title`。
- 查询和筛选区域使用 `Filter-Bar` 或页面模板中确认的筛选结构。
- 表单区域使用 `Form Container`。
- 表格区域使用 `TableHeaderActions`、`Table`、`Pagination`。
- 详情区域使用 `Summary`、`Detail Sections`、`Related Table`、`Timeline / Operation Log`。
- 图表区域使用 `Metric Cards`、`Chart Grid`、`Detail Table / Rank List`。
- 不得在页面中临时新增 Pattern 未确认的一级结构。

## 3. 视觉布局规则

- 页面外层背景优先使用 `Background/Disabled Subtle`。
- `Body` 主内容区背景必须使用 `Background/Default`。
- 内容容器背景使用 `Background/Default`。
- 左侧导航背景使用 `Background/Sidebar`。
- 顶部导航背景使用 `Background/Top Navigation`。
- 表格表头背景使用 `Background/TableHeader`。
- 表格线使用 `Border/Table`。
- 间距必须使用 `Spacing/*` Token，未确认写 `待定`。
- 圆角必须使用 `Radius/*` Token，未确认写 `待定`。
- 阴影必须使用 Figma 已确认 Effect Style，未确认写 `待定`。
- 字体必须使用 Figma Text Styles 或 `Typography.md` 中已确认样式。

## 4. 内容区布局规则

- 页面主操作应靠近页面标题或工具栏，不得散落在多个无关区域。
- 表格页的查询、工具栏、表格、分页顺序不得随意调整。
- 表单页的底部操作区必须保持稳定位置，主提交按钮只能有一个。
- 详情页首屏必须展示业务对象身份、关键状态和主要操作。
- Dashboard 页不得使用数据大屏式全屏装饰布局，除非 Figma 或具体产品需求已确认。
- 复杂编辑流程使用 FormPage，不放入大弹窗。
- 关联数据使用 Table，不使用自定义列表替代表格。
- 禁止卡片嵌套卡片。

## 5. 响应与溢出规则

- Body 内容超出可视区域时允许页面纵向滚动。
- 表格横向字段过多时优先使用表格自身横向滚动和固定列能力。
- 超长文本优先使用截断和 Tooltip，具体截断规则未确认写 `待定`。
- 内容区宽度与响应式适配遵循 `Foundations/Grid.md` 中的 8 栅格与 Breakpoint 规则。
- 移动端布局规则未在 Figma 中确认，统一写 `待定`。

## 6. 禁止事项

- 禁止使用旧结构名替代布局壳，例如 `App / SideMenu / Main`。
- 禁止使用未确认的 CSS 变量名替代 Token。
- 禁止把管理端页面设计成营销页 Hero 布局。
- 禁止使用大面积渐变、背景图、装饰插画、光斑和强阴影。
- 禁止页面区块层层套卡片。
- 禁止临时新增未在 Figma 或 Pattern 中确认的布局模块。
- 禁止硬编码未经 Figma 或 Token 确认的尺寸、间距、圆角、阴影。

## 7. 待确认

- 移动端布局规则：`待定`。
- 页面级固定底部操作栏规则：`待定`。
- 滚动吸顶、固定列、固定操作栏的具体触发条件：`待定`。
