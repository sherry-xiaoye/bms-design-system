# Naming

本文件定义 TL Design System 的命名规则。命名必须区分 Figma 原始名称、Markdown 文件名、代码组件名、Props / Variant、CSS class 和 Token，不得混用。

## 1. 总原则

- Figma 中已存在的组件名、变体名、样式名、Token 名必须保留原始写法。
- 不得自行翻译、重命名、修正大小写、修正空格或修正拼写。
- 代码中可以建立 alias，但必须在组件文档的“前端适配”中说明映射关系。
- 未在 Figma 或 Token 中确认的名称写 `待定`，不得为了完整性自行补名。

## 2. Figma 组件命名

Figma 组件名按设计稿原名书写，例如：

```text
Button
TextButton
Link
Button-Danger
Button-Group
Input
Input-Dropdown-Single
Select
Select-DropdownMenu
Cascader
DatePicker
TimePicker
DateTimePicker
Table-Header
TableHeaderActions
Table-Dropdown-Single
ColumnSettings
Sort
Dialog
AppHeader
Sidebar-Left
```

命名规则：

- 不得把 Figma 组件名改写为自定义 class 名。
- 不得把多个 Figma 组件合并成一个新名称，除非 Figma 已存在组合组件。
- 不得新增 Figma 中未出现的组件名。
- 带中横线的名称必须保留中横线，例如 `Button-Danger`、`Input-Dropdown-Single`。
- 无中横线的名称不得强行拆分，例如 `TextButton`、`TableHeaderActions`。

## 3. Figma Variant 命名

Variant 属性和值必须按 Figma 文档或组件文档中的原始写法记录，例如：

```text
Style=Single
Style=Multiple
Style=Multiple Fold
Style=DateRange
Style=TimeRange
State=Default
State=Hover
State=Active
State=Blur
State=Disabled
Component=Date
Component=DateRange
```

命名规则：

- 文档中记录 Variant 时使用 `属性=值` 格式。
- 失焦状态统一使用 `Blur`，不得再使用旧失焦状态命名。
- `Style`、`State`、`Component` 等属性名不得自行翻译。
- 未确认的 Variant 必须写 `待定`。

## 4. Markdown 文件命名

文件名使用组件或页面模板英文名，并保持 README 中登记的名称。

```text
Components/AppHeader.md
Components/Button.md
Components/Input.md
Components/SelectAndPickers.md
Components/Table.md
Components/Dialog.md
Components/Feedback.md
Components/OverlayTips.md
Components/Default.md
Patterns/TablePage.md
Patterns/FormPage.md
Patterns/DetailPage.md
Patterns/DashboardPage.md
```

命名规则：

- 文件名不得随意改名。
- 一个文档承载多个相关组件时，文件名以合集语义命名，例如 `SelectAndPickers.md`、`Feedback.md`、`OverlayTips.md`。
- 新增文档前必须确认 Figma 中存在对应组件或页面模板。

## 5. 代码组件命名

代码组件名应使用前端框架常规组件命名方式，并映射到 Figma 原始组件名。

示例：

```tsx
<Button type="primary">查询</Button>
<Button danger>删除</Button>
<Input status="error" />
<Select mode="multiple" />
<DatePicker />
<TimePicker />
<DateTimePicker />
<Table rowSelection />
<Dialog open />
```

命名规则：

- 代码中用 Props 表达类型、状态、尺寸，不直接把 Figma Variant 名作为 class。
- Figma 的 `Button-Danger` 可映射为代码中的 `Button` + `danger`，但文档中必须保留 `Button-Danger` 原名。
- Figma 的 `Input-Dropdown-Single` 可映射为 Input 的搜索结果下拉能力，不能另起未确认组件名。
- Figma 的选择器组合必须分别映射为 `Select`、`Cascader`、`DatePicker`、`TimePicker`、`DateTimePicker`。

## 6. CSS Class 命名

CSS class 建议使用项目约定前缀和 kebab-case / BEM 形式。通用文档中使用 `ds-` 作为示例前缀，实际项目可按工程约定替换。

示例：

```css
.ds-button
.ds-button--primary
.ds-button--danger
.ds-input
.ds-input--error
.ds-table
.ds-table__header
.ds-dialog
```

命名规则：

- CSS class 不得直接使用 Figma Variant 全名，例如 `.Button-Primary-Hover`。
- CSS class 不得使用无项目前缀的泛化名称，例如 `.button`、`.input`。
- 状态 class 使用语义后缀，例如 `--active`、`--disabled`、`--error`。
- 不得同时混用 `button-primary`、`Button-Primary`、`btnPrimary` 等多套风格。

## 7. Token 命名

Token 名称必须保留 Figma / JSON 中的原始命名。

示例：

```text
Background/Default
Background/Disabled Subtle
Background/TableHeader
Text/Primary
Text/brand
Border/Table
Icon/Brand
Charts/Backgroung
Color/Orange/Orange- O1
Radius/Card Small
Radius/Card Larger
Radius/Form
Spacing/5
Size/16*16
```

命名规则：

- 业务 UI 优先使用 Semantic Token，其次 Primitive Token。
- 禁止把 Token 名改写为自定义 CSS 变量名。
- 禁止修正 Token 中已有的大小写、空格、拼写问题。
- `Text/brand` 必须保留小写 `brand`。
- `Charts/Backgroung` 必须保留原始拼写。
- `Color/Orange/Orange- O1` 必须保留中横线后的空格。

## 8. 状态命名

状态名称必须以组件文档和 Figma 为准。

常见状态：

```text
Default
Hover
Active
Focus
Blur
Disabled
Error
Loading
Selected
Empty
```

命名规则：

- 文档中状态名优先使用 Figma 原始英文。
- 中文说明可以跟在状态名后，例如 `Default 默认状态`。
- 未在 Figma 中确认的状态必须写 `待定`。
- 禁止为组件新增未确认状态，例如随意新增 `warning`、`success`、`expanded`。

## 9. 禁止事项

- 禁止在代码里使用 `Button-Primary-Hover` 作为 class。
- 禁止将 Figma 组件名、代码组件名、CSS class、Token 名混用。
- 禁止新增没有语义的颜色变量，例如 `--blue1`、`--gray2`。
- 禁止把 `Background/Default` 改写成 `bgDefault` 后在文档中当作 Token。
- 禁止把 Figma 中不存在的组合组件命名为系统组件。
- 禁止为了统一风格而修改 Figma 原始命名。
