# Pagination

## 1.1 用途

用于列表、表格等分页数据的页码切换和每页条数选择。

## 1.2 视觉规范

- 组件：`Pagination`
- Style：
  - `Number`：`220px x 44px`
  - `Select`：`474px x 60px`
- 颜色：`Text/Primary`,`Text/Brand`,`Icon/Primary`,`Border/Default`，禁止自定义色值
- 字体：`Body/文本`
- 间距:`8`
- 圆角：`Radius/Form`
- 边框：`1`,`Border/Default`
- 图标：`Arrow-Left`,`Arrow-Right`,`Size/16*16`

## 1.3 状态规范

- default：默认分页展示
- hover：鼠标悬停时触发，文字/图标颜色变化
- active：当前页激活状态，文字/图标颜色变化
- disabled：上一页 / 下一页不可用状态



## 1.4 交互规则

- `Number` 用于标准页码分页。
- `Select` 用于带每页条数选择的分页。
- 切换页码后触发列表数据刷新。
- 每页条数变更后应刷新当前列表，页码重置规则待定。

## 1.5 业务场景示例

- 场景 1：【列表业务】中的【表格分页】
- 场景 2：【查询业务】中的【分页结果浏览】

## 1.6 前端适配点

- `style` 映射 `Number | Select`
- `current` 映射当前页
- `pageSize` 映射每页条数
- `total` 映射总数
- 组件名建议：`Pagination`

## 1.7 AI 生成约束

- 必须使用系统 `Pagination`。
- 表格页必须包含分页，除非业务明确为全量展示。
- 禁止自定义分页样式。
- 禁止新增未在 Figma 出现的尺寸、颜色、状态、圆角、阴影。
