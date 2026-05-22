# Feedback

## 反馈选择规则

| 反馈类型 | 使用场景 | 持续时间 | 是否阻断操作 | 典型位置 | 适用组件 |
| --- | --- | --- | --- | --- | --- |
| 页面内提示 | 页面局部需要持续展示的提示、警告、说明 | 持续展示，用户可关闭或随页面消失 | 否 | 内容区顶部 / 表单区顶部 | Alert |
| 全局通知 | 异步任务、系统事件、跨页面状态通知 | 短暂或手动关闭 | 否 | 页面右上角 | Notification |
| 即时轻提示 | 用户完成点击、保存、删除等操作后的即时反馈 | 短暂自动消失 | 否 | 页面顶部或居中浮层 | Toast |
| 加载反馈 | 页面、区域、按钮、数据请求加载中 | 请求结束后消失 | 视场景而定 | 页面 / 区块 / 按钮内部 | Loading |
| 进度反馈 | 上传、导入、批处理等可量化过程 | 任务结束后消失或保留结果 | 否 | 任务区域 / 弹窗 / 表格行 | Progress |
| 空状态 | 列表、表格、搜索结果无数据 | 持续展示 | 否 | 内容区域 | Default-Image / Empty |
| 结果反馈 | 提交完成、审批完成、支付结果、流程结束 | 持续展示 | 可引导下一步 | 独立结果页 / 弹窗结果区 | Result |
| 异常页面 | 404、无权限、系统错误、网络异常 | 持续展示 | 是 | 整页 | Default-Image / Result |

## 使用优先级

- 用户完成一个轻量操作后，只需要短提示，使用 `Toast`。
- 当前页面需要持续展示一段提示或风险说明，使用  `Alert`。
- 操作结果来自异步任务，且用户可能已经离开当前上下文，使用 `Notification`。
- 用户正在等待数据或处理结果，使用 `Loading`。
- 任务可以量化进度，使用 `Progress`。
- 列表、搜索、页面内容为空或不可访问，使用 `Default-Image / Empty`。
- 流程已经结束并需要承接下一步动作，使用 `Result`。

## 组件规范

## Alert

### 使用场景

用于页面内展示持续性提示、警告或说明信息，通常出现在内容区或表单区顶部。

### 允许变体

- 以 Figma 中已确认的组件属性和 Variant 为准。

### 尺寸与视觉
- Alert 支持以下信息类型：
  - `Info`：常规提示，背景使用 `Background/Info`,图标使用 `Icon/InfoFilled`, `Icon/Brand`
  - `Warning`：预警提示，背景使用 `Background/Warning`,图标使用 `Icon/InfoFilled`, `Icon/Warning`
  - `Success`：成功提示，背景使用 `Background/Success`,图标使用 `Icon/Success`, `Icon/Success`
  - `Error`：失败提示，背景使用 `Background/Error`,图标使用 `Icon/CircleCloseFilled`, `Icon/Danger`
- 文案颜色使用 `Text/Primary`。
- 文案字体使用 `Body/文本`。
- 图标尺寸使用 `Size/16*16`。
- 容器高度使用 `36`。
- 圆角使用 `Radius/Card Small`。

### 状态

- info：默认提示。
- success：操作成功提示。
- warning：警告提示。
- error：操作失败提示。

### 交互规则

- 可支持关闭。
- 可支持文本链接或按钮操作。
- 不自动消失，除非业务主动移除。

### 前端适配
- `type` 映射 `Info | Success | Warning | Error`。
- `closable` 控制是否显示关闭按钮。
- 操作项支持 `link` 或 `button`，具体字段待定。

### 禁止事项

- 禁止使用 Figma 未确认的组件、状态、尺寸、颜色、圆角和阴影。
- 禁止自定义 Token 或硬编码未经确认的样式。

### AI 生成约束
- 禁止用 Toast 替代需要持续阅读的 Alert。
- 禁止自定义 Alert 颜色。

## Toast

### 使用场景
用于用户操作后的即时轻反馈，反馈内容短，自动消失。

### 允许变体

- 以 Figma 中已确认的组件属性和 Variant 为准。

