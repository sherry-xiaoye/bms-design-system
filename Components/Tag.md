# Tag

## 1.1 用途

用于状态、分类、标签、风险等级等短文本标识。

## 1.2 视觉规范

- 组件：`Tag`
- Color：`Gray`, `Blue`, `Green`, `Orange`, `Red`
- 背景颜色：- `Gray`：`#Background/Top Navigation`，文本颜色：`Text/Primary`
- 背景颜色： `Blue`：`Background/Info`，文本颜色：`Text/Brand`
- 背景颜色：`Green`：`Background/Success`，文本颜色：`Text/Success`
- 背景颜色：`Orange`：`Background/Warning`，文本颜色：`Text/Warning`
- 背景颜色：`Red`：`Background/Error`，文本颜色：`Text/Error`
- 禁止自定义色值
- 圆角：`Radius/Smallest`
- 字体：`Body文本`
- 图标：`Icon/Close`  

## 1.3 状态规范

- default：`Gray`
- in progress：`Blue`
- error：`Error`
- warning：`Warning`
- success：`Success`

## 1.4 交互规则

- Tag 默认用于展示，不承担主操作。
- 如需可关闭、可点击按钮`Icon/Close`，点击后关闭 Tag。
-- 状态语义需与颜色一致。

## 1.5 业务场景示例

- 场景 1：【列表业务】中的【状态标签】
- 场景 2：【详情业务】中的【分类标签】

## 1.6 前端适配点

- `color` 映射 `Gray | Blue | Green | Orange | Red`
- `children` 映射标签文本
- 组件名建议：`Tag`

## 1.7 AI 生成约束

- 必须使用系统 `Tag`。
- 禁止自定义 Tag 颜色。
- 禁止用普通 span 模拟状态标签。
- 禁止新增未在 Figma 出现的尺寸、颜色、状态、圆角、阴影。
