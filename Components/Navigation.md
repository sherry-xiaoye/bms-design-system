# Navigation

## 使用场景

用于系统导航、层级定位和流程步骤展示。

## 允许变体

- 以 Figma 中已确认的组件属性和 Variant 为准。

## 尺寸与视觉

- 组件：`Breadcrumb`, `Breadcrumb-Item`, `Menu-Item`, `Step-Item`, `AppHeader`, `Sidebar-Left`
- `AppHeader` 独立规范见 `Components/AppHeader.md`
- Menu Props：`Style`, `State`, `Icon`
- Step Props：`State`, `Type`, `Last`
- Header 高度：`56px`
- Sidebar 宽度：`180px`
- 菜单颜色使用 `Background/Sidebar`, `Text/Primary`, `Icon/Default`, `Text/brand`

## 状态

- default：默认导航项。
- hover：悬浮导航项。
- active / focus：当前导航项。
- blur：`待定`。
- disabled：`待定`。
- error / loading：不适用。

### default 默认状态
- 用于展示当前页面所在的层级路径。
- 非当前层级文本使用 `Text/Secondary`，字体使用 `Body/次文本`。
- 当前页面文本使用 `Text/Primary`，字体使用 `Heading/页面内容的标题`。
- 分隔符使用箭头图标 `Icon/Menu-Unfold-1st`，图标尺寸使用 `Size/12*12`，颜色 Token 为 `Icon/Thirdly`。
- 支持层级：Level 1 / Level 2 / Level 3 / Level 4。
- 面包屑项可通过 `to` 配置跳转目标。

### hover 悬浮状态
- 仅可点击的上级页面支持 hover 状态。
- hover 时，上级页面文本颜色切换为 `Text/brand`。
- 当前页面不响应 hover，不展示可点击样式。
- 分隔符 hover 样式：图标不变。

### active 激活状态
- 当前页面为激活项，使用 `Text/brand` 和 `Heading/页面内容的标题`。
- 当前页面仅用于标识当前位置，不触发跳转。

#### blur 失焦状态
- 失焦后恢复为 default 默认状态。

## 交互规则

- Breadcrumb 只用于位置层级，不作为主导航。
- Sidebar 用于模块导航。
- Step 用于多步骤创建或审批流程。
- 同一导航组内只能存在一个 active。


业务场景示例：

- 场景 1：【设备管理】中的【左侧模块导航】。
- 场景 2：【新建流程】中的【步骤条】。

## 前端适配

- `Menu-Item.Style` 映射一级 / 二级 / 三级菜单。
- `Menu-Item.Icon` 映射是否显示图标。
- `Step-Item.State` 映射 `Finish | Process | Wait`。
- `AppHeader` 映射顶部全局导航壳；高度、Logo 区、右侧工具和用户入口规则以 `Components/AppHeader.md` 为准。

## 禁止事项

- 禁止使用 Figma 未确认的组件、状态、尺寸、颜色、圆角和阴影。
- 禁止自定义 Token 或硬编码未经确认的样式。

## AI 生成约束

- 必须保留 Header + Sidebar + Body 壳结构。
- 禁止将管理端页面改成顶部营销导航。
- 禁止多个菜单项同时 active。
