# WuWa Echo Tuning Simulator

> 鸣潮声骸调谐模拟器 · 表格化 13 词条 · 批量自动化 · 评分体系

一个用于《鸣潮》（Wuthering Waves）声骸开孔 / 调谐模拟的单文件网页工具。  
无需安装、无需构建，浏览器直接打开 HTML 即可运行。

---

## ✨ 功能特性

| 功能 | 说明 |
|---|---|
| 📊 **13 词条概率表** | 完整展示 13 个副词条的档位、数值、单项概率、累计概率 |
| 🎯 **评分体系** | 主词条保底 8.5 分，有效词条按系数计分，垃圾词条恒为 0 分 |
| 🔁 **批量自动化** | 一次模拟最多 10000 个胚子，支持「无脑拉满」与「5开4止损」两种策略 |
| 🎨 **颜色视觉增强** | 金 / 紫 / 绿 / 灰 四档品质配色，无效词条整体降亮并标注「无收益」 |
| ⚡ **防抖渲染** | 评分表使用 `requestAnimationFrame` 合并渲染，保留滚动位置，避免卡顿 |
| 📜 **历史记录** | 自动保存最近 1000 条模拟记录，双爆高分胚子高亮显示 |
| 🏆 **历史最高值** | 记录 13 个词条出现过的最高数值，摸到顶档显示 🏆 |
| 💾 **本地持久化** | 通过 `localStorage` 保存历史与最高值，刷新不丢失 |
| 🖱️ **交互增强** | 空孔位可直接点击开孔，支持 +1 / 开2 / 开3 / 开4 / 拉满5孔 |

---

## 🚀 快速开始

1. 下载 `声骸模拟器-v10-....html` 文件
2. 用任意现代浏览器（Chrome / Edge / Firefox）双击打开
3. 点击 **+1 开孔** 或 **无脑拉满5孔** 开始模拟
4. 在右侧查看评分表、概率表、历史记录、历史最高值

> 无需 Node.js、无需服务器、无需联网。

---

## 📐 评分规则

### 主词条

- COST 4 声骸主词条保底 **8.5 分**

### 有效词条（6 种，计分）

| 词条 | 品质 | 系数 | 满档得分 |
|---|---|---|---|
| 暴击率 | ★ 金 | 8.7 / 7.5 | ≈ 12.18 |
| 暴击伤害 | ★ 金 | 8.7 / 15.0 | ≈ 12.18 |
| 百分比攻击 | ◆ 紫 | 8 / 11.6 | 8.00 |
| 共鸣解放伤害 | ◆ 紫 | 5 / 11.6 | 5.00 |
| 固定攻击 | ● 绿 | 5 / 60 | 5.00 |
| 共鸣效率 | ● 绿 | 1.5 / 12.4 | 1.50 |

### 无效词条（7 种，恒 0 分）

百分比生命 / 固定生命 / 百分比防御 / 固定防御 / 普攻伤害 / 重击伤害 / 共鸣技能伤害

> 无论数值多高，一律 **0 分**，列表中标注「无收益」，评分表整行变灰。

### 总分评级

| 总分 | 评级 |
|---|---|
| ≥ 40 | 极品 |
| ≥ 30 | 优秀 |
| ≥ 20 | 合格 |
| ≥ 12 | 一般 |
| < 12 | 拉胯 |

---

## 🤖 批量模拟策略

| 策略 | 逻辑 |
|---|---|
| **无脑拉满5孔** | 每个胚子都开到 5 孔，统计总消耗与平均评分 |
| **5开4止损** | 开到第 4 孔时判断：<br>• 2 条双爆 → 继续开第 5 孔<br>• 1 条双爆 + 大攻击 → 继续开第 5 孔<br>• 其余情况 → 直接放弃，节省打孔器 |

模拟完成后弹出统计结果：

- 总模拟数量
- 总消耗打孔器
- 出双爆次数
- 平均每个双爆消耗打孔器
- 平均评分

---

## 🧠 技术说明

- **纯前端单文件**：HTML + CSS + 原生 JavaScript，无任何依赖
- **防抖渲染**：`requestAnimationFrame` + 渲染标志位，避免重复重绘
- **滚动位置保持**：评分表重绘前记录 `scrollTop`，重绘后恢复
- **表格化布局**：`table-layout: fixed` + `contain: strict`，提升滚动性能
- **品质配色**：CSS 变量统一管理金 / 紫 / 绿 / 灰四档颜色
- **数据持久化**：`localStorage` 键名 `wuwa_echo_history`、`wuwa_echo_max`

---

## 📁 项目结构

```text
wuwa-echo-simulator/
├── 声骸模拟器-v10-表格化13词条-增强交互-防抖-自动化打孔-颜色视觉增强-添加评分体系-优化体验-垃圾词条不得分.html
└── README.md
```

> 单文件项目，HTML 即全部。

---

## ⚠️ 免责声明

- 本项目为**非官方粉丝工具**，与库洛游戏 / 《鸣潮》官方无关
- 概率数据来源于社区整理，仅供参考，不代表游戏内真实掉落
- 评分体系为主观设计，仅用于娱乐与参考
- 请勿用于任何商业用途

---

## 📄 License

MIT License

---

# English Version

## WuWa Echo Tuning Simulator

A single-file web tool for simulating Echo tuning / substat rolling in **Wuthering Waves**.

### Features

- 13 substats probability table with per-tier and cumulative rates
- Scoring system: main stat base 8.5, 6 valuable substats, 7 trash substats always 0
- Batch simulation up to 10,000 echoes with two strategies: **Full 5-hole** and **Stop-at-4**
- Color-coded grades (Gold / Purple / Green / Gray) with visual dimming for useless stats
- Debounced rendering via `requestAnimationFrame`, scroll position preserved
- History (last 1000 records) and per-substat max values, persisted in `localStorage`
- Click empty slots to open holes directly

### Quick Start

Download the HTML file and open it in any modern browser. No build step required.

### Scoring

- Main stat base: **8.5**
- Valuable substats: Crit Rate, Crit DMG, ATK%, Flat ATK, Energy Regen, Resonance Liberation DMG
- Trash substats: HP / DEF / Basic / Heavy / Skill DMG → always **0**

### Batch Strategies

- **Full 5-hole**: always open all 5 slots
- **Stop-at-4**: at 4 holes, keep going only if 2 crits, or 1 crit + ATK%

### Disclaimer

Unofficial fan-made tool. Not affiliated with Kuro Games. For entertainment only.

### License

MIT
