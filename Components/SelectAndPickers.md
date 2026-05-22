# SelectAndPickers

## Select

### 1.1 用途

用于从已知选项中选择一个或多个值。包含单选、多选和多选折叠形态，并配套 `Select-DropdownMenu` 下拉菜单。

### 1.2 视觉规范

- 背景：`Background/Default`,`Background/Disabled Subtle`
- 文本：`Text/Primary`或`Text/Disabled` 
- placeholder： `Text/Thirdly`
- 边框：`Border/Default`, `Border/Hover`, `Border/Active`, `Border/Blur`, `Border/Disabled`, `Border/Error`
- 图标：`Icon/Arrow-Down`
- 图标颜色：`Icon/Secondary`
- 尺寸：
  - `Select` 触发器宽度：`240px`
  - `Select` 触发器高度：`36px`
  - `Select-DropdownMenu / Single`：`240px x Max192px`
  - `Select-DropdownMenu / Multiple`：`240px x Max192px`
  - 左右内边距：`12`
  - 圆角：`Radius/Form`
  - 边框：`1`
  - 图标：`Size/16*16`


### 1.3 状态规范

- default 默认状态：
  - `Style=Single, State=Default`
  - `Style=Multiple, State=Default`
- hover 悬浮状态：
  - `Style=Single, State=Hover`
  - `Style=Multiple, State=Hover`
- active / focus 激活状态：
  - `Style=Single, State=Active`
  - `Style=Multiple, State=Active`
- blur 失焦状态：
  - `Style=Single, State=Blur`
  - `Style=Multiple, State=Blur`
  - `Style=Multiple Fold, State=Blur`
- disabled 禁用状态：
  - `Style=Single, State=Disabled`
  - `Style=Multiple, State=Disabled`

### 1.4 交互规则

- 点击 Select 触发器后展开对应下拉菜单。
- `Single` 用于单值选择。
- `Multiple` 用于多值选择。
- `Multiple Fold` 用于多选结果折叠展示。
- 选择选项后，触发器区域回显已选值。
- 禁用状态不可点击、不可展开、不可选择。
- 多选时，Filter Bar中多选折叠，表单中使用多选。

### 1.5 业务场景示例

- 场景 1：【筛选业务】中的【状态选择】
- 场景 2：【表单业务】中的【枚举字段选择】

### 1.6 前端适配点

- Props / Variant 映射：
  - `style` 映射 `Single | Multiple | Multiple Fold`
  - `state` 映射 `Default | Hover | Active | Blur | Disabled`
  - `dropdownType` 映射 `Single | Multiple`
- 数据回显规则：
  - 单选回显单个 label。
  - 多选回显多个已选项。
  - 多选折叠回显规则：首个选项展示名称，其余的收起来展示为数量。
- 接口字段映射说明：
  - 选项 label 字段：`待定`
  - 选项 value 字段：`待定`
  - disabled 字段：`待定`
- 样式类名 / 组件名规范：
  - 组件名使用 `Select`
  - 下拉菜单使用 `Select-DropdownMenu`
  - 禁止新建未在 Figma 出现的选择器组件名。

### 1.7 AI 生成约束

- 必须使用系统定义的 `Select` 和 `Select-DropdownMenu`。
- 必须使用 Figma 中确认的 `Single`、`Multiple`、`Multiple Fold` 变体。
- 禁止自定义样式、状态和交互。
- 生成时必须包含已确认的 `Default`、`Hover`、`Active`、`Blur`、`Disabled` 状态。
- 禁止新增未在 Figma 出现的尺寸、颜色、状态、圆角、阴影。

## Cascader

### 1.1 用途

用于层级数据选择。包含单选、多选和折叠形态，并配套级联下拉菜单。

### 1.2 视觉规范

- - 背景：`Background/Default`,`Background/Disabled Subtle`
- 文本：`Text/Primary`或`Text/Disabled` 
- placeholder： `Text/Thirdly`
- 边框：`Border/Default`, `Border/Hover`, `Border/Active`, `Border/Blur`, `Border/Disabled`, `Border/Error`
- 图标：`Icon/Arrow-Down`
- 图标颜色：`Icon/Secondary`
- 尺寸：
  - `Cascader` 触发器宽度：`240px`
  - `Cascader` 触发器高度：`36px`
  - `Cascader-DropdownMenu / Single`：`322px x Max192px`
  - `Cascader-DropdownMenu / Multiple`：`322px x Max192px`
  - 内边距：`12`
  - 圆角：`Radius/Form`
  - 边框：`1`
  - 图标：`Size/16*16`

### 1.3 状态规范

