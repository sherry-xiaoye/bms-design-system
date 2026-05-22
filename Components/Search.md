# Search

## 1.1 用途

Search 用于关键词搜索、列表快速检索和页面内对象查询。适用于需要用户输入搜索词并触发查询的场景。

Figma 原始组件名称为 `Search`，节点 ID 为 `2727:1692`。

## 1.2 视觉规范

### 组件与变体

- 组件：`Search`
- 建议文档文件名：`Search.md`
- 变体属性：`State`
- 可选能力：`Delete`，用于展示清空图标

### State

| State | 用途 |
|---|---|
| `Default` | 默认占位状态 |
| `Hover` | 鼠标悬浮状态 |
| `Active` | 输入聚焦 / 激活状态 |
| `Blur` | 失焦后状态 |
| `Disable` | 禁用状态，按 Figma 原始命名记录 |
| `Error` | 错误状态 |

### 尺寸

| 项目 | 规范 | 来源 |
|---|---:|---|
| 宽度 | `320px` | Figma |
| 高度 | `36px` | Figma |
| 圆角 | `Radius/Form` | Token |
| 边框 | `1px` | Figma |
| 左侧图标尺寸 | `Size/16*16` | Token |
| 左侧图标位置 | left `12px`, top `10px` | Figma |
| 文本起点 | left `32px`, top `9px` | Figma |
| 清空图标尺寸 | `Size/16*16` | Token |
| 清空图标位置 | left `292px`, top `10px` | Figma |
| 错误提示位置 | top `40px` | Figma |

### 颜色 Token

- 背景：`Background/Default`
- 禁用背景：`Background/Disabled Subtle`
- 默认文本 / placeholder：`Text/Thirdly`
- 输入后文本：`Text/Primary`
- 错误提示文字：`Text/Error`
- 边框：
  - Default：`Border/Default`
  - Hover：`Border/Hover`
  - Active：`Border/Active`
  - Blur：`Border/Blur`
  - Disable：`Border/Disabled`
  - Error：`Border/Error`
- 图标：
  - 搜索图标：`Icon/Search`
  - 清空图标：`Icon/CircleClose`
  - 图标颜色：`Icon/Secondary`
  - 禁用图标颜色：`待定`

### 字体

| 文本 | 字体样式 | 颜色 |
|---|---|---|
| 占位文字 `搜索` | `Body/文本`，12px / 18px，Regular | `Text/Thirdly` |
| 输入文字 | `Body/文本`，12px / 18px，Regular | `Text/Primary` |
| 错误提示文字 | 12px，Regular | `Text/Error` |

## 1.3 状态规范

- default 默认状态：
  - Figma：`State=Default`
  - 展示搜索图标和 placeholder 文案 `搜索`
  - 文本颜色使用 `Text/Thirdly`
  - 边框使用 `Border/Default`

- hover 悬浮状态：
  - Figma：`State=Hover`
  - 鼠标悬浮时边框使用 `Border/Hover`
  - placeholder 和搜索图标保持可识别状态

- active / focus 激活状态：
  - Figma：`State=Active`
  - 输入框获得焦点
  - 文本颜色使用 `Text/Primary`
  - 边框使用 `Border/Active`

- blur 失焦状态：
  - Figma：`State=Blur`
  - 输入框失焦后保留已输入内容
  - 文本颜色使用 `Text/Primary`
  - 边框使用 `Border/Blur`

- disabled 禁用状态：
  - Figma：`State=Disable`
  - 禁止输入、聚焦和清空
  - 背景使用 `Background/Disabled Subtle`
  - 边框使用 `Border/Disabled`
  - 文本颜色使用 `Text/Disabled`

- error 错误状态：
  - Figma：`State=Error`
  - 边框使用 `Border/Error`
  - 下方展示错误提示文案
  - 错误提示文字使用 `Text/Error`

- loading 加载状态：
  - Figma 未确认，写 `待定`

## 1.4 交互规则

- 点击 Search 后进入 `Active` 状态。
- 用户输入关键词后，Search 显示输入内容。
- 当 `Delete=true` 且输入内容不为空时，可展示清空图标。
- 点击清空图标后，清空当前输入内容，并恢复 placeholder。
- 查询触发方式由业务确认，可使用：
  - 输入后即时查询：`待定`
  - 按 Enter 查询：`待定`
  - 点击搜索图标查询：`待定`
- 禁用状态下不可输入、不可聚焦、不可清空。
- 错误状态下错误信息以内联提示展示在输入框下方。
- 不得使用弹窗替代 Search 的错误提示，除非业务流程明确要求。

## 1.5 业务场景示例

- 场景 1：【列表页】中的【关键词快速搜索】
- 场景 2：【表格页】中的【名称 / 编码 / 关键字段检索】

## 1.6 前端适配点

### Props / Variant 映射

| Props | Figma 映射 | 说明 |
|---|---|---|
| `state` | `Default \| Hover \| Active \| Blur \| Disable \| Error` | 状态映射 |
| `value` | 输入文字 | 当前搜索词 |
| `placeholder` | 默认文案 `搜索` | 占位提示 |
| `disabled` | `State=Disable` | 禁用状态 |
| `error` | `State=Error` | 错误状态 |
| `errorMessage` | 错误文字提示 | 错误提示文案 |
| `showDelete` | `Delete=true` | 是否展示清空图标 |
| `onChange` | 输入行为 | 输入变化 |
| `onClear` | 清空图标 | 清空输入 |
| `onSearch` | 搜索行为 | 查询触发 |

### 数据回显规则

- 有搜索值时，Search 回显 `value`。
- 无搜索值时，展示 placeholder 文案 `搜索`。
- 清空后 `value` 置空。
- 禁用状态下仍可回显已有值，但不可编辑。

### 样式类名 / 组件名规范

- 建议代码组件名：`Search`
- Figma 原始名称：`Search`
- 文件名建议：`Search.md`
- 状态命名以 Figma 为准，禁用态记录为 `Disable`；代码中可映射为 `disabled`

## 1.7 AI 生成约束

- 必须使用 Figma 中确认的 `Search` 组件结构。
- 必须包含 `Default`、`Hover`、`Active`、`Blur`、`Disable`、`Error` 状态。
- 必须使用系统 Token，不得自定义颜色、圆角、边框和字号。
- 禁止把 Search 改造成普通 Input 后自行补样式。
- 禁止新增 Figma 未确认的尺寸、状态、圆角、阴影和交互。
- 禁止新增未确认的 loading 状态；如业务需要，必须标记为 `待定`。