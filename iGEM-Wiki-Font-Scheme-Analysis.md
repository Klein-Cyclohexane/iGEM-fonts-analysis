# iGEM Wiki 字体方案分析报告

---

## 一、字体使用总览

| # | Wiki | 年份 | 标题字体 | 导航栏字体 | 正文字体 | 代码字体 | 字体数量 |
|---|------|------|---------|-----------|---------|---------|---------|
| 1 | MSP Maastricht | 2025 | Oswald | 系统 UI 栈 | Inter | monospace | 2 |
| 2 | EPFL PYRONIX | 2025 | Anton + Outfit | Inter / Roboto (CSS var) | Inter + Roboto | System Mono 栈 | 4 |
| 3 | Heidelberg PACE | 2024 | Exo 2 | Exo 2 | Exo 2 | System Mono 栈 | 1 |
| 4 | JU Krakow | 2024 | Poppins | Poppins | Poppins | Bootstrap Mono 栈 | 1 |
| 5 | INSA Lyon1 FIAT LUX | 2022 | Fira Sans | Fira Sans Bold | Fira Sans | Courier | 2 |
| 6 | Patras Medicine | 2022 | Abril Fatface | Fira Sans Bold (inline) | Figtree | System Mono 栈 | 2 |
| 7 | Barcelona-UB SKIPPIT | 2025 | Inter | Inter | Inter | JetBrains Mono | 2 |
| 8 | McGill | 2025 | Onest | Onest (+ Open Sans 气泡) | Onest | Bootstrap Mono 栈 | 2 |
| 9 | Patras Med MORPHE | 2025 | Noto Serif VF | Noto Serif VF | Noto Serif VF | System Mono 栈 | 3 |
| 10 | PekingHSC | 2025 | Inter | Inter | Inter | Fira Code + System Mono | 2 |
| 11 | ShanghaiTech China | 2025 | Gilroy | Gilroy | Gilroy | System Mono (fallback) | 1 |
| 12 | ShanghaiTech China | 2023 | Arlon | AlibabaPuHuiTi | AlibabaPuHuiTi | Courier New | 2 |

---

## 二、逐站详细分析

### 1. MSP Maastricht (CoreSpin) — 2025

| 角色 | 字体 | 字重 | 加载方式 |
|------|------|------|----------|
| 标题 | **Oswald** | 700 / 500 / 400 | Google Fonts CDN |
| 导航栏 | 系统 UI 栈 (`-apple-system, BlinkMacSystemFont, Segoe UI, ...`) | 500–600 | 系统默认 |
| 正文 | **Inter** | 400 (300–700 可用) | Google Fonts CDN |
| 代码 | `monospace` | 400 | 系统默认 |

**特点**：经典的 Inter + Oswald 搭配，无衬线正文 + 紧凑无衬线标题。导航栏使用系统字体。

---

### 2. EPFL (PYRONIX) — 2025

| 角色 | 字体 | 字重 | 加载方式 |
|------|------|------|----------|
| 标题 | **Anton** + **Outfit** (Variable) | Anton 400 / Outfit 100–900 | 自托管 `.woff2` |
| 导航栏 | Inter / Roboto (通过 `var(--font-body)`) | 500 | 自托管 `.woff2` |
| 正文 | **Inter** + **Roboto** | 400 / 500 / 700 | 自托管 `.woff2` |
| 代码 | `ui-monospace, SFMono-Regular, Menlo, ...` | 400 | 系统默认 |

**特点**：最复杂的字体方案。同时加载了 5 种字体（Anton、Outfit Variable、Inter 4 级、Roboto 3 级），通过 CSS 变量管理。Anton 用于极具视觉冲击力的大标题（condensed, all-caps 风格），Outfit 作为标题辅助。Inter 和 Roboto 同时加载形成了双正文回退体系。

---

### 3. Heidelberg (PACE) — 2024

| 角色 | 字体 | 字重 | 加载方式 |
|------|------|------|----------|
| 标题 | **Exo 2** | 700–900 | 自托管 `.ttf` (18 个文件 + 2 个 Variable) |
| 导航栏 | **Exo 2** | 500 | 自托管 `.ttf` |
| 正文 | **Exo 2** | 400 | 自托管 `.ttf` |
| 代码 | `SFMono-Regular, Menlo, Monaco, Consolas, ...` | 400 | 系统默认 |