- default 默认状态：
  - `Style=Single, State=Default`
  - `Style=Multiple, State=Default`
- hover 悬浮状态：
  - `Style=Single, State=Hover`
  - `Style=Multiple, State=Hover`
- active / focus 激活状态：
  - `Style=Single, State=Active`
  - `Style=Multiple, State=Active`
- blur 失焦状态：
  - `Style=Single, State=Blur`
  - `Style=Multiple, State=Blur`
  - `Style=Fold, State=Blur`
- disabled 禁用状态：
  - `Style=Single, State=Disabled`
  - `Style=Multiple, State=Disabled`

### 1.4 交互规则

- 点击 Cascader 触发器后展开级联下拉菜单。
- `Single` 用于选择单条层级路径。
- `Multiple` 用于选择多条层级路径。
- `Fold` 用于选择结果折叠展示。
- 选择完成后，触发器区域回显已选层级路径。
- 禁用状态不可点击、不可展开、不可选择。

### 1.5 业务场景示例

- 场景 1：【组织业务】中的【组织层级选择】
- 场景 2：【区域业务】中的【省市区层级选择】

### 1.6 前端适配点

- Props / Variant 映射：
  - `style` 映射 `Single | Multiple | Fold`
  - `state` 映射 `Default | Hover | Active | Blur | Disabled`
  - `dropdownType` 映射 `Single | Multiple`
- 数据回显规则：
  - 单选回显一条完整层级路径。
  - 多选回显多条层级路径。
  - 折叠展示规则：首个选项展示名称，其余的收起来展示为数量。
- 接口字段映射说明：
  - 节点 label 字段：`待定`
  - 节点 value 字段：`待定`
  - children 字段：`待定`
  - disabled 字段：`待定`
- 样式类名 / 组件名规范：
  - 组件名使用 `Cascader`
  - 下拉菜单使用 `Cascader-DropdownMenu`

### 1.7 AI 生成约束

- 必须使用系统定义的 `Cascader` 和 `Cascader-DropdownMenu`。
- 必须使用 Figma 中确认的 `Single`、`Multiple`、`Fold` 变体。
- 禁止自定义样式、状态和交互。
- 生成时必须包含已确认的 `Default`、`Hover`、`Active`、`Blur`、`Disabled` 状态。
- 禁止新增未在 Figma 出现的尺寸、颜色、状态、圆角、阴影。

## DatePicker

### 1.1 用途

用于日期类字段选择。Figma 节点中确认包含年、月、周、日期和日期范围形态，并配套 DatePicker 下拉菜单。

### 1.2 视觉规范

- 背景：`Background/Default`,`Background/Disabled Subtle`
- 文本：`Text/Primary`或`Text/Disabled` 
- placeholder： `Text/Thirdly`
- 边框：`Border/Default`, `Border/Hover`, `Border/Active`, `Border/Blur`, `Border/Disabled`, `Border/Error`
- 图标：`Icon/Date`
- 图标颜色：`Icon/Primary`,`Icon/Secondary`,`Icon/Disabled`
- 尺寸：
 - `Year` 触发器：`240px x 36px`
  - `Month` 触发器：`240px x 36px`
  - `Week` 触发器：`240px x 36px`
  - `Date` 触发器：`240px x 36px`
  - `DateRange` 触发器：`320px x 36px`
  - `Dropdown / Year`：`280px x 305px`
  - `Dropdown / Month`：`280px x 305px`
  - `Dropdown / Week`：`280px x 344px`
  - `Dropdown / Day`：`280px x 344px`
  - `Dropdown / DateRange`：`560px x 344px`
  - 左右内边距：`12`
  - 圆角：`Radius/Form`
  - 边框：`1`
  - 图标：`Size/16*16`

### 1.3 状态规范

- default 默认状态：
  - `Style=Year, State=Default`
  - `Style=Month, State=Default`
  - `Style=Week, State=Default`
  - `Style=Date, State=Default`
  - `Style=DateRange, State=Default`
- hover 悬浮状态：
  - `Style=Year, State=Hover`
  - `Style=Month, State=Hover`
  - `Style=Week, State=Hover`
  - `Style=Date, State=Hover`
  - `Style=DateRange, State=Hover`
- active / focus 激活状态：
  - `Style=Year, State=Active`
  - `Style=Month, State=Active`
  - `Style=Week, State=Active`
  - `Style=Date, State=Active`
  - `Style=DateRange, State=Active`
- blur 失焦状态：
  - Figma 变体名为 `Blur`
  - 覆盖 `Year`、`Month`、`Week`、`Date`、`DateRange`
