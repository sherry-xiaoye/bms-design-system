# Spacing

间距、圆角和尺寸 Token。

## 已确认节奏

Figma 中存在 4px 基础节奏。

## Primitive Spacing Tokens

### Spacing 间距

| Token | Value | 用途 |
|---|---:|---|
| `Spacing/0` | `0` | 无间距 |
| `Spacing/1` | `4` | 最小间距 |
| `Spacing/2` | `8` | 小间距，常用于图标与文字、按钮组间距 |
| `Spacing/3` | `12` | 中小间距，具体用途待定 |
| `Spacing/4` | `16` | 常规内容间距 |
| `Spacing/5` | `20` | 页面内容内边距、区域间距 |
| `Spacing/6` | `24` | 大间距，常用于表单区块间距 |
| `Spacing/7` | `28` | 具体用途待定 |
| `Spacing/8` | `32` | 大区块间距，具体用途待定 |
| `Spacing/9` | `36` | 具体用途待定 |
| `Spacing/10` | `40` | 最大基础间距，具体用途待定 |

---

## Primitive Radius Tokens

### Radius 圆角

| Token | Value | 用途 |
|---|---:|---|
| `Radius/0` | `0` | 无圆角 |
| `Radius/1` | `4` | 最小圆角 |
| `Radius/2` | `8` | 表单、卡片小圆角 |
| `Radius/3` | `12` | 大卡片圆角 |
| `Radius/4` | `16` | 更大圆角，具体用途待定 |

---

## Semantic Radius Tokens

### Radius 语义圆角

| Token | Value | 来源 | 用途 |
|---|---:|---|---|
| `Radius/Card Larger` | `12` | `Radius/3` | 大卡片圆角 |
| `Radius/Card Small` | `8` | `Radius/2` | 小卡片圆角 |
| `Radius/Form` | `8` | `Radius/2` | 表单控件圆角 |
| `Radius/Smallest` | `4` | `Radius/1` | 最小圆角，用于小型控件或紧凑元素 |

---

## Primitive Size Tokens

### Size 尺寸

| Token | Value | 用途 |
|---|---:|---|
| `Size/0` | `0` | 无尺寸 |
| `Size/1` | `4` | 具体用途待定 |
| `Size/2` | `8` | 具体用途待定 |
| `Size/3` | `12` | 小图标 / 紧凑尺寸，具体用途待定 |
| `Size/4` | `16` | 常用图标尺寸 |
| `Size/5` | `20` | 具体用途待定 |
| `Size/6` | `24` | 常用图标 / 控件尺寸 |
| `Size/7` | `28` | 具体用途待定 |
| `Size/8` | `32` | 中型控件尺寸 |
| `Size/9` | `36` | 按钮高度等场景，具体用途待定 |
| `Size/10` | `40` | 大型控件尺寸 |
| `Size/11` | `44` | 具体用途待定 |
| `Size/12` | `48` | 大图标 / 大控件尺寸 |

---

## Semantic Size Tokens

### Size 语义尺寸

| Token | Value | 来源 | 用途 |
|---|---:|---|---|
| `Size/8*8` | `8` | `Size/2` | 8 x 8 尺寸 |
| `Size/12*12` | `12` | `Size/3` | 12 x 12 尺寸 |
| `Size/16*16` | `16` | `Size/4` | 16 x 16 图标 / 控件尺寸 |
| `Size/24*24` | `24` | `Size/6` | 24 x 24 图标 / 控件尺寸 |
| `Size/32*32` | `32` | `Size/8` | 32 x 32 图标 / 控件尺寸 |
| `Size/48*48` | `48` | `Size/12` | 48 x 48 图标 / 控件尺寸 |

---

## 使用约束

- 间距必须优先使用 `Spacing/*` Token。
- 圆角必须优先使用 Semantic Radius Token，其次使用 Primitive Radius Token。
- 表单控件圆角使用 `Radius/Form`。
- 卡片圆角根据组件语义使用 `Radius/Card Small` 或 `Radius/Card Larger`。
- 小型控件或紧凑元素使用 `Radius/Smallest`。
- 图标和固定宽高元素优先使用 Semantic Size Token。
- 禁止使用未确认的间距值，例如 `5px`、`7px`、`13px`、`18px`。
- 禁止为单个页面临时新增 spacing / radius / size Token。
- 禁止把未确认的阴影、圆角或尺寸写成系统 Token。