**特点**：单字体方案。18 个静态 `.ttf`（100–900 × normal + italic）+ 2 个 Variable 字体文件，总共 20 个字体文件全部是 Exo 2。所有层级——从 100 Thin 到 900 Black——完全依赖一个字体家族的字重变化来实现视觉层级。字体文件数量庞大但类型统一。

---

### 4. JU Krakow — 2024

| 角色 | 字体 | 字重 | 加载方式 |
|------|------|------|----------|
| 标题 | **Poppins** | 700 / 500 | 自托管 `.ttf` (仅 400 + 700) |
| 导航栏 | **Poppins** | 500–700 | 自托管 `.ttf` |
| 正文 | **Poppins** | 400 | 自托管 `.ttf` |
| 代码 | `SFMono-Regular, Menlo, Monaco, Consolas, ...` | 400 | Bootstrap 默认 |

**特点**：最精简的单字体方案。仅加载 2 个 `.ttf` 文件（Poppins Regular + Bold），通过覆盖 Bootstrap 5 的 `--bs-font-sans-serif` CSS 变量实现全站字体统一。HTML 中还有内联 `<style>` 显式设置 `body, h2–h6, p, a, div, span` 全部使用 Poppins。

---

### 5. INSA Lyon1 (FIAT LUX) — 2022

| 角色 | 字体 | 字重 | 加载方式 |
|------|------|------|----------|
| 标题 | **Fira Sans** | 600–700 | 系统字体 / 未明确自托管 |
| 导航栏 | **Fira Sans** Bold (x-large) | 700 | 同上 |
| 正文 | **Fira Sans** | 400 | 同上 |
| 代码 | **Courier** | 400 | 系统默认 |

**特点**：CSS 中声明了 Fira Sans 和 Fira Sans Extra Condensed，但 HTML 中未发现 Google Fonts 链接或 `@font-face` 声明，依赖系统已安装的字体。使用 `font-family: 'Fira Sans', sans-serif` 直接引用。风格简洁，但字体可用性依赖用户系统环境。Fira Sans 是 Firefox OS 的系统字体，有些 Linux 发行版预装，但对Windows/macOS 用户来说大概率会 fallback 到系统无衬线体

---

### 6. Patras Medicine — 2022

| 角色 | 字体 | 字重 | 加载方式 |
|------|------|------|----------|
| 标题 | **Abril Fatface** | 400 | 自托管 `.ttf` |
| 导航栏 | Fira Sans Bold (内联) | 700 | 系统字体 |
| 正文 | **Figtree** | 400 | 自托管 `.ttf` |
| 代码 | System Mono 栈 | 400 | 系统默认 |

**特点**：高对比度搭配——Abril Fatface（Didone 装饰衬线体，用于大标题、统计数字、手风琴标签、时间线标题）+ Figtree（现代无衬线体，用于正文和 UI）。视觉对比度高

---

### 7. Barcelona-UB (SKIPPIT) — 2025

| 角色 | 字体 | 字重 | 加载方式 |
|------|------|------|----------|
| 标题 | **Inter** (Variable) | 600–800 | 自托管 `.ttf` (Variable + Italic Variable) |
| 导航栏 | **Inter** | 500–600 | 同上 |
| 正文 | **Inter** | 400 | 同上 |
| 代码 | **JetBrains Mono** | 400 | 自托管 `.ttf` |

**特点**：极简两字体方案。Inter Variable 覆盖 100–900 全部字重（一个 normal 文件 + 一个 italic 文件），JetBrains Mono 仅加载 Regular 用于代码。CSS 变量管理：`--main-font: 'Inter', sans-serif` 和 `--code-font: 'JetBrains Mono', monospace`。
---

### 8. McGill — 2025

| 角色 | 字体 | 字重 | 加载方式 |
|------|------|------|----------|
| 标题 | **Onest** | 400–800 | 自托管 `.ttf` (Regular 400 + ExtraBold 700) |
| 导航栏 | **Onest** (药丸按钮) / **Open Sans** (气泡标签) | 500–600 | Onest 自托管 / Open Sans 系统回退 |
| 正文 | **Onest** | 400 | 自托管 `.ttf` |
| 代码 | Bootstrap Mono 栈 | 400 | Bootstrap 默认 |