- disabled 禁用状态：
  - `Style=Year, State=Disabled`
  - `Style=Month, State=Disabled`
  - `Style=Week, State=Disabled`
  - `Style=Date, State=Disabled`
  - `Style=DateRange, State=Disabled`

### 1.4 交互规则

- 点击 DatePicker 触发器后展开对应日期下拉面板。
- `Year` 用于年份选择。
- `Month` 用于月份选择。
- `Week` 用于周选择。
- `Date` 用于单日期选择。
- `DateRange` 用于日期范围选择。
- 选择完成后，触发器区域回显日期或日期范围。
- 禁用状态不可点击、不可展开、不可选择。
- 异常场景处理逻辑：起始日期前的日期不展示，起止范围内不可选的日期禁用状态选择，字体颜色使用`Text/Disabled`。

### 1.5 业务场景示例

- 场景 1：【筛选业务】中的【日期范围筛选】
- 场景 2：【表单业务】中的【生效日期选择】

### 1.6 前端适配点

- Props / Variant 映射：
  - `style` 映射 `Year | Month | Week | Date | DateRange`
  - `state` 映射 `Default | Hover | Active | Blur | Disabled`
  - 下拉类型映射 `Year | Month | Week | Day | DateRange`
- 数据回显规则：
  - 单值日期回显单个日期值。
  - 日期范围回显开始日期和结束日期。
  - 日期格式：`待定`。
- 接口字段映射说明：
  - 单日期字段：`待定`
  - 开始日期字段：`待定`
  - 结束日期字段：`待定`
  - 禁用日期字段：`待定`
- 样式类名 / 组件名规范：
  - 组件名使用 `DatePicker`
  - 下拉菜单使用 DatePicker 对应 DropdownMenu
  - 代码中将 `Blur` 映射为 `blur`，事件使用 `onBlur`。

### 1.7 AI 生成约束

- 必须使用系统定义的 `DatePicker` 及其下拉菜单。
- 必须使用 Figma 中确认的 `Year`、`Month`、`Week`、`Date`、`DateRange` 变体。
- 禁止自定义样式、状态和交互。
- 生成时必须包含已确认的 `Default`、`Hover`、`Active`、`Blur`、`Disabled` 状态。
- 禁止新增未在 Figma 出现的尺寸、颜色、状态、圆角、阴影。

## TimePicker

### 1.1 用途

用于时间字段选择。确认包含单时间和时间范围两种形态，并配套 TimePicker 下拉菜单。

### 1.2 视觉规范

- 背景：`Background/Default`,`Background/Disabled Subtle`
- 文本：`Text/Primary`或`Text/Disabled` 
- placeholder： `Text/Thirdly`
- 边框：`Border/Default`, `Border/Hover`, `Border/Active`, `Border/Blur`, `Border/Disabled`, `Border/Error`
- 图标：`Icon/Clock`
- 图标颜色：`Icon/Primary`,`Icon/Secondary`,`Icon/Disabled`
- 尺寸：
 - 尺寸：
  - `Time` 触发器：`240px x 36px`
  - `TimeRange` 触发器：`320px x 36px`
  - `Dropdown / Time`：`188px x 273px`
  - `Dropdown / TimeRange`：`436px x 334px`
  - 左右内边距：`12`
  - 圆角：`Radius/Form`
  - 边框：`1`
  - 图标：`Size/16*16`

### 1.3 状态规范

- default 默认状态：
  - `Style=Time, State=Default`
  - `Style=TimeRange, State=Default`
- hover 悬浮状态：
  - `Style=Time, State=Hover`
  - `Style=TimeRange, State=Hover`
- active / focus 激活状态：
  - `Style=Time, State=Active`
  - `Style=TimeRange, State=Active`
- blur 失焦状态：
  - `Style=Time, State=Blur`
  - `Style=TimeRange, State=Blur`
- disabled 禁用状态：
  - `Style=Time, State=Disabled`
  - `Style=TimeRange, State=Disabled`

### 1.4 交互规则

- 点击 TimePicker 触发器后展开对应时间下拉面板。
- `Time` 用于单时间选择。
- `TimeRange` 用于时间范围选择。
- 选择完成后，触发器区域回显时间或时间范围。
- 禁用状态不可点击、不可展开、不可选择。
- 异常场景处理逻辑：结束时间要在开始时间之后。

### 1.5 业务场景示例

- 场景 1：【排班业务】中的【时间段选择】
- 场景 2：【筛选业务】中的【操作时间筛选】

### 1.6 前端适配点

- Props / Variant 映射：
  - `style` 映射 `Time | TimeRange`
  - `state` 映射 `Default | Hover | Active | Blur | Disabled`
  - 下拉类型映射 `Time | TimeRange`
