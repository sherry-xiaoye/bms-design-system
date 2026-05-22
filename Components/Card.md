# Card

## 1.1 用途

用于承载相对独立的信息块，例如仪表盘指标、详情分组、列表卡片、信息摘要区块。

## 1.2 视觉规范
Card 支持以下信息类型：
- `Default`:背景颜色：`Background/Default`,描边：`Divider/Default`
- `Hover`:背景颜色：`Background/Default`,描边：`Border/Hover` 
- 背景颜色：`Background/Default`，禁止自定义色值
- 尺寸：默认自适应内容宽高，不定义固定高度
- 圆角：建议使用系统圆角 Token，默认中大圆角
- 边框 ：`1`
- 标题:`Heading/主页面和弹窗的标题`,`text/Primary`
- 正文:`Body/文本`,`text/Primary`
- 按钮：`Link`, `text/Brand`
- 内容结构：支持 `title`、`content`

## 1.3 状态规范

- default：默认展示信息分组
- hover：鼠标悬停卡片上启用 Hover

## 1.4 交互规则

- Card 可用于展示内容分组,2个Card之间间距默认`16`。
- 展示型 Card 不应模拟按钮交互。
- 禁止卡片嵌套卡片。
- Card 内操作区应尽量收敛，不在同一卡片中放置多个同级主操作。

## 1.5 业务场景示例

- 场景 1：【仪表盘业务】中的【指标卡片】
- 场景 2：【详情业务】中的【信息分组】
- 场景 3：【列表业务】中的【可点击列表卡片】
- 场景 4：【工作台业务】中的【摘要卡片】

## 1.6 前端适配点

- `state` 映射 `Default | Hover | Selected | Disabled`
- `clickable` 控制是否启用交互态
- `title` 映射卡片标题区
- `extra` 映射标题区右侧扩展内容
- `content` 映射主体内容
- `footer` 映射底部附加信息或操作区
- `children` 可作为自由内容插槽
- 组件名建议：`Card`

建议结构：

```tsx
<Card state="Default" clickable={false}>
  <Card.Header title="标题" extra="补充信息" />
  <Card.Content>内容区域</Card.Content>
  <Card.Footer>底部区域</Card.Footer>
</Card>
```

## 1.7 AI 生成约束

- 必须使用系统 `Card`。
- 禁止将页面大区块全部做成浮动卡片。
- 禁止卡片套卡片。
- 禁止将普通容器随意包装成高阴影 Card。
- 禁止把按钮、表单项、弹窗面板错误抽象成 Card。
- 禁止新增未在 Figma 出现的尺寸、颜色、状态、圆角、阴影。
