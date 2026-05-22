# AppHeader

## 使用场景

用于管理端或业务系统的顶部全局导航壳，承载品牌 Logo、面包屑、顶部导航、全局工具、组织选择和用户入口。

`AppHeader` 与 `Sidebar-Left`、`Body` 共同组成标准页面布局。页面级业务操作不得放入 `AppHeader`，应根据页面类型放入对应 Pattern 的标题区、筛选区、工具区或操作区。

## 允许变体

- Figma 组件：`AppHeader`
- Figma 节点：`2275:4235`
- 当前节点尺寸：`1440px × 56px`
- 实际实现：宽度随应用壳横向填充，高度固定为 `56px`
- 内部结构：`Logo Area`、`Breadcrumb`、`Top Navigation`、`Global Tools`、`Organization Selector`、`User Entry`
- 当前 Figma 节点未确认独立 Variant 属性；不得自行新增 `AppHeader` 变体
- 面包屑、图标按钮、组织选择、用户入口的状态以各自组件文档或 Figma 状态为准

## 尺寸与视觉

| 区域 | 规范 | Token / 来源 |
|---|---|---|
| 整体高度 | `56px` | Figma `AppHeader` |
| 整体背景 | 顶部导航背景 | `Background/Top Navigation` |
| 底部分割线 | `1px` | `Border/Disabled` |
| Logo 区宽度 | `180px` | Figma `AppHeader` |
| Logo 区高度 | `56px` | Figma `AppHeader` |
| Logo 区右分割线 | `1px` | `Border/Disabled` |
| Logo 资源 | 使用 Figma 中的品牌 Logo 资源 | Figma |
| 主内容高度 | `56px` | Figma `AppHeader` |
| 主内容横向间距 | `Spacing/4` | Figma MCP |
| 顶部导航项高度 | `50px` | Figma `AppHeader` |
| 顶部导航项间距 | `Spacing/5` | Figma MCP |
| 右侧工具区内边距 | 左右 `Spacing/5` | Figma MCP |
| 右侧工具区间距 | `Spacing/4` | Figma MCP |
| 图标按钮尺寸 | `30px × 30px` | Figma `AppHeader` |
| 图标按钮圆角 | `6px` | Figma `AppHeader` |
| 搜索 / 通知图标 | `16px × 16px` | Figma `AppHeader` |
| 通知红点尺寸 | `6px × 6px` | Figma `AppHeader` |
| 通知红点颜色 | `待定` | Figma 显示色值，未确认 Token |
| 组织选择器尺寸 | `113px × 32px` | Figma `AppHeader` |
| 组织选择器圆角 | `6px` | Figma `AppHeader` |
| 组织选择器边框 | `1px` | `Border/Default` |
| 用户入口尺寸 | `78px × 32px` | Figma `AppHeader` |
| 用户头像尺寸 | `28px × 28px` | Figma `AppHeader` |

文字规范：

| 文本 | 字体样式 | 颜色 |
|---|---|---|
| 面包屑上级页面 | `Body/次文本`，`14px / 20px`，Regular | `Text/Secondary` |
| 面包屑当前页面 | `Heading/页面内容的标题`，`14px / 20px`，Semibold | `Text/Primary` |
| 顶部导航未选中项 | `Body/次文本`，`14px / 20px`，Regular | `待定` |
| 顶部导航选中项 | `Heading/页面内容的标题`，`14px / 20px`，Semibold | `Text/brand` |
| 组织选择器文字 | `Body/文本`，`12px / 18px`，Regular | `Text/Primary` |
| 用户名称 | `待定` | `待定` |

图标规范：

- 面包屑分隔图标使用 `Icon/Menu-Unfold-1st`，尺寸使用 `Size/12*12`，颜色使用 `Icon/Thirdly`。
- 搜索图标、通知图标、组织选择器箭头、顶部导航关闭图标均使用 Figma 中已确认图标。
- 未在 Token 中确认的图标颜色写 `待定`，不得硬编码 Figma 导出色值。

## 状态

