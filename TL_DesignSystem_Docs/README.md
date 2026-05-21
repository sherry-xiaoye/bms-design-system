# TL Design System Docs

本仓库是面向多业务系统复用的设计系统 Markdown 文档包，用于设计规范沉淀、前端实现对齐，以及 Cursor / Claude / Windsurf / Figma Make / Stitch 等 AI 工具协作。

文档来源优先级：

1. Figma 组件库与 Figma MCP 读取结果
2. `Foundations/SemanticTokens.json`
3. `Foundations/PrimitivesTokens.json`
4. 已确认的 Markdown 规范文档

如 Figma、Token 与 Markdown 描述不一致，以 Figma 和 Token 为准。未确认的颜色、尺寸、圆角、阴影、间距、字号、状态样式必须标记为 `待定`。

## 目录结构

```text
TL_DesignSystem_Docs/
├── README.md
├── Foundations/
│   ├── SemanticTokens.json
│   ├── PrimitivesTokens.json
│   ├── Color.md
│   ├── Typography.md
│   ├── Spacing.md
│   ├── Grid.md
│   └── Icon.md
├── Components/
│   ├── AppHeader.md
│   ├── Button.md
│   ├── Input.md
│   ├── SelectAndPickers.md
│   ├── Table.md
│   ├── Dialog.md
│   ├── Navigation.md
│   ├── Feedback.md
│   ├── Radio.md
│   ├── Checkbox.md
│   ├── Stepper.md
│   ├── Switch.md
│   ├── Upload.md
│   ├── Card.md
│   ├── Title.md
│   ├── Tag.md
│   ├── Pagination.md
│   ├── Timeline.md
│   ├── OverlayTips.md
│   └── Default.md
├── Patterns/
│   ├── TablePage.md
│   ├── FormPage.md
│   ├── DetailPage.md
│   └── DashboardPage.md
└── Guidelines/
    ├── Guidelines.md
    ├── Layout.md
    ├── Naming.md
    ├── AI_Coding_Rules.md
    └── AI_Output_Checklist.md
```

> 注意：文档文件名统一使用 PascalCase，不使用空格；脚本、命令行或 AI 工具读取时应保留完整路径。

## 使用方式

不要一次性把所有文档都提供给 AI。应按任务类型加载最小必要上下文，优先加载全局规则、Token、页面模板和相关组件。

### 生成 TablePage

建议读取：

```text
Guidelines/AI_Coding_Rules.md
Guidelines/AI_Output_Checklist.md
Guidelines/Naming.md
Guidelines/Layout.md
Components/AppHeader.md
Foundations/SemanticTokens.json
Foundations/PrimitivesTokens.json
Foundations/Color.md
Foundations/Typography.md
Foundations/Spacing.md
Foundations/Grid.md
Patterns/TablePage.md
Components/Button.md
Components/Input.md
Components/SelectAndPickers.md
Components/Table.md
Components/Pagination.md
Components/Checkbox.md
Components/Tag.md
Components/OverlayTips.md
Components/Feedback.md
```

### 生成 FormPage

建议读取：

```text
Guidelines/AI_Coding_Rules.md
Guidelines/AI_Output_Checklist.md
Guidelines/Naming.md
Guidelines/Layout.md
Components/AppHeader.md
Foundations/SemanticTokens.json
Foundations/PrimitivesTokens.json
Foundations/Color.md
Foundations/Typography.md
Foundations/Spacing.md
Foundations/Grid.md
Patterns/FormPage.md
Components/Button.md
Components/Input.md
Components/SelectAndPickers.md
Components/Radio.md
Components/Checkbox.md
Components/Switch.md
Components/Stepper.md
Components/Upload.md
Components/Dialog.md
Components/Feedback.md
```

### 生成 DetailPage

建议读取：

```text
Guidelines/AI_Coding_Rules.md
Guidelines/AI_Output_Checklist.md
Guidelines/Naming.md
Guidelines/Layout.md
Components/AppHeader.md
Foundations/SemanticTokens.json
Foundations/PrimitivesTokens.json
Foundations/Color.md
Foundations/Typography.md
Foundations/Spacing.md
Foundations/Grid.md
Patterns/DetailPage.md
Components/Button.md
Components/Card.md
Components/Title.md
Components/Tag.md
Components/Table.md
Components/Timeline.md
Components/Dialog.md
Components/Feedback.md
```

### 生成 DashboardPage

建议读取：

```text
Guidelines/AI_Coding_Rules.md
Guidelines/AI_Output_Checklist.md
Guidelines/Naming.md
Guidelines/Layout.md
Components/AppHeader.md
Foundations/SemanticTokens.json
Foundations/PrimitivesTokens.json
Foundations/Color.md
Foundations/Typography.md
Foundations/Spacing.md
Foundations/Grid.md
Patterns/DashboardPage.md
Components/Card.md
Components/Title.md
Components/Table.md
Components/Tag.md
Components/SelectAndPickers.md
Components/OverlayTips.md
Components/Feedback.md
```

## 核心规则

1. 页面必须优先匹配 `Patterns/` 中的页面模板。
2. 组件必须优先使用 `Components/` 中的系统组件规范。
3. 颜色必须优先使用 Semantic Token，其次 Primitive Token，禁止自定义色值。
4. 间距、圆角、尺寸、字号、行高、阴影必须来自 Figma 或 Token；未确认写 `待定`。
5. 禁止新增未在 Figma 出现的组件、状态、尺寸、颜色、圆角和阴影。
6. 禁止生成营销页、官网页、活动页、装饰型数据大屏。
7. 禁止用 `div` / `span` 模拟 Button、Input、Select、Table、Dialog 等基础组件。
8. 表格、表单、详情、图表必须覆盖适用的 loading / empty / error 状态。
9. 危险操作必须使用危险按钮和确认弹窗。
10. 文档中保留 Figma 原始命名；如需代码 alias，应在组件文档中单独说明。

## 命名约束

- Figma 组件名、变体名按原始名称书写。
- 文件名使用组件或页面模板英文名。
- Token 名称不得自行翻译或重命名。
- Figma 中存在拼写问题的名称仍保留原名，并在前端适配中说明 alias。
- CSS class 前缀应按项目配置，不得固定绑定单一业务系统。

## AI 输出自检

AI 生成代码或页面前后必须检查：

- 是否使用了系统组件。
- 是否使用了 Token。
- 是否存在硬编码颜色。
- 是否伪造了未确认的尺寸、圆角、阴影。
- 是否遗漏 loading / empty / error。
- 是否违反页面模板结构。
- 是否出现营销式布局或装饰性视觉。
- 是否重复创建已有组件。

## 组件文档固定结构

新增或重写组件文档时必须使用以下一级小节：

1. 使用场景
2. 允许变体
3. 尺寸与视觉
4. 状态
5. 交互规则
6. 前端适配
7. 禁止事项
8. AI 生成约束

## 维护规则

- 修改 Token 相关文档前必须核对 JSON 源文件。
- 无法确认的内容统一写 `待定`。
- 不要为了让文档完整而补写 Figma 中不存在的组件或状态。