**特点**：Onest 是一款较新的几何无衬线体（2023 年发布），圆润友好。McGill 使用其 Regular 和 ExtraBold 两个文件覆盖全站，气泡导航标签使用 Open Sans。

---

### 9. Patras Med (MORPHE) — 2025

| 角色 | 字体 | 字重 | 加载方式 |
|------|------|------|----------|
| 标题 | **Noto Serif VF** | 400–800 | 自托管 `.woff2` + `.ttf` (Variable + Italic) |
| 导航栏 | **Noto Serif VF** | 500 | 同上 |
| 正文 | **Noto Serif VF** | 400 | 同上 |
| Footer 标题 | **Bitter VF** | 600 | 自托管 `.ttf` (Variable + Italic) |
| 辅助 UI | **Montserrat VF** | 可变 | 自托管 `.ttf` (Variable + Italic) |
| 代码 | System Mono 栈 | 400 | 系统默认 |

**特点**：十个方案中唯一的衬线主导设计。Noto Serif VF 作为主字体（含宽度轴可变），Bitter VF 用于 Footer 标题，Montserrat VF 作为无衬线辅助。深色背景+ 珊瑚色强调

---

### 10. PekingHSC — 2025

| 角色 | 字体 | 字重 | 加载方式 |
|------|------|------|----------|
| 标题 | **Inter** | 700 | 自托管 `.woff2` (14 个文件，按 Unicode 子集) |
| 导航栏 | **Inter** | 500–600 | 同上 |
| 正文 | **Inter** | 400 | 同上 |
| 代码（行内） | **Fira Code** | 400 | 自托管 `.woff2` |
| 代码（块级） | `ui-monospace, Menlo, Monaco, Consolas, ...` | 400 | 系统默认 |
| 中文标点 | **Punctuation SC** | 400–700 | `local()` 回退链 (PingFang SC / Noto Sans CJK SC / Microsoft YaHei) |

**特点**：VitePress 默认字体方案 + 中文支持。Inter 按 7 个 Unicode 子集（Latin / Latin-ext / Cyrillic / Cyrillic-ext / Greek / Greek-ext / Vietnamese）分别加载 roman 和 italic `.woff2`，共 14 个文件。Fira Code 用于行内代码，`--vp-font-family-mono` 用于代码块。Punctuation SC 通过 `local()` 链解决中文标点问题。最工程化的方案，适合多语言文档站。

---

### 11. ShanghaiTech China (DOCTOR) — 2025

| 角色 | 字体 | 字重 | 加载方式 |
|------|------|------|----------|
| 标题 | **Gilroy** | 700–950 | 自托管 `.otf` (13 个文件) |
| 导航栏 | **Gilroy** | 500–700 | 自托管 `.otf` |
| 正文 | **Gilroy** | 400 | 自托管 `.otf` |
| 代码 | System Mono (fallback) | 400 | 系统默认 |

**特点**：单字体方案，使用了 Gilroy 这个 premium 几何无衬线体。13 个 `.otf` 文件覆盖了 100–950 的极宽字重范围（Thin → Black，含 italic）。CSS 中还注释掉了一个中文字体引用 `HYMacintoshH1`（可能是考虑过但未启用的中文备选）。值得注意的是全部使用 `.otf` 格式而非更现代的 `.woff2`，且包含 font-size 无障碍切换功能（Small/Medium/Large）。Gilroy 在正文中的表现比 Inter 更宽、更具几何感，辨识度很高。

---

### 12. ShanghaiTech China — 2023

| 角色 | 字体 | 字重 | 加载方式 |
|------|------|------|----------|
| 标题 | **Arlon** | 600 | 自托管 `.otf` |
| 导航栏 | **AlibabaPuHuiTi** | 400 | 自托管 `.ttf` |
| 正文 | **AlibabaPuHuiTi** | 400 | 自托管 `.ttf` |
| 代码 | **Courier New**, Courier, monospace | 400 | 系统默认 |

**特点**：双字体方案。Arlon 是一款粗体展示字体（SemiBold 600），专用于主标题和页面标题。AlibabaPuHuiTi（阿里巴巴普惠体）是一款支持中文和拉丁字符的现代无衬线体，用于正文和导航栏。深色背景（#0a0a0a）+ 奶油色文字（#F8F0E8）。与同校 2025 年的 Gilroy 单字体方案形成对比——2023 年版更注重中文阅读体验。