- default：展示 Logo、面包屑、顶部导航、右侧工具、组织选择器和用户入口。
- hover：仅可点击的导航项、图标按钮、组织选择器、用户入口响应 hover；样式以 Figma 已确认状态为准，未确认写 `待定`。
- active / focus：当前顶部导航项使用 active 样式；键盘聚焦样式未确认写 `待定`。
- blur：可聚焦控件失焦后恢复 default；`AppHeader` 容器本身不定义 blur 状态。
- disabled：`AppHeader` 容器不定义 disabled；内部控件如需禁用，以对应组件状态为准。
- error：不适用。
- loading：不适用；如搜索、通知或组织切换存在异步加载，加载反馈由对应下拉层或页面反馈组件承载。

## 交互规则

- Logo 区可作为返回首页或系统首页入口；具体跳转目标由业务系统确认。
- Breadcrumb 用于展示当前位置层级；上级页面可点击，当前页面不触发跳转。
- 顶部导航用于一级或常用模块切换；同一组内只能存在一个 active 项。
- Figma 中出现的顶部导航关闭图标仅作为已确认图标能力使用；关闭行为规则为 `待定`。
- 搜索图标点击后触发全局搜索入口；搜索面板样式和结果规则为 `待定`。
- 通知图标点击后打开消息 / 通知入口；红点表示存在未读内容。
- 组织选择器点击后打开组织切换下拉层；下拉层组件和选项规则为 `待定`。
- 用户入口点击后打开用户菜单；菜单项、退出登录、账号设置等内容为 `待定`。
- `AppHeader` 不承载页面级新建、导入、导出、批量处理、筛选等业务操作。

## 前端适配

建议代码组件名：

```tsx
<AppHeader />
```

建议 Props 映射：

| Prop | 说明 |
|---|---|
| `logo` | Figma 确认的品牌 Logo 资源 |
| `breadcrumbItems` | 面包屑层级数据 |
| `navItems` | 顶部导航项数据 |
| `activeNavKey` | 当前激活导航项 |
| `tools` | 右侧全局工具配置 |
| `organization` | 当前组织信息 |
| `user` | 当前用户信息 |
| `unread` | 是否展示通知红点 |
| `onSearch` | 点击搜索图标 |
| `onNotificationClick` | 点击通知图标 |
| `onOrganizationChange` | 切换组织 |
| `onUserMenuOpen` | 打开用户菜单 |

实现规则：

- `height` 固定映射为 `56px`。
- Logo 区宽度固定映射为 `180px`，需与 `Sidebar-Left` 宽度一致。
- 页面壳结构应保持 `AppHeader + Sidebar-Left + Body`。
- Breadcrumb 必须复用 `Navigation.md` 中的 `Breadcrumb` 规范。
- 颜色必须优先使用 Semantic Token；未确认 Token 的样式写 `待定`，不得直接落硬编码色值。
- Tailwind / CSS class 仅作为实现层命名，不得替代 Figma Token 名称。

## 禁止事项

- 禁止将 `AppHeader` 改造成营销页顶部导航。
- 禁止在 `AppHeader` 中放置页面级筛选、表格工具、批量操作或表单提交按钮。
- 禁止修改已确认的顶部高度 `56px` 和 Logo 区宽度 `180px`。
- 禁止新增 Figma 未确认的 AppHeader Variant。
- 禁止多个顶部导航项同时 active。
- 禁止使用自定义色值替代 `Background/Top Navigation`、`Border/Disabled`、`Text/brand` 等已确认 Token。
- 禁止在未确认的情况下新增阴影、渐变、背景图或装饰图形。

## AI 生成约束

- 生成管理端或业务系统页面时，默认使用 `AppHeader + Sidebar-Left + Body` 的页面壳。
- 必须使用 Figma 已确认的 `AppHeader` 结构、尺寸和 Token。
- 必须复用 `Breadcrumb`、图标、组织选择器、用户入口等已确认结构。
- 未确认的搜索面板、通知面板、组织下拉和用户菜单内容必须写 `待定`，不得自行补充交互和样式。
- 禁止新增未在 Figma 出现的尺寸、颜色、状态、圆角、阴影和导航结构。
