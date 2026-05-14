<div align="center">

# Academic Research Graphify (ARG)

**你的 AI 學術研究副駕駛**

[![Version](https://img.shields.io/badge/version-v4.0.0-blue)](#)
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](https://opensource.org/licenses/MIT)
[![Agents](https://img.shields.io/badge/agents-37-purple)](#-代理團隊)
[![Skills](https://img.shields.io/badge/skills-4-orange)](#-技能與模式)
[![Modes](https://img.shields.io/badge/modes-25-red)](#-技能與模式)

[English](README.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Português](README.pt-BR.md) | [हिन्दी](README.hi.md) | [العربية](README.ar.md) | [Русский](README.ru.md)

---

**37 個專業 AI 代理**，橫跨 **4 項技能** 和 **25 種模式**，帶你從研究構思到論文發表。
支援**任何 AI 編碼助手** — Windsurf、Cursor、Claude Code、GitHub Copilot、Cline、Aider、Continue 等。

[快速開始](#-快速開始) | [功能特色](#-功能特色) | [架構](docs/ARCHITECTURE.md) | [設置指南](UNIVERSAL_SETUP.md)

</div>

---

## 為什麼選 ARG？

> **AI 是你的副駕駛，不是機長。** ARG 不會替你寫論文。它處理苦工——搜文獻、排格式、驗數據、查邏輯——讓你專注在真正需要你腦子的事：定義問題、選方法、詮釋數據、寫出「我認為」後面那句話。

全自動 AI 研究管線會繼承結構性失敗模式：幻覺結果、方法論偽造、框架鎖定、引用幻覺。**這些不是 bug——是架構性的。** 再多的規模擴展也無法消除。

ARG 建立在一個前提上：**人類研究者 + AI 的組合，比任何一方單獨運作都更能避開這些失敗模式。**

| 問題 | ARG 的解法 |
|------|-----------|
| 引用幻覺 | Semantic Scholar API 驗證 + 誠信閘門 |
| 框架鎖定 | 魔鬼代言人 + 讓步門檻協議 |
| 諂媚性 | 反諂媚評分（讓步前須 1-5 分評估） |
| 過早收束 | 意圖偵測 + 對話健康度監控 |
| 方法論偽造 | Stage 2.5 & 4.5 的 7 類阻斷式檢查清單 |
| 不可驗證的主張 | 三層引用協議 + 主張忠實度錨定 |

---

## 快速開始

```bash
git clone https://github.com/Masqiller/ARG-Researcher.git ~/ARG-Researcher
```

在 IDE 中開啟，設定檔自動偵測：

| 助手 | 設定檔 | 指令 |
|:-----|:-------|:-----|
| **Windsurf** | `.windsurf/workflows/arg-*.md` | 原生 `/arg-*` 工作流 |
| **Cursor** | `.cursor/rules/arg-instructions.mdc` | 聊天中輸入 `/arg-*` |
| **Claude Code** | `.claude/CLAUDE.md` + `commands/` | 原生 `/arg-*` 指令 |
| **GitHub Copilot** | `.github/copilot-instructions.md` | 聊天中輸入 `/arg-*` |
| **Cline / Roo Code** | `.clinerules` | 聊天中輸入 `/arg-*` |
| **Aider** | `.aider/conventions.md` | 聊天中輸入 `/arg-*` |
| **Continue** | `.continue/config.json` | 聊天中輸入 `/arg-*` |
| **其他** | `.ai/instructions.md` | 聊天中輸入 `/arg-*` |

**測試：** 執行 `/arg-plan` 並描述你正在寫的論文。ARG 會啟動蘇格拉底式對話來規劃章節結構。

> **詳細設置：** [UNIVERSAL_SETUP.md](UNIVERSAL_SETUP.md) | **完整設定指南：** [docs/SETUP.zh-TW.md](docs/SETUP.zh-TW.md)

---

## 功能特色

<table>
<tr>
<td width="50%">

### 深度研究
*13 個代理 | 7 種模式*

- 蘇格拉底引導式探索
- PRISMA 系統性回顧
- Semantic Scholar API 驗證
- 意圖偵測（探索型 vs. 目標型）
- 對話健康度監控
- 跨模型魔鬼代言人（選用）
- 證據階層事實查核

</td>
<td width="50%">

### 學術論文
*12 個代理 | 10 種模式*

- 風格校準（學習你的寫作風格）
- 寫作品質檢查
- LaTeX 強化（APA 7.0、IEEE、Chicago）
- 視覺化代理（matplotlib/seaborn/ggplot2）
- 修訂指導 & R&R 回覆
- 引用格式轉換（5 種格式）
- 反洩漏協議
- VLM 圖表驗證

</td>
</tr>
<tr>
<td width="50%">

### 學術論文審查
*7 個代理 | 6 種模式*

- 主編 + 3 位動態審查者 + 魔鬼代言人
- 0-100 品質評分標準
- Sprint Contract（論文盲審第一階段 + 第二階段）
- 讓步門檻協議
- 校準模式（測量 FNR/FPR）
- R&R 追蹤矩陣

</td>
<td width="50%">

### 學術管線
*10 階段協調器*

- 自適應檢查點（需用戶確認）
- Stage 2.5 & 4.5 誠信閘門（強制，不可跳過）
- Material Passport 與主張驗證
- 協作深度觀察者（諮詢性質）
- 分數軌跡追蹤
- 6 維度協作品質評估（1-100）

</td>
</tr>
</table>

---

## `/arg-*` 指令

| 指令 | 功能 |
|:-----|:-----|
| `/arg-full` | 完整管線：研究 → 寫作 → 審查 → 修訂 → 定稿 |
| `/arg-plan` | 蘇格拉底式逐章規劃 |
| `/arg-outline` | 詳細大綱 + 證據地圖 |
| `/arg-abstract` | 雙語摘要（繁中 + 英文）+ 關鍵字 |
| `/arg-revision` | 修訂稿 + R&R 回覆 |
| `/arg-revision-coach` | 修訂路線圖 + 回覆信骨架 |
| `/arg-lit-review` | 論文格式的文獻綜述 |
| `/arg-format-convert` | 轉換為 LaTeX / DOCX / PDF / Markdown |
| `/arg-citation-check` | 引用錯誤報告 |
| `/arg-disclosure` | 特定場合 AI 使用聲明 |

---

## 支援格式

| 類別 | 選項 |
|:-----|:-----|
| **引用格式** | APA 7.0（預設）、Chicago、MLA、IEEE、Vancouver |
| **論文類型** | IMRaD、文獻回顧、理論分析、案例研究、政策簡報、會議論文 |
| **輸出格式** | Markdown、LaTeX、DOCX（Pandoc）、PDF（tectonic） |
| **語言** | 英文、繁體中文、雙語摘要；意圖偵測支援任何語言 |

---

## 架構

```
研究 → 寫作 → 審查 → 修訂 → 發表
 |       |      |      |      |
Stage 1  S2    S3     S4     S5
 |       |      |      |      |
 +- 2.5 -+      +- 4.5-+      +- Stage 6
 誠信閘門        誠信閘門       流程總結與評估
```

**完整架構：** [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md)

---

## 效能與成本

| 管線 | 預估成本 | Token 數 |
|:-----|:---------|:---------|
| 完整論文（15k 字） | ~$4–6 | ~500k tokens |
| 單次審查 | ~$1–2 | ~150k tokens |
| 文獻回顧 | ~$0.50–1 | ~80k tokens |

詳見：[docs/PERFORMANCE.md](docs/PERFORMANCE.md)

---

## 授權條款

本專案採用 [MIT 授權](LICENSE)。可自由使用、修改、散布，不限商業用途。詳見 [CONTRIBUTORS.md](CONTRIBUTORS.md)。