---

## 三、字体使用统计

### 3.1 标题字体

| 字体 | 使用站点 | 出现次数 |
|------|---------|---------|
| **Inter** | Barcelona-UB, PekingHSC | 2 |
| **Oswald** | MSP Maastricht | 1 |
| **Anton** | EPFL | 1 |
| **Outfit** | EPFL | 1 |
| **Exo 2** | Heidelberg | 1 |
| **Poppins** | JU Krakow | 1 |
| **Fira Sans** | INSA Lyon1 | 1 |
| **Abril Fatface** | Patras Medicine 2022 | 1 |
| **Onest** | McGill | 1 |
| **Noto Serif VF** | Patras Med 2025 | 1 |
| **Gilroy** | ShanghaiTech China 2025 | 1 |
| **Arlon** | ShanghaiTech China 2023 | 1 |



### 3.2 导航栏字体

| 字体 | 使用站点 | 出现次数 |
|------|---------|---------|
| **Inter** | Barcelona-UB, PekingHSC, EPFL | 3 |
| **Poppins** | JU Krakow | 1 |
| **Exo 2** | Heidelberg | 1 |
| **Fira Sans** | INSA Lyon1 | 1 |
| **Fira Sans Bold** (inline) | Patras Medicine 2022 | 1 |
| **Onest** | McGill | 1 |
| **Noto Serif VF** | Patras Med 2025 | 1 |
| **Gilroy** | ShanghaiTech China 2025 | 1 |
| **AlibabaPuHuiTi** | ShanghaiTech China 2023 | 1 |
| **系统 UI 栈** | MSP Maastricht | 1 |

Inter 这类高可读性无衬线字体最受欢迎。MSP 是唯一在导航栏使用系统 UI 栈的站点。Patras Med 2025 是唯一在导航栏使用衬线体的站点。ShanghaiTech China 2023 是唯一在导航栏使用中文字体（AlibabaPuHuiTi）的站点。

### 3.3 正文字体

| 字体 | 使用站点 | 出现次数 |
|------|---------|---------|
| **Inter** | MSP Maastricht, EPFL, Barcelona-UB, PekingHSC | 4 |
| **Poppins** | JU Krakow | 1 |
| **Exo 2** | Heidelberg | 1 |
| **Fira Sans** | INSA Lyon1 | 1 |
| **Figtree** | Patras Medicine 2022 | 1 |
| **Onest** | McGill | 1 |
| **Noto Serif VF** | Patras Med 2025 | 1 |
| **Gilroy** | ShanghaiTech China 2025 | 1 |
| **AlibabaPuHuiTi** | ShanghaiTech China 2023 | 1 |
| **Roboto** | EPFL (备选) | 1 |

Inter 是绝对的主流正文字体，Inter 也是 Figma 的默认 UI 字体。值得注意的是 Patras Med 2025 使用衬线体（Noto Serif）作为正文——在 Web 阅读场景中这是少数派选择。AlibabaPuHuiTi 是唯一一个主要用于中文的正文字体。

### 3.4 代码字体

| 字体 | 使用站点 | 出现次数 |
|------|---------|---------|
| **System Mono 栈** (SFMono / Menlo / Monaco / Consolas) | EPFL, Heidelberg, Patras Medicine 2022, Patras Med 2025 | 4 |
| **Bootstrap Mono 栈** | JU Krakow, McGill | 2 |
| **JetBrains Mono** | Barcelona-UB | 1 |
| **Fira Code** | PekingHSC | 1 |
| **Courier** | INSA Lyon1, ShanghaiTech China 2023 | 2 |
| **monospace** (generic) | MSP Maastricht | 1 |

**洞察**：绝大多数站点依赖系统等宽字体栈，只有 Barcelona-UB 和 PekingHSC 自托管了特定的代码字体（JetBrains Mono 和 Fira Code）。INSA Lyon1 使用 Courier 是一种复古的选择

---

## 四、加载策略分析

### 4.1 自托管

