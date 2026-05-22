# Title

## 1.1 用途

用于页面、区块、卡片或内容分组的标题层级。

## 1.2 视觉规范

- 组件：`Title`
- State：`Large`, `Middle`, `Little`
- 颜色：`Text/Primary`，`Text/Brand`，禁止自定义色值
- 文字：
  - `Large`:`Chart/主要`
  - `Middle`:`Heading/页面内容的标题`
  - `Little`:`Heading/弹窗内容标题`

## 1.4 交互规则

- Title 仅用于结构表达，不承担点击行为。
- 标题层级应与页面信息结构一致。
- 不得用 Title 制作营销式大标题。

## 1.5 业务场景示例

- 场景 1：【表单业务】中的【区块标题】
- 场景 2：【详情业务】中的【信息分组标题】

## 1.6 前端适配点

- `level` 或 `size` 映射 `Large | Middle | Little`
- 文本内容映射 `children` / `title`
- 组件名建议：`Title`

## 1.7 AI 生成约束

- 必须使用系统 `Title`。
- 禁止自定义标题字号和字重。
- 禁止生成营销式标题层级。
- 禁止新增未在 Figma 出现的尺寸、颜色、状态。
