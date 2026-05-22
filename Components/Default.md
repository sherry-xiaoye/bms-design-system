# Default-Image

## 使用场景

用于列表、表格、搜索结果、页面内容为空或不可访问时的空状态 / 异常状态展示。本文档对应 Figma 组件 `Default-Image`。

## 允许变体

- 以 Figma 中已确认的 `Default-Image` 状态为准。
- 与 `Feedback.md` 中的 `Default-Image / Empty` 规范保持一致。

## 尺寸与视觉

- 插图：使用 Figma 已确认的 `Default-Image`，禁止自绘或替换为未确认插图。
- 文本：使用已确认 Text Token 和 Text Style；未确认写 `待定`。
- 间距、尺寸、圆角、阴影：以 Figma 或 Token 为准；未确认写 `待定`。

## 状态

- empty：无数据 / 暂无内容。
- search-empty：搜索或筛选无结果，具体 Figma 状态名待定。
- access-denied：无权限，具体 Figma 状态名待定。
- error：异常页面或加载失败，具体 Figma 状态名待定。

## 交互规则

- 空状态应说明当前为空的原因。
- 如用户可继续操作，应提供主要操作入口。
- 搜索无结果时可提供清空筛选、重置搜索等操作。
- 无权限状态应说明无权限原因或联系管理员方式，具体规则待定。

## 前端适配

- 组件名建议映射为 `DefaultImage` 或项目既有 Empty 组件，必须在代码中说明与 Figma `Default-Image` 的对应关系。
- `state` 映射 `Empty | SearchEmpty | AccessDenied | Error`，具体枚举以 Figma 后续确认为准。
- `title` / `description` 映射说明文案。
- `action` 映射操作按钮或链接。

## 禁止事项

- 禁止继续将该文档理解为通用默认规则组件。
- 禁止新增 Figma 未确认的空状态插图、颜色、尺寸、圆角、阴影。
- 禁止用营销插画替代系统 Default-Image。

## AI 生成约束

- 必须优先使用系统 `Default-Image`。
- 禁止临时创建同类空状态组件。
- 颜色、尺寸、圆角、阴影必须来自 Figma 或 Token；未确认写 `待定`。
