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