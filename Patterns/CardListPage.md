# CardListPage

## 1.1 用途

CardListPage 用于以卡片形式展示列表数据，适合对象列表、项目列表、课程列表、任务列表、配置项列表等需要展示标题、描述、状态标签和卡片级操作的页面。

当信息需要严格按列对齐、支持复杂排序、批量操作、横向滚动或财务/明细类数据时，应优先使用 `TablePage`，不应强行使用卡片列表。

## 1.2 页面结构

页面采用后台系统通用布局结构：

- `AppHeader`：页面顶部导航区域。
- `Sidebar-Left`：左侧导航区域。
- `Body`：主内容区域，采用自上而下的单列布局。
- `Optional Query Area`：可选查询 / 筛选区域，根据业务情况使用。
- `CardList`：卡片列表区域。
- `Optional Pagination`：分页区域，根据业务情况使用。

Body 区域结构：

```text
Body
├── Optional Query Area
│   ├── Filter-Bar
│   ├── Search
│   ├── Capsule
│   └── Search + Capsule / Search + Filter-Bar / Capsule + Filter-Bar
├── CardList
│   ├── Card Item
│   ├── Card Item
│   ├── Card Item
│   └── Card Item
└── Optional Pagination
```

查询 / 筛选区域不是必填模块，不应默认强制出现。

- 仅关键词检索：使用 `Search`，规范见 `Components/Search.md`。
- 仅状态 / 分类切换：使用 `Capsule`，规范见 `Components/Capsule.md`。
- 多字段结构化筛选：使用 `Filter-Bar`。
- 关键词 + 状态分类：使用 `Search + Capsule`。
- 关键词 + 多条件筛选：使用 `Search + Filter-Bar`。
- 状态分类 + 多条件筛选：使用 `Capsule + Filter-Bar`。

如果页面无查询、筛选或分类需求，CardList 应直接从 Body 顶部开始排列，不保留空筛选区域。

## 1.3 视觉规范

### 页面容器

- `AppHeader`：高度为 `56px`。
- `Sidebar-Left`：宽度为 `180px`。
- `Body`：位于 `AppHeader` 下方、`Sidebar-Left` 右侧。
- `Body` 内边距：`20px`。
- `Body` 背景颜色遵循 `Guidelines/Layout.md`，必须使用 `Background/Default`。
- `Body` 内部纵向间距：`Spacing/5`。
- `Body` 区域遵循 `Foundations/Grid.md` 中的 8 栅格与 Breakpoint 规则。
- 主内容宽度随 Body 自动填充，不设置固定最大宽度。

### Optional Query Area

Figma 当前节点中展示的是 `Filter-Bar`，同时存在隐藏态的 `Search` 与 `Capsule` 方案。

- `Filter-Bar`
  - 参考宽度：随 Body 内容区自动填充。
  - Figma 参考高度：`112px`。
  - 底部分割线：`Border/Disabled`。
  - 底部内边距：`Spacing/5`。
  - 控件宽度：`240px`。
  - 控件高度：`36px`。
  - Label 宽度：`60px`。
  - Label 与控件间距：`Spacing/2`。
  - 筛选项横向 / 纵向间距：`Spacing/5`。
  - 操作按钮位于筛选区右侧。

- `Search`
  - Figma 参考宽度：`320px`。
  - Figma 参考高度：`36px`。
  - 具体状态与视觉规范遵循 `Components/Search.md`。

- `Capsule`
  - Figma 参考宽度：`222px`。
  - Figma 参考高度：`36px`。
  - 具体状态与视觉规范遵循 `Components/Capsule.md`。

### CardList

- 列表方向：单列纵向排列。
- 卡片之间间距：`Spacing/5`。
- 卡片宽度：随 Body 内容区自动填充。
- Figma 参考卡片高度：`162px`。
- 卡片背景：`Background/Default`。
- 默认边框：`Border/Default`。
- Hover / 强调边框：`Border/Hover`。
- 圆角：`Radius/Card Larger`。
- 卡片内边距：`Spacing/4`。
- 卡片内部纵向间距：`Spacing/3`。

### Card Item 内容

- 标题区
  - 标题文本：`Heading/主页面和弹窗的标题`。
  - 字号 / 行高：`16/24`。
  - 字重：`Semibold`。
  - 文本颜色：`Text/Primary`。
  - 操作按钮位于标题区右侧。
  - Figma 当前展示 3 个按钮，其中主按钮不超过 1 个。

- 描述区
  - 文本样式：`Body/文本`。
  - 字号 / 行高：`12/18`。
  - 文本颜色：`Text/Primary`。
  - 长文本截断、换行规则：`待定`。

- 重要信息区
  - 标题文字：`重要信息`。
  - 字号 / 行高：`12/18`。
  - 字重：`Semibold`。
  - 文本颜色：`Text/Primary`。
  - 标签使用 `Tag` 组件。
  - Figma 中出现的 Tag 类型包括：Gray、Blue、Green、Orange、Red。

- 辅助信息区
  - 文本样式：`Body/文本`。
  - 字号 / 行高：`12/18`。
  - 文本颜色：`Text/Secondary`。