- 数据回显规则：
  - 单时间回显一个时间值。
  - 时间范围回显开始时间和结束时间。
  - 时间格式：`待定`。
- 接口字段映射说明：
  - 单时间字段：`待定`
  - 开始时间字段：`待定`
  - 结束时间字段：`待定`
  - 禁用时间字段：`待定`
- 样式类名 / 组件名规范：
  - 组件名使用 `TimePicker`
  - 下拉菜单使用 TimePicker 对应 DropdownMenu

### 1.7 AI 生成约束

- 必须使用系统定义的 `TimePicker` 及其下拉菜单。
- 必须使用 Figma 中确认的 `Time`、`TimeRange` 变体。
- 禁止自定义样式、状态和交互。
- 生成时必须包含已确认的 `Default`、`Hover`、`Active`、`Blur`、`Disabled` 状态。
- 禁止新增未在 Figma 出现的尺寸、颜色、状态、圆角、阴影。

## DateTimePicker

### 1.1 用途

用于同时选择日期和时间。确认包含日期和日期范围形态，并配套日期、日期范围、时间下拉面板。

### 1.2 视觉规范

- 背景：`Background/Default`,`Background/Disabled Subtle`
- 文本：`Text/Primary`或`Text/Disabled` 
- placeholder： `Text/Thirdly`
- 边框：`Border/Default`, `Border/Hover`, `Border/Active`, `Border/Blur`, `Border/Disabled`, `Border/Error`
- 图标：`Icon/Date`
- 图标颜色：`Icon/Primary`,`Icon/Secondary`,`Icon/Disabled`
- 尺寸：
  - `Date` 触发器：`240px x 36px`
  - `DateRange` 触发器：`320px x 36px`
  - `Dropdown / Date`：`278px x 384px`
  - `Dropdown / DateRange`：`560px x 384px`
  - `Dropdown / Time`：`188px x 273px`
  - 左右内边距：`12`
  - 圆角：`Radius/Form`
  - 边框：`1`
  - 图标：`Size/16*16`

### 1.3 状态规范

- default 默认状态：
  - `Component=Date, State=Default`
  - `Component=DateRange, State=Default`
- hover 悬浮状态：
  - `Component=Date, State=Hover`
  - `Component=DateRange, State=Hover`
- active / focus 激活状态：
  - `Component=Date, State=Active`
  - `Component=DateRange, State=Active`
- blur 失焦状态：
  - Figma 变体名为 `Blur`
  - 覆盖 `Date`、`DateRange`
- disabled 禁用状态：
  - `Component=Date, State=Disabled`
  - `Component=DateRange, State=Disabled`

### 1.4 交互规则

- 点击 DateTimePicker 触发器后展开日期或日期范围面板。
- 选择日期后可继续选择时间。
- `Date` 用于单个日期时间选择。
- `DateRange` 用于日期时间范围选择。
- 选择完成后，触发器区域回显日期时间或日期时间范围。
- 禁用状态不可点击、不可展开、不可选择。
- 异常场景处理逻辑：结束时间要在开始时间之后。

### 1.5 业务场景示例

- 场景 1：【任务业务】中的【开始 / 结束日期时间选择】
- 场景 2：【筛选业务】中的【创建时间范围筛选】

### 1.6 前端适配点

- Props / Variant 映射：
  - `component` 映射 `Date | DateRange`
  - `state` 映射 `Default | Hover | Active | Blur | Disabled`
  - 下拉类型映射 `Date | DateRange | Time`
- 数据回显规则：
  - 单个日期时间回显一个完整日期时间值。
  - 日期时间范围回显开始日期时间和结束日期时间。
  - 日期时间格式：`待定`。
- 接口字段映射说明：
  - 单日期时间字段：`待定`
  - 开始日期时间字段：`待定`
  - 结束日期时间字段：`待定`
  - 禁用日期时间字段：`待定`
- 样式类名 / 组件名规范：
  - 组件名使用 `DateTimePicker`
  - 下拉菜单使用 `DateTimePicker-DropdownMenu`
  - 代码中将 `Blur` 映射为 `blur`，事件使用 `onBlur`。

### 1.7 AI 生成约束

- 必须使用系统定义的 `DateTimePicker` 和 `DateTimePicker-DropdownMenu`。
- 必须使用 Figma 中确认的 `Date`、`DateRange`、`Time` 下拉类型。
- 禁止自定义样式、状态和交互。
- 生成时必须包含已确认的 `Default`、`Hover`、`Active`、`Blur`、`Disabled` 状态。
- 禁止新增未在 Figma 出现的尺寸、颜色、状态、圆角、阴影。
