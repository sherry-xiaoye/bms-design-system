# Color

## 使用原则

- 业务组件优先使用 Semantic Token。
- Primitive Token 主要用于主题定义、图表色板或解释语义 Token 来源。
- 禁止在业务代码中直接写自定义色值。
- 禁止新增未在 Figma Token 中出现的颜色。
- Token 名称必须保留 Figma 原始命名，包括拼写和空格。

---

## Primitive Tokens

### Blue 蓝色

| Token | Value | 用途 |
|---|---:|---|
| `Color/Blue/Blue-B1` | `#EEF5FF` | 信息弱背景、品牌浅色背景 |
| `Color/Blue/Blue-B2` | `#B0C7FF` | 品牌浅色边框 / 填充，具体用途待定 |
| `Color/Blue/Blue-B3` | `#6E98FF` | 品牌 hover 色，具体用途待定 |
| `Color/Blue/Blue-B4` | `#3D71FF` | 品牌主色、激活色、主按钮背景 |
| `Color/Blue/Blue-B5` | `#2460F5` | 深品牌色，具体用途待定 |

### Yellow 黄色

| Token | Value | 用途 |
|---|---:|---|
| `Color/Yellow/Yellow-Y1` | `#FFF5E3` | 警告弱背景 |
| `Color/Yellow/Yellow-Y2` | `#FACF90` | 警告边框，具体用途待定 |
| `Color/Yellow/Yellow-Y3` | `#FAAA48` | 警告 hover 色，具体用途待定 |
| `Color/Yellow/Yellow-Y4` | `#F69825` | 警告文本、警告图标 |
| `Color/Yellow/Yellow-Y5` | `#EA8E1D` | 警告 active 色，具体用途待定 |

### Green 绿色

| Token | Value | 用途 |
|---|---:|---|
| `Color/Green/Green-G1` | `#E8FAF4` | 成功弱背景 |
| `Color/Green/Green-G2` | `#97E0CF` | `Icon/Select-Disabled` 来源 |
| `Color/Green/Green-G3` | `#4FC5A8` | 成功 hover 色，具体用途待定 |
| `Color/Green/Green-G4` | `#0FBB82` | 成功文本、成功图标 |
| `Color/Green/Green-G5` | `#1F967C` | 成功 active 色，具体用途待定 |

### Red 红色

| Token | Value | 用途 |
|---|---:|---|
| `Color/Red/Red-R1` | `#FFEEEE` | 错误弱背景 |
| `Color/Red/Red-R2` | `#FFB4B4` | 错误边框，Input报错 |
| `Color/Red/Red-R3` | `#FC8B8B` | 错误 hover 色，具体用途待定 |
| `Color/Red/Red-R4` | `#F96C6C` | 错误文本、危险图标、危险语义 |
| `Color/Red/Red-R5` | `#E95454` | 错误 active 色，具体用途待定 |

### Middle 中性色

| Token | Value | 用途 |
|---|---:|---|
| `Color/Middle/Middle-N1` | `#F7F8F9` | 页面弱背景、斑马纹背景 |
| `Color/Middle/Middle-N2` | `#F2F2F3` | 侧边栏、表头背景、顶部导航背景、图表坐标轴 |
| `Color/Middle/Middle-N3` | `#EDEDEF` | 弱分割线，具体用途待定 |
| `Color/Middle/Middle-N4` | `#E1E2E5` | 表格线、分割线、禁用边框 |
| `Color/Middle/Middle-N5` | `#C0C1C6` | 禁用填充、三级文本、禁用图标 |
| `Color/Middle/Middle-N6` | `#A0A1A2` | 次级文本、禁用文本、hover 边框 |
| `Color/Middle/Middle-N7` | `#666666` | 表头文本 |
| `Color/Middle/Middle-N8` | `#303133` | 主文本、主图标 |

### White 白色

| Token | Value | 用途 |
|---|---:|---|
| `Color/White/White` | `#FFFFFF` | 默认内容背景、反白文本 |
| `Color/White/White80%` | `#FFFFFF`, alpha 80% / CSS `#ffffffcc` | 半透明浮层、图表 Tooltip 背景 |

### Purple 紫色

| Token | Value | 用途 |
|---|---:|---|
| `Color/Purple/Purple-P4` | `#907AFD` | 图表紫色系列 |

### Orange 橙色

| Token | Value | 用途 |
|---|---:|---|
| `Color/Orange/Orange- O1` | `#FFEFE2` | 图表橙色弱背景 |
| `Color/Orange/Orange-O4` | `#FF955F` | 图表橙色主色 |

---

## Semantic Tokens

### Background 背景色

| Token | Value | 来源 |
|---|---:|---|
| `Background/Default` | `#FFFFFF` | `Color/White/White` |
| `Background/Disabled Filled` | `#C0C1C6` | `Color/Middle/Middle-N5` |
| `Background/Brand` | `#3D71FF` | `Color/Blue/Blue-B4` |
| `Background/Sidebar` | `#F2F2F3` | `Color/Middle/Middle-N2` |
| `Background/TableHeader` | `#F2F2F3` | `Color/Middle/Middle-N2` |
| `Background/Top Navigation` | `#F2F2F3` | `Color/Middle/Middle-N2` |
| `Background/Disabled Subtle` | `#F7F8F9` | `Color/Middle/Middle-N1` |
| `Background/zebra` | `#F7F8F9` | `Color/Middle/Middle-N1` |
| `Background/Info` | `#EEF5FF` | `Color/Blue/Blue-B1` |
| `Background/Success` | `#E8FAF4` | `Color/Green/Green-G1` |
| `Background/Warning` | `#FFF5E3` | `Color/Yellow/Yellow-Y1` |
| `Background/Error` | `#FFEEEE` | `Color/Red/Red-R1` |

