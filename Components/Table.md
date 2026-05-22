# Table

## 使用场景

用于结构化数据展示、批量操作、排序、列设置、行内操作和表格操作菜单。适用于列表页、详情关联列表、日志列表和配置列表等高频数据场景。

## 允许变体

- `Table-Header`
- `TableHeaderActions`
- `Table-Dropdown-Single`
- `ColumnSettings`
- `Sort`

Figma 映射：

| 组件 | Figma 节点 | 用途 |
|---|---|---|
| `TableHeaderActions` | `2248:5658` | 表格上方默认工具栏 / 批量操作栏 |
| `ColumnSettings` | `2271:1358` | 列显示、列宽、冻结、字段顺序配置 |
| `Table-Dropdown-Single` | `2282:6310` | 表格行内更多操作的单列下拉菜单 |

`TableHeaderActions` 已确认属性：

| Props / Variant | 可选值 | 说明 |
|---|---|---|
| `LeftActions` | `Ture` / `False` | 是否展示左侧全局操作区；保留 Figma 原始拼写 `Ture` |
| `RightTools` | `true` / `false` | 是否展示右侧列表工具区 |
| `State` | `Default（Toolbar）` / `Selected（BulkActionBar）` | 默认工具栏 / 批量操作栏 |

## 尺寸与视觉

- 表头背景：`Background/TableHeader`
- 表头文本：`Text/TableHeader`
- 表格线：`Border/Table`
- 表格行 hover 背景：`Background/Zebra`
- 表格正文：`Body/文本`
- 表格工具栏宽度：自动填充满 Body 可用区域；Figma 节点中的固定宽度仅作为设计画布参考。
- `TableHeaderActions`：背景使用 `Background/Default`，底部间距使用 `Spacing/5`，操作按钮间距使用 `Spacing/3` 或 `Spacing/5`。
- `ColumnSettings`：面板背景使用 `Background/Default`，阴影使用 Figma Effect Style `Drop shadow`，标题使用 `Heading/主页面和弹窗的标题`。
- `ColumnSettings` 表头：字段 / 列宽 / 冻结 / 显示，表头高度 `44px`，字段行高度 `48px`。
- `ColumnSettings` 操作区：底部使用 `Button-Group`，包含 `重置` 与 `保存`。
- `Table-Dropdown-Single`：宽度 `88px`，高度 `96px`，每项高度 `32px`，背景使用 `Background/Default`，hover / 选中项背景使用 `Background/Zebra`，文本使用 `Text/brand`。
- 最小行高：`40`
- 单元格 padding：`12`
- 未在 Figma 或 Token 中确认的尺寸、圆角、阴影写 `待定`。

## 状态

- default：正常数据展示。
- hover：行 hover 背景使用 `Background/Zebra`。
- loading：首次加载、查询、重置、分页切换、列表工具生效、批量操作刷新时必须支持。
- empty：无数据时必须展示空状态。
- error：接口失败时展示错误反馈和重试入口。
- selected：选中行后 `TableHeaderActions` 切换为 `State=Selected（BulkActionBar）`。
- disabled：无权限操作、不可选行、当前数据态不可执行操作使用禁用状态。

## 交互规则

- 默认工具栏使用 `TableHeaderActions` 的 `State=Default（Toolbar）`。
- 勾选行后切换为 `State=Selected（BulkActionBar）`，不得同时展示默认工具栏。
- `LeftActions=False` 且 `RightTools=true` 时，仅展示右侧列表工具。
- `RightTools=false` 时，不展示列设置、排序等右侧工具。
- 列显示、列宽、冻结、字段顺序配置使用 `ColumnSettings`。
- `ColumnSettings` 中主键不可隐藏；冻结列数量上限为 5 列。
- `ColumnSettings` 点击 `保存` 后配置生效并刷新列表；点击 `重置` 恢复默认列配置。
- 页面再次刷新后应保留最近一次列配置。
- 行内操作多于 2 个时，收纳进 `Icon/More` 触发的更多菜单；下拉内容使用 `Table-Dropdown-Single`。
- `Table-Dropdown-Single` 菜单项点击后执行对应动作；危险项必须进入二次确认。
- 排序使用 `Sort`。单字段排序优先在表头触发，多字段排序在列表工具中处理。
- 行内操作使用 `TextButton` 或 `Link`；不使用大按钮堆叠。

## 前端适配

- `columns` 映射表头配置。
- `dataSource` 映射接口列表数据。
- `rowSelection` 映射 Checkbox Cell 与批量操作栏状态。
- `sorter` 映射 `Sort`。
- `toolbar` 映射 `TableHeaderActions`。
- `toolbar.state` 映射 `Default（Toolbar） | Selected（BulkActionBar）`。
- `toolbar.leftActions` 映射 Figma `LeftActions=Ture | False`。
- `toolbar.rightTools` 映射 Figma `RightTools=true | false`。
- `columnSettings` 映射 `ColumnSettings`，包含字段顺序、列宽、冻结、显示 / 隐藏。
- `rowActions.moreTrigger` 映射 `Icon/More`。
- `rowActions.moreMenu` 映射 `Table-Dropdown-Single`。
- Figma 中 `LeftActions=Ture` 拼写需保留；代码可建立 `leftActions=true` alias，但必须在实现中注明映射关系。

## 禁止事项

- 禁止用 `div` 拼表格。
- 禁止伪造未在 Figma 出现的表格工具栏、列设置面板和行内菜单。
- 禁止全局操作与批量操作混排。
- 禁止列表工具区出现危险操作。
- 禁止隐藏主键列。
- 禁止冻结列超过 5 列。
- 禁止行内操作堆叠大按钮。
- 禁止自定义表头颜色、表格边框、行 hover 背景。

## AI 生成约束

- 表格页必须使用系统 `Table`、`TableHeaderActions`、`ColumnSettings`、`Table-Dropdown-Single`、`Pagination`；非分页场景需由业务或 Figma 模板确认。
- 必须包含 loading / empty / error / selected / disabled 状态。
- 批量操作出现时，必须使用 `TableHeaderActions` 的 `Selected（BulkActionBar）` 状态。
- 行内更多菜单必须使用 `Table-Dropdown-Single`。
- 列设置必须使用 `ColumnSettings`。
- 禁止新增未在 Figma 或 Token 中确认的颜色、圆角、阴影、状态。
- 未确认的表格尺寸、间距、圆角、阴影必须写 `待定`。
