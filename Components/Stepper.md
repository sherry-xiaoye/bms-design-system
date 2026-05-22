# Stepper

## 1.1 用途

用于数值递增、递减输入，适合有明确范围或步长的数值字段。

## 1.2 视觉规范

- 组件：`Stepper`
- 尺寸：`132px x 36px`
- 颜色：
- `Default`：文字使用`Text/Primary`，背景使用`Background/Default`,`Border/Default`,图标使用`Icon/Minus`,`Icon/Plus`,`Icon/Primary`
- `Hover`：文字使用`Text/Primary`，背景使用`Background/Hover`,`Border/Hover`,图标使用`Icon/Minus`,`Icon/Plus`,`Icon/Primary`
- `Active`：文字使用`Text/Primary`，背景使用`Background/Active`,`Border/Active`,图标使用`Icon/Minus`,`Icon/Plus`,`Icon/Primary`
- `Blur`：文字使用`Text/Primary`，背景使用`Background/Blur`,`Border/Blur`,图标使用`Icon/Minus`,`Icon/Plus`,`Icon/Primary`
- `Disabled`：文字使用`Text/Disabled`，背景使用`Background/Disabled Subtle`,`Border/Disabled`,图标使用`Icon/Minus`,`Icon/Plus`,`Icon/Disabled`
- 禁止自定义色值
- 圆角：左右两边圆角`Radius/Form`
- 边框：`1`
- 字体：`Text/Primary`
- 图标：`Size/16*16`

## 1.3 状态规范

- default：`Default`
- hover：`Hover`
- active：`Active`
- blur：`Blur`
- disabled：`Disabled`


## 1.4 交互规则

- 点击加号增加数值。
- 点击减号减少数值。
- 可输入范围、步长、最小值、最大值规则待定。
- 禁用状态不可输入、不可点击。

## 1.5 业务场景示例

- 场景 1：【配置业务】中的【数量设置】
- 场景 2：【表单业务】中的【排序值填写】

## 1.6 前端适配点

- `value` 映射当前数值
- `min` / `max` / `step` 映射范围与步长，具体规则待定
- `disabled` 映射禁用状态
- Figma 状态名统一为 `Blur`，代码中映射为 `blur`

## 1.7 AI 生成约束

- 必须使用系统 `Stepper`。
- 禁止用 Input + Button 自行拼装。
- 禁止新增未在 Figma 出现的状态名。
- 禁止新增未在 Figma 出现的状态、尺寸、颜色、圆角、阴影。
