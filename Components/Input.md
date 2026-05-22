# Input

## 1.1 用途

Input 用于单行文本输入、编号输入、关键词输入、数值输入和模糊搜索输入。

## 1.2 视觉规范

### 组件与变体

- 组件：`Input`
- 关联组件：`Input-Dropdown-Single`
- 变体属性：`Style`, `State`

### Style

| Style | 用途 |
|---|---|
| `Short` | 用于筛选区、窄表单、紧凑输入场景 |
| `Long` | 用于标准表单输入场景 |
| `Unit` | 用于带单位的数值输入场景 |

### State

| State | 用途 |
|---|---|
| `Default` | 默认输入状态 |
| `Hover` | 鼠标悬浮状态 |
| `Active` | 输入聚焦状态 |
| `Blur` | 失焦后状态 |
| `Disabled` | 禁用状态 |
| `Error` | 错误状态 |

### 视觉 Token

- 背景：`Background/Default`,`Background/Disabled Subtle`
- 文本：`Text/Primary`或`Text/Disabled` 
- placeholder： `Text/Thirdly`
- 边框：`Border/Default`, `Border/Hover`, `Border/Active`, `Border/Blur`, `Border/Disabled`, `Border/Error`
- 圆角：`Radius/Form`
- 最小高度：`36`
- 左右内边距：`12`
- 边框：`1`
- 图标：`Icon/CircleClose`
- 图标尺寸：`Size/16*16`
- 图标尺寸：`Size/16*16`
- 图标颜色：`Icon/Secondary`

## 1.3 状态规范

- default：可输入。
- hover：边框使用 hover Token。
- active：边框使用 active Token。
- blur：使用 Figma `Blur` 状态。
- disabled：禁止输入和聚焦。
- error：边框使用 error Token。

## 1.4 交互规则

- 支持普通文本输入。
- 输入内容应支持清空、校验和数据回显。
- 支持模糊搜索。
- 模糊搜索结果必须使用 `Input-Dropdown-Single` 展示并选择，不允许自己新增无关的结果面板。
- 用户输入关键字后触发搜索，结果在下拉中展示。
- 用户点击下拉项后，Input 显示所选结果。
- 当输入为空、无匹配结果或接口异常时，反馈方式应统一，使用 error Token。
- 错误信息应以内联提示展示在输入框下方，除非业务场景明确要求弹窗或提示。
- 禁止仅依赖 placeholder 作为字段说明。

## 1.5 业务场景示例

- 场景 1：【筛选区】中的【关键词查询】。
- 场景 2：【表单页】中的【名称 / 编码填写】。

## 1.6 前端适配点

- `Style` 映射为 `Short | Long | Unit`
- `State` 映射为 `Default | Hover | Active | Blur | Disabled | Error`
- `value` 映射输入值
- `placeholder` 映射占位文案
- `disabled` 映射禁用状态
- `onChange` 映射输入变化
- `onFocus` / `onBlur` 映射聚焦和失焦
- `showDropdown` 或等效状态用于模糊搜索下拉展示
- `options` 映射 `Input-Dropdown-Single` 的候选结果
- `onSelect` 映射下拉结果选中
- 远程搜索时需要支持输入值与展示值回显，接口字段映射规则：`待定`
- 组件名建议保持为 `Input`，模糊搜索联动能力通过额外属性或组合组件实现，不要拆成新的基础输入控件

## 1.7 AI 生成约束

- 必须使用系统 Input。
- 禁止使用 div 模拟输入框。
- 禁止新增 Figma 未出现的输入框尺寸和状态。