### 尺寸与视觉
- Toast 支持以下信息类型：
  - `Warning`：预警提示，图标使用 `Icon/InfoFilled`, `Icon/Warning`,背景颜色：`Background/Warning`,字体 `Text/Warning`,`Body/次文本`
  - `Success`：成功提示，图标使用 `Icon/Success`, `Icon/Success`,背景颜色：`Background/Success`,字体 `Text/Success`,`Body/次文本`
  - `Error`：失败提示，图标使用 `Icon/CircleCloseFilled`, `Icon/Danger`,背景颜色：`Background/Error`,字体 `Text/Error`,`Body/次文本`
- 图标尺寸使用 `Size/16*16`。
- 圆角使用 `Radius/Card Small`。

### 状态
- success：操作成功提示。
- warning：警告提示。
- error：操作失败提示。

### 交互规则
- 自动消失。
- 不承载复杂操作。
- 不用于长文本说明。
- 同一时间多条 Toast 的堆叠规则：按照先后顺序平铺展示，不准重叠在一起。

业务场景示例：
- 保存成功。
- 删除失败。
- 复制成功。

### 前端适配
- `type` 映射 `Success | Warning | Error`。
- `duration` 控制显示时长，默认值5s。
- `message` 显示提示内容。

### 禁止事项

- 禁止使用 Figma 未确认的组件、状态、尺寸、颜色、圆角和阴影。
- 禁止自定义 Token 或硬编码未经确认的样式。

### AI 生成约束
- 禁止用 Toast 展示需要用户长期阅读的信息。
- 禁止在 Toast 中放复杂表单、按钮组或长说明。



## Notification


### 使用场景
用于展示全局层级的通知提醒，适合异步任务、系统事件、跨页面状态变化等与当前页面无强绑定关系的反馈。
常见于：
- 异步任务处理完成或失败。
- 系统消息、审批消息、权限变更提醒。
- 用户离开当前操作上下文后仍需要感知的结果通知。

### 允许变体

- 以 Figma 中已确认的组件属性和 Variant 为准。

### 尺寸与视觉
- Notification 支持以下信息类型：
  - `Info`：常规提示，图标使用 `Icon/InfoFilled`, `Icon/Brand`
  - `Warning`：预警提示，图标使用 `Icon/InfoFilled`, `Icon/Warning`
  - `Success`：成功提示，图标使用 `Icon/Success`, `Icon/Success`
  - `Error`：失败提示，图标使用 `Icon/CircleCloseFilled`, `Icon/Danger`
- 支持以下右侧操作形式：
  - `Icon`：右侧关闭图标
- 内容字体： `Text/Primary`,`Body/主页面和弹窗标题`。
- 标题字体： `Text/Primary`,`Body/文本`。
- 图标尺寸使用 `Size/16*16`。
- 圆角使用 `Radius/Card Small`。
- 背景颜色：`Background/Default`

### 状态
- info：常规通知，用于中性系统消息。
- success：成功通知，用于异步任务完成、提交成功等结果。
- warning：警告通知，用于风险提醒、待处理事项、非阻断异常。
- error：错误通知，用于异步任务失败、系统异常等结果。

### 交互规则
- Notification 不阻断用户当前操作。
- 手动关闭。
- 可包含标题、描述文本、关闭按钮。
- 多条 Notification 同时出现时，按照出现的时间先后顺序平铺展示，不准重叠在一起。
- 错误类 Notification 必须说明失败原因或提供可理解的下一步处理方式。
- 不应用 Notification 展示页面内必须持续阅读的说明，此类场景应使用 Alert。

业务场景示例：
- 场景 1：【批量导入】中的【导入完成 / 导入失败通知】。
- 场景 2：【审批流程】中的【审批结果通知】。
- 场景 3：【系统消息】中的【权限变更 / 任务完成提醒】。

### 前端适配
- `type` 映射 `Info | Success | Warning | Error`。
- `title` 显示通知标题。
- `message` / `description` 显示通知正文。
- `closable` 控制是否显示关闭按钮。
- `onClose` 映射关闭回调。
- 操作项字段映射规则：待定。
- 接口字段映射规则：待定。

### 禁止事项

- 禁止使用 Figma 未确认的组件、状态、尺寸、颜色、圆角和阴影。
- 禁止自定义 Token 或硬编码未经确认的样式。