### Text 文本色

| Token | Value | 来源 |
|---|---:|---|
| `Text/Primary` | `#303133` | `Color/Middle/Middle-N8` |
| `Text/Secondary` | `#A0A1A2` | `Color/Middle/Middle-N6` |
| `Text/Disabled` | `#A0A1A2` | `Color/Middle/Middle-N6` |
| `Text/Thirdly` | `#C0C1C6` | `Color/Middle/Middle-N5` |
| `Text/Inverse` | `#FFFFFF` | `Color/White/White` |
| `Text/brand` | `#3D71FF` | `{Background.Brand}` |
| `Text/TableHeader` | `#666666` | `Color/Middle/Middle-N7` |
| `Text/Warning` | `#F69825` | `Color/Yellow/Yellow-Y4` |
| `Text/Success` | `#0FBB82` | `Color/Green/Green-G4` |
| `Text/Error` | `#F96C6C` | `Color/Red/Red-R4` |

### Border 边框色

| Token | Value | 来源 |
|---|---:|---|
| `Border/Default` | `#C0C1C6` | `Color/Middle/Middle-N5` |
| `Border/Hover` | `#A0A1A2` | `Color/Middle/Middle-N6` |
| `Border/Active` | `#A0A1A2` | `Color/Middle/Middle-N6` |
| `Border/Blur` | `#C0C1C6` | `Color/Middle/Middle-N5` |
| `Border/Disabled` | `#E1E2E5` | `Color/Middle/Middle-N4` |
| `Border/Error` | `#FFB4B4` | `Color/Red/Red-R2` |
| `Border/Table` | `#E1E2E5` | `Color/Middle/Middle-N4` |
| `Border/Chart Axis` | `#F2F2F3` | `Color/Middle/Middle-N2` |

### Divider 分割线

| Token | Value | 来源 |
|---|---:|---|
| `Divider/Default` | `#E1E2E5` | `Color/Middle/Middle-N4` |

### Icon 图标色

| Token | Value | 来源 |
|---|---:|---|
| `Icon/Primary` | `#303133` | `Color/Middle/Middle-N8` |
| `Icon/Secondary` | `#A0A1A2` | `Color/Middle/Middle-N6` |
| `Icon/Disabled` | `#C0C1C6` | `Color/Middle/Middle-N5` |
| `Icon/Thirdly` | `#C0C1C6` | `Color/Middle/Middle-N5` |
| `Icon/Inverse` | `#FFFFFF` | `Color/White/White` |
| `Icon/Brand` | `#3D71FF` | `Color/Blue/Blue-B4` |
| `Icon/Danger` | `#F96C6C` | `Color/Red/Red-R4` |
| `Icon/Success` | `#0FBB82` | `Color/Green/Green-G4` |
| `Icon/Warning` | `#F69825` | `Color/Yellow/Yellow-Y4` |
| `Icon/Select-Disabled` | `#97E0CF` | `Color/Green/Green-G2` |

### Charts 图表色

| Token | Value | 来源 |
|---|---:|---|
| `Charts/Dark B` | `#3D71FF` | `Color/Blue/Blue-B4` |
| `Charts/Light B` | `#EEF5FF` | `Color/Blue/Blue-B1` |
| `Charts/Dark O` | `#FF955F` | `Color/Orange/Orange-O4` |
| `Charts/Light O` | `#FFEFE2` | `Color/Orange/Orange- O1` |
| `Charts/Dark P` | `#907AFD` | `Color/Purple/Purple-P4` |
| `Charts/Backgroung` | `#E1E2E5` | `Color/Middle/Middle-N4` |
| `Charts/TooltipBackground` | `#FFFFFF`, alpha 80% / CSS `#ffffffcc` | `Color/White/White80%` |

---

## 使用约束

- 业务 UI 必须优先使用 Semantic Token，不直接使用 Primitive Token。
- 页面背景使用 `Background/Disabled Subtle` 或业务确认的背景 Token，不得自定义浅灰。
- 内容容器背景使用 `Background/Default`。
- 主按钮、激活态、品牌强调使用 `Background/Brand` 或 `Text/brand`。
- 表格表头背景使用 `Background/TableHeader`。
- 表格线使用 `Border/Table`。
- 主文本使用 `Text/Primary`。
- 次级说明使用 `Text/Secondary`。
- 禁用文本使用 `Text/Disabled`。
- 表头文本使用 `Text/TableHeader`。
- 成功、警告、错误状态必须分别使用对应的 `Success`、`Warning`、`Error` 语义 Token。
- 图标颜色必须使用 `Icon/*` Token。
- 图表颜色必须使用 `Charts/*` Token。
- 禁止使用 Figma Token 之外的颜色值。
- 禁止修改 Token 名称中的大小写、空格和拼写，例如 `Color/Orange/Orange- O1`、`Charts/Backgroung` 必须保持原名。
```