| 加载方式 | 站点 |
|---------|------|
| **自托管** (.ttf / .woff2) | EPFL, Heidelberg, JU Krakow, Patras Medicine 2022, Barcelona-UB, McGill, Patras Med 2025, PekingHSC, ShanghaiTech China |
| **Google Fonts CDN** | MSP Maastricht (1/10) |
| **系统依赖** (仅声明，未加载) | INSA Lyon1 (1/10) |

自托管字体文件，这是 iGEM Wiki 的规则。2025-MSP直接使用了Google Fonts CDN 上的字体文件（实际上这是不符合规则的），但该团队仍然拿到了best wiki award。

### 4.2 Variable Fonts 使用

| 站点 | Variable 字体 |
|------|---------------|
| EPFL | Outfit (100–900) |
| Barcelona-UB | Inter (100–900 + italic) |
| Patras Med 2025 | Noto Serif VF (100–900 + wdth), Bitter VF (100–900), Montserrat VF (100–900) |
| PekingHSC | Inter (100–900, 按 Unicode 子集) |

**洞察**：仅 4/10 站点使用了 Variable Fonts。使用 Variable Fonts 的站点通常字体文件数量更少（例如 Barcelona-UB 仅 3 个文件），而传统静态字体方案可能加载 14–20 个文件（Heidelberg, PekingHSC）。

---

## 五、字体方案模式总结


### 模式 A：单一字体 + 字重层级

```
正文字体 = 标题字体 = 导航字体
通过字重 (100–900) 区分层级
```

**代表**：Heidelberg (Exo 2)、JU Krakow (Poppins)、Barcelona-UB (Inter)、ShanghaiTech China (Gilroy)

**优点**：加载量小、视觉统一、维护简单、不会出现字体搭配不协调的问题。

**缺点**：设计层次完全依赖字重变化，缺乏字体个性对比。


---

### 模式 B：正文 + 标题双字体

```
正文字体 ≠ 标题字体
导航栏 = 正文字体 或 标题字体
```

**代表**：MSP Maastricht (Inter + Oswald)、Patras Medicine 2022 (Figtree + Abril Fatface)、ShanghaiTech China 2023 (AlibabaPuHuiTi + Arlon)

**优点**：正文与标题有清晰对比，标题能体现品牌个性，正文保持最佳可读性。

**缺点**：需要选择合适的字体配对，否则可能不协调。

---

### 模式 C：多字体分层

```
3+ 种字体，各自负责不同的视觉层级
标题 ≠ 正文 ≠ 导航 ≠ 代码
```

**代表**：EPFL (5 种字体)、Patras Med 2025 (3 种字体)

**优点**：设计自由度最大，每个视觉层级都能用最合适的字体。

**缺点**：加载量大、管理复杂、容易出现冗余（EPFL 同时加载了 Inter 和 Roboto 两个功能重叠的正文字体）。


---

### 模式 D：使用现成框架

```
使用现成generator提供的默认字体方案
按需扩展中文或其他语言支持
```

**代表**：PekingHSC (Vitepress框架 Inter + Fira Code + 中文标点)

**优点**：零配置、经过框架作者精心调校、多语言支持开箱即用。

**缺点**：缺乏个性，可能与使用相同框架的其他 Wiki 看起来相似。


---

## 附录：示例文件索引

| 示例文件 | 对应 Wiki | 年份 |
|---------|----------|------|
| `2025-MSP-Maastricht.html` | MSP Maastricht (CoreSpin) | 2025 |
| `2025-EPFL.html` | EPFL (PYRONIX) | 2025 |
| `2024-Heidelberg.html` | Heidelberg (PACE) | 2024 |
| `2024-JU-Krakow.html` | JU Krakow | 2024 |
| `2022-INSA-Lyon1.html` | INSA Lyon1 (FIAT LUX) | 2022 |
| `2022-Patras-Medicine.html` | Patras Medicine | 2022 |
| `2025-Barcelona-UB.html` | Barcelona-UB (SKIPPIT) | 2025 |
| `2025-McGill.html` | McGill | 2025 |
| `2025-Patras-Med.html` | Patras Med (MORPHE) | 2025 |
| `2025-PekingHSC.html` | PekingHSC | 2025 |
| `2025-ShanghaiTech-China.html` | ShanghaiTech China (DOCTOR) | 2025 |
| `2023-ShanghaiTech-China.html` | ShanghaiTech China | 2023 |

---