### AI 生成约束
- 禁止用 Notification 替代页面内需要持续展示的 Alert。
- 禁止用 Notification 替代操作后的轻量 Toast。
- 禁止连续生成大量 Notification 干扰用户操作。
- 禁止在 Notification 中放复杂表单、表格或多步骤操作。
- 错误类 Notification 必须包含可理解的错误说明；无法确认原因，不展示原因内容。
- 禁止自定义 Notification 颜色、图标、圆角、阴影。


## Loading

### 使用场景
用于页面、区块、表格、按钮或数据请求处于加载中的反馈，告知用户系统正在处理。

### 允许变体

- 以 Figma 中已确认的组件属性和 Variant 为准。

### 尺寸与视觉
- 图标：浅色背景上使用`L-Loading-blue` ,深色背景上使用`L-Loading-white` 
- 图标尺寸：`Size/32*32`。
- 字体：`Body/次文本`,`Text/brand`。

### 状态
- loading：加载中状态。
- success：不适用，加载完成后应切换为内容展示或结果反馈。
- error：不适用，加载失败后应切换为 Alert / Toast / Result / Default-Image。
- disabled：不适用。
- timeout：不适用，超时后切换为 Alert / Toast / Result / Default-Image。

### 交互规则
- 请求开始时展示 Loading，请求结束后必须移除。
- 页面级 Loading 可阻断页面操作。
- 区块级 Loading 仅阻断当前区块。
- 按钮 Loading 仅阻断当前按钮重复提交。
- 长时间加载应展示可理解文案，具体时长规则待定。

业务场景示例：
- 场景 1：【列表页】中的【表格数据加载】。
- 场景 2：【表单提交】中的【提交中状态】。
- 场景 3：【详情页】中的【页面初始化加载】。

### 前端适配
- `loading` 控制是否展示加载状态。
- `fullscreen` 控制是否为页面级 Loading。
- `target` 控制 Loading 作用范围。
- `text` 控制加载文案，默认文案待定。
- 请求失败后的错误反馈组件映射规则：待定。

### 禁止事项

- 禁止使用 Figma 未确认的组件、状态、尺寸、颜色、圆角和阴影。
- 禁止自定义 Token 或硬编码未经确认的样式。

### AI 生成约束
- 异步请求必须包含 Loading 处理。
- 禁止加载时页面无反馈。
- 禁止同一区域重复叠加多个 Loading。
- 禁止用 Loading 替代可展示进度的 Progress。

## Progress

### 使用场景
用于上传、导入、批处理、任务执行等可量化过程，展示任务当前进度。

### 允许变体

- 以 Figma 中已确认的组件属性和 Variant 为准。

### 尺寸与视觉
- Toast 支持以下信息类型：
  - `Info`：常规提示，进度条填充颜色：`Background/brand`, 文字字体使用`Background/brand`,`Heading/页面内容的标题`
  - `Success`：成功提示，图标使用 `Icon/Success`, `Icon/Success`,进度条填充颜色：`Background/Success`
  - `Error`：失败提示，图标使用 `Icon/CircleCloseFilled`, `Icon/Danger`,进度条填充颜色：`Background/Error`
- 图标尺寸使用 `Size/16*16`。
- 进度条颜色：`Border/Default`。
- 尺寸：`240`。
- 形态：线性。

### 状态
- processing：任务进行中。
- success：任务完成。
- error：任务失败。
- loading：不单独使用，进行中状态使用 processing。
- disabled：不适用。

### 交互规则
- 必须展示任务状态。
- 可量化任务应展示百分比或明确进度。
- 任务失败时必须提供失败原因或重试入口。

业务场景示例：
- 场景 1：【文件上传】中的【上传进度】。
- 场景 2：【批量导入】中的【导入进度】。
- 场景 3：【异步处理】中的【任务执行进度】。

### 前端适配
- `percent` 映射当前进度百分比。
- `status` 映射 `processing | success | error`。
- `type` 映射进度条形态，具体枚举待定。
- `showText` 控制是否展示进度文本。
- `onRetry` / `action` 等失败操作字段待定。

### 禁止事项

- 禁止使用 Figma 未确认的组件、状态、尺寸、颜色、圆角和阴影。
- 禁止自定义 Token 或硬编码未经确认的样式。