## 1.4 组件使用

CardListPage 可使用以下组件：

- `AppHeader`
- `Sidebar-Left`
- `Filter-Bar`
- `Search`
- `Capsule`
- `Card`
- `Button`
- `Tag`
- `Pagination`
- `Feedback`
- `Default-Image`

组件使用规则：

- 查询 / 筛选区域根据业务选择，不得强制出现。
- `Search` 用于关键词检索。
- `Capsule` 用于状态、分类、轻量级视图切换。
- `Filter-Bar` 用于多字段结构化筛选。
- `Card` 用于承载单条列表数据。
- `Button` 用于卡片级操作。
- `Tag` 用于状态、类型、风险、分类等信息标记。
- 空数据、加载失败、无权限等场景使用 `Feedback` 或 `Default-Image`。

## 1.5 状态规范

- default 默认状态：页面正常加载 CardList 数据，卡片按单列顺序展示。
- hover 悬浮状态：卡片存在可点击或可操作行为时，可使用 `Border/Hover`；如果卡片本身不可点击，不应添加整卡点击暗示。
- active / focus 激活状态：`Search`、`Capsule`、`Input`、`Select`、`DatePicker`、`Button` 等组件遵循各自组件状态。
- blur 失焦状态：输入类组件失焦后恢复为 Blur 状态；不再使用 `Unfocus` 或 `Unfocused` 命名。
- disabled 禁用状态：无权限或当前数据状态不可操作时，对应按钮进入 disabled。
- error 错误状态：查询失败、加载失败时展示错误反馈，可提供重试操作。
- loading 加载状态：首次进入页面、查询、切换 Capsule、分页或刷新列表时进入 loading。
- empty 空状态：查询无结果或当前无数据时展示空状态。

## 1.6 交互规则

### 查询 / 筛选交互

- Query Area 为可选区域，不存在筛选需求时不展示。
- 使用 `Search` 时，适用于关键词快速检索。
- 使用 `Capsule` 时，适用于状态、分类或轻量级视图切换。
- 使用 `Filter-Bar` 时，适用于多条件组合筛选。
- 修改 `Filter-Bar` 条件不自动刷新列表，用户点击「查询」后统一触发。
- 点击「重置」后恢复默认筛选值，并刷新列表。
- 当 `Search` 与 `Filter-Bar` 组合使用时，Search 作为查询条件之一。
- 当 `Capsule` 与 `Filter-Bar` 组合使用时，Capsule 作为分类或状态条件之一。
- 当 `Search` 与 `Capsule` 组合使用时，Search 负责关键词检索，Capsule 负责分类 / 状态切换。
- 重置操作影响范围需由业务确认；未确认时，仅重置当前 Filter-Bar 内部条件。
- 日期区间、状态、枚举类条件支持在组件内清空。
- 查询过程中，查询按钮进入 loading 状态；返回结果或修改查询条件后恢复。

### CardList 交互

- 卡片按单列纵向排列。
- 不默认支持整卡点击跳转。
- 如需进入详情，应优先使用标题链接、查看按钮或明确的操作按钮。
- 卡片内操作仅对当前卡片数据生效。
- 页面级操作不应放入单张卡片内部。
- Figma 当前卡片展示 3 个操作按钮；超过 3 个操作时，收纳方式需由 Figma 或业务规则确认。
- 主按钮数量不超过 1 个。
- 危险操作必须二次确认。
- 如果操作影响不可逆，确认弹窗中必须说明影响范围。
- 如果操作影响上下游对象，需展示关联提示。
- Tag 默认用于信息展示；是否可点击需由业务或 Figma 状态确认。
- 卡片描述支持长文本，但截断、换行、展开规则未在当前节点确认时统一写为 `待定`。

### 分页交互

- 当前 Figma 节点未展示 Pagination。
- 如果业务为分页列表，应使用 `Pagination` 组件。
- 如果业务为加载更多、无限滚动或不分页，需由业务或 Figma 模板确认。
- 不允许在未确认情况下自行新增分页、加载更多或无限滚动规则。

## 1.7 AI 生成约束

- 必须使用系统定义的 Token 和组件变体。
- 必须使用 `AppHeader`、`Sidebar-Left`、`Body` 的页面框架。
- CardList 必须采用单列纵向布局，不得自行改为宫格、瀑布流或营销卡片布局。
- Query Area 为可选区域，不得默认强制生成 `Filter-Bar`。
- 查询区域只能使用 Figma 中确认的 `Filter-Bar`、`Search`、`Capsule` 或其组合。
- 禁止新增未在 Figma 出现的筛选样式、状态、圆角、阴影或布局。
- 卡片必须使用 `Card` 组件，不得自定义卡片样式。
- 卡片内状态标记必须使用 `Tag` 组件。
- 卡片操作必须使用系统 `Button` 组件。
- 不得新增表格列、批量选择、列设置、冻结列等 TablePage 专属能力。
- 如业务需要复杂列对齐、批量操作或横向滚动，应切换为 `TablePage`。
- 必须包含 loading、empty、error 状态处理。
- 无法从 Figma 或 Token 确认的值统一写为 `待定`。