### AI 生成约束
- 禁止只展示动画但无进度或状态说明。
- 可量化任务禁止只使用 Loading。
- 失败状态必须包含错误说明或处理入口。
- 禁止自定义进度颜色。

## Default-Image / Empty

### 使用场景
用于列表、表格、搜索结果、页面区块无数据时的空状态展示，也可用于无权限、错误、404 等缺省占位场景。

### 允许变体

- 以 Figma 中已确认的组件属性和 Variant 为准。

### 尺寸与视觉
- 描述文案字体：`Body/次文本`,`Text/Secondary`。
- 插图：以 Figma 已出现的 Default-Image 状态为准。
- 布局：图片、文案、按钮之间的间距使用 `16`。

### 状态
- empty：无数据。
- search-empty：无搜索结果，是否单独支持待定。
- access-denied：无权限。
- 404：页面不存在。
- error：系统错误或加载失败。
- loading：不适用，加载中应使用 Loading。

### 交互规则
- 空状态应说明当前为空的原因。
- 如用户可继续操作，应提供主要操作入口。
- 搜索无结果时可提供清空筛选、重置搜索等操作。
- 无权限状态应说明无权限原因或联系管理员方式，具体规则待定。
- 404 / Error 页面可提供返回首页、刷新、返回上一页等操作，具体规则待定。

业务场景示例：
- 场景 1：【表格页】中的【暂无数据】。
- 场景 2：【搜索结果】中的【无匹配结果】。
- 场景 3：【权限页面】中的【无访问权限】。

### 前端适配
- `state` 映射 `Empty | 404 | AccessDenied | Error`。
- `title` 显示主文案。
- `description` 显示辅助说明。
- `action` 映射操作按钮或链接。
- 空状态图片与状态的映射规则：待定。
- 接口空数据判断规则：待定。

### 禁止事项

- 禁止使用 Figma 未确认的组件、状态、尺寸、颜色、圆角和阴影。
- 禁止自定义 Token 或硬编码未经确认的样式。

### AI 生成约束
- 列表、表格、搜索结果必须考虑 empty 状态。
- 禁止用 Toast 替代空状态。
- 禁止自定义空状态插图。
- 禁止在无权限或错误状态中只展示“暂无数据”。

## Result

### 使用场景
用于提交完成、创建完成、审批完成、支付结果、流程结束等高强调结果反馈，并引导用户进行下一步操作。

### 允许变体

- 以 Figma 中已确认的组件属性和 Variant 为准。

### 尺寸与视觉
- 图标尺寸：`Size/48*48`。
- 成功图标颜色：`Icon/Success`。
- 失败图标颜色：`Icon/Danger`。
- 主文案：使用 `Text/Primary`，字体使用 `Body/次文本`。
- 按钮：复用 Button 组件规范。
- Error 错误原因区域：背景使用 `Background/Zebra`。

### 状态
- success：流程成功完成。
- error：流程失败或提交失败。

### 交互规则
- Result 不自动消失。
- Success 状态必须提供下一步操作，例如查看详情、继续创建、返回列表。
- Error 状态必须说明失败原因或提供解决办法。
- Error 状态应提供返回修改、重试或回到列表等操作。
- 按钮数量、优先级和跳转规则由业务决定，默认规则待定。

业务场景示例：
- 场景 1：【表单创建】中的【创建成功 / 提交失败】。
- 场景 2：【审批流程】中的【审批完成 / 审批失败】。
- 场景 3：【支付流程】中的【支付成功 / 支付失败】。

### 前端适配
- `state` 映射 `Success | Error`。
- `title` 显示结果主文案。
- `reasons` 显示失败原因列表。
- `actions` 映射底部操作按钮。
- `primaryAction` 映射主按钮。
- `secondaryAction` 映射次按钮。
- 错误原因、解决办法、按钮跳转的接口字段映射规则：待定。

### 禁止事项

- 禁止使用 Figma 未确认的组件、状态、尺寸、颜色、圆角和阴影。
- 禁止自定义 Token 或硬编码未经确认的样式。

### AI 生成约束
- 流程结束页必须优先使用 Result。
- Success 必须包含明确成功文案和下一步操作。
- Error 必须包含失败原因或解决入口。
- 禁止用 Alert 或 Toast 替代完整结果页。
- 禁止新增 Figma 未确认的 Result 状态。
