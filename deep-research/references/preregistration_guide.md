# Preregistration Guide — 研究預註冊指引

## Purpose
研究預註冊（preregistration）決策指引與操作手冊。協助 research_architect_agent 在方法論設計階段判斷是否需要預註冊，並引導研究者完成預註冊流程。

---

## 1. 預註冊決策樹

```
你的研究是否具有以下特徵？
│
├── 驗證假設（confirmatory research）
│   └── 強烈建議預註冊
│       ├── 有預定的統計假設 → 預註冊
│       ├── 會進行顯著性檢定 → 預註冊
│       └── 有主要結果變項 → 預註冊
│
├── 探索性研究（exploratory research）
│   └── 不需要預註冊（但可以）
│       ├── 質性研究 → 通常不預註冊
│       ├── 資料探勘 / EDA → 通常不預註冊
│       └── 但可以預註冊研究設計與分析流程
│
├── 系統性回顧 / Meta-analysis
│   └── 強烈建議註冊（PROSPERO）
│       └── 許多期刊要求系統性回顧需事前註冊
│
├── 隨機對照試驗（RCT）
│   └── 必須註冊
│       ├── ICMJE 要求 RCT 事前註冊
│       └── 未註冊的 RCT 多數期刊不接受
│
├── 複製研究（replication study）
│   └── 強烈建議預註冊
│       └── 預註冊可清楚區分原始假設與修改假設
│
└── 次級資料分析（secondary data analysis）
    └── 建議預註冊
        └── 可防止 HARKing（Hypothesizing After Results are Known）
```

### 何時不需要預註冊

- 純質性研究（grounded theory, phenomenology）
- 探索性資料分析（無預設假設）
- 理論性或哲學性研究
- 文獻回顧（但系統性回顧除外）
- 個案報告或個案研究

### 何時強烈建議預註冊

- 任何涉及假設檢定的研究
- 涉及多重比較的研究
- 需要區分 confirmatory vs. exploratory 分析的研究
- 可能受到 p-hacking、HARKing 質疑的研究
- 申請研究經費時（展現研究嚴謹度）
- 期刊明確要求或鼓勵預註冊

---

## 2. 預註冊平台一覽

| 平台 | 適用領域 | 特色 | 費用 |
|------|---------|------|------|
| **OSF Registries** | 所有學科 | 最廣泛使用、多種模板、DOI、永久保存 | 免費 |
| **PROSPERO** | 系統性回顧 | 專門用於系統性回顧與 meta-analysis | 免費 |
| **AEA Registry** | 經濟學 | 美國經濟學會的 RCT 註冊平台 | 免費 |
| **AsPredicted** | 所有學科 | 簡化版預註冊（9 題）、快速完成 | 免費 |
| **ClinicalTrials.gov** | 臨床試驗 | 美國 FDA 要求的 RCT 註冊 | 免費 |
| **EGAP** | 政治科學 | 實驗與觀察研究治理 | 免費 |
| **RIDIE** | 發展經濟學 | 發展中國家介入研究 | 免費 |

### 平台選擇建議

```
你的研究是？
│
├── 系統性回顧 / meta-analysis → PROSPERO
├── 臨床試驗 / 醫療介入 → ClinicalTrials.gov
├── 經濟學 RCT → AEA Registry
├── 只需要簡單預註冊 → AsPredicted
└── 其他所有研究 → OSF Registries（推薦）
```

---

## 3. 21 項核心內容 Checklist

基於 OSF 標準預註冊格式（Standard Pre-Data Collection Registration），以下為 21 項核心內容：

### A. 研究資訊

| # | 項目 | 說明 |
|---|------|------|
| 1 | **研究標題** | 描述性標題 |
| 2 | **作者/研究團隊** | 所有研究者姓名與隸屬機構 |
| 3 | **研究問題** | 主要研究問題（明確、具體） |
| 4 | **假設** | 預先陳述的假設（含方向性預測） |

### B. 研究設計

| # | 項目 | 說明 |
|---|------|------|
| 5 | **研究設計** | 實驗/觀察、between/within-subjects、因子設計等 |
| 6 | **隨機化** | 隨機分派方法（如適用） |
| 7 | **盲法** | 盲法程度與實施方式（如適用） |
| 8 | **條件/操弄** | 各實驗條件/組別的具體描述 |

### C. 抽樣計畫

| # | 項目 | 說明 |
|---|------|------|
| 9 | **既有資料** | 是否使用既有資料？資料的性質與狀態 |
| 10 | **資料蒐集程序** | 如何蒐集資料（問卷、訪談、實驗、檔案） |
| 11 | **樣本數** | 計畫蒐集的樣本數與決定依據 |
| 12 | **樣本數理由** | Power analysis 或其他樣本數計算方法 |
| 13 | **停止規則** | 何時停止蒐集資料（固定 N / 達到 power / 時間截止） |

### D. 變項

| # | 項目 | 說明 |
|---|------|------|
| 14 | **操弄變項** | 自變項的操作型定義 |
| 15 | **測量變項** | 依變項的操作型定義與測量工具 |
| 16 | **指標** | 各變項的具體指標（量表、題目、計分方式） |

### E. 分析計畫

| # | 項目 | 說明 |
|---|------|------|
| 17 | **統計模型** | 主要分析使用的統計方法 |
| 18 | **轉換** | 資料轉換計畫（如 log 轉換、標準化） |
| 19 | **推論標準** | 顯著水準（alpha）、校正方法、效果量報告 |
| 20 | **資料排除** | 排除標準（outlier 定義、注意力檢查失敗等） |
| 21 | **探索性分析** | 計畫進行但非主要假設的分析 |

---

## 4. 高教研究預註冊範例

### 範例：教學策略對學習成效的影響

```
標題：翻轉教學對大學生批判思考能力的影響：隨機對照試驗

假設：
H1: 接受翻轉教學的學生在批判思考測驗（CCTST）上的分數
    顯著高於接受傳統講授的學生
H2: 翻轉教學對低先備知識學生的效益 > 高先備知識學生

設計：Cluster-randomized controlled trial（班級為隨機化單位）
樣本：12 個班級（6 實驗 / 6 控制），每班約 40 人，共 480 人
Power: 80% power to detect d = 0.4, alpha = .05, ICC = 0.05

主要結果：CCTST 後測分數（控制前測）
次要結果：期末成績、學習動機量表
分析：Multilevel modeling（學生 nested in 班級）

排除標準：
- 出席率 < 50%
- 前後測都未完成
- 注意力檢查題答錯

探索性分析：
- 性別 × 教學法交互作用
- 學習動機作為中介變項
```

### 範例：大學退學因素系統性回顧

```
標題：影響台灣大學生退學決策的因素：系統性文獻回顧

研究問題：哪些因素影響台灣大學生的退學決策？
資料庫：華藝線上圖書館、TSSCI、Scopus、Web of Science
搜尋策略：(退學 OR 休學 OR 離校 OR dropout OR withdrawal)
          AND (大學 OR 高等教育 OR university)
          AND (台灣 OR Taiwan)
時間範圍：2010-2025
納入標準：
- 以台灣大學生為研究對象
- 探討退學/休學原因或影響因素
- 同儕審查之期刊論文或博碩士論文
排除標準：
- 研究對象為高中以下
- 純政策評論（無實證資料）
品質評估：Mixed Methods Appraisal Tool (MMAT)
統合方法：Thematic synthesis
註冊平台：PROSPERO
```

---

## 5. 預註冊聲明範本

### 在論文中揭露預註冊

#### 標準聲明（已預註冊）
```
This study was preregistered on [Platform] prior to data collection
(registration number: [NUMBER]; URL: [URL]). All hypotheses, sample size
rationale, and analysis plans were specified before data collection began.
Deviations from the preregistered plan are noted in [section/supplementary
materials].

本研究於資料蒐集前已在 [平台] 完成預註冊（註冊編號：[編號]；
網址：[URL]）。所有假設、樣本數理由及分析計畫均在資料蒐集前確定。
與預註冊計畫的偏離之處詳見 [章節/補充資料]。
```

#### 偏離預註冊的揭露
```
Deviations from preregistered plan:
1. [Deviation description]: [Reason for deviation]
2. [Deviation description]: [Reason for deviation]
These deviations do not affect the confirmatory nature of the primary analyses.
The preregistered analyses are reported as planned; additional exploratory
analyses are clearly labeled.
```

#### 未預註冊的揭露
```
This study was not preregistered. While the hypotheses were formulated before
data analysis, the distinction between confirmatory and exploratory analyses
should be interpreted with this limitation in mind.

本研究未進行預註冊。儘管假設在資料分析前已形成，但讀者在解讀
驗證性與探索性分析的區分時，應考量此限制。
```

---

## 6. 預註冊 vs. Registered Reports

| 面向 | 預註冊（Preregistration） | 註冊報告（Registered Reports） |
|------|-------------------------|-------------------------------|
| **定義** | 研究計畫事前公開註冊 | 研究計畫事前送交期刊審查 |
| **審查** | 不經過同儕審查 | 第一階段同儕審查（研究設計） |
| **接受時機** | 論文完成後才投稿 | 通過 Stage 1 審查即獲「原則上接受」（IPA） |
| **結果偏誤** | 降低但不消除（研究者仍可選擇性報告） | 大幅消除（無論結果如何都會刊登） |
| **出版偏誤** | 無法解決 | 有效解決（null results 也刊登） |
| **適用期刊** | 所有期刊 | 僅接受 Registered Reports 的期刊 |
| **難度** | 低（填寫表單即可） | 高（需撰寫完整方法論並通過審查） |
| **彈性** | 較高（偏離需揭露但不阻止投稿） | 較低（重大偏離可能影響接受） |

### Registered Reports 流程

```
Stage 1: 提交研究計畫
├── Introduction（理論背景、文獻回顧）
├── Methods（完整方法論、分析計畫）
├── Pilot data（如有）
└── 預測結果的解讀計畫
         ↓
Stage 1 審查（研究設計品質）
├── Accept（In-Principle Acceptance, IPA）
├── Revise and resubmit
└── Reject
         ↓
Stage 2: 執行研究、撰寫結果
├── 嚴格遵循 Stage 1 計畫
├── 報告所有預註冊分析（含 null results）
├── 探索性分析明確標記
└── 偏離之處揭露並說明
         ↓
Stage 2 審查（執行品質）
├── 是否忠實執行 Stage 1 計畫？
├── 結果報告是否完整？
└── 通常不會因為 null results 被拒絕
         ↓
刊登
```

### 支援 Registered Reports 的高教相關期刊（精選）

- *Studies in Higher Education*
- *Higher Education*
- *Assessment & Evaluation in Higher Education*
- *Teaching in Higher Education*
- *Educational Research Review*
- *Learning and Instruction*

> 完整清單：[COS Registered Reports](https://www.cos.io/initiatives/registered-reports)

---

## Quick Reference: 預註冊三步驟

1. **決定是否預註冊**：確認你的研究是否涉及假設檢定
2. **選擇平台**：系統性回顧用 PROSPERO，其他用 OSF
3. **填寫 21 項 checklist**：使用 `templates/preregistration_template.md` 模板

> 預註冊不是完美的解決方案，但它是目前最實用的透明度工具。即使不完美的預註冊，也比沒有預註冊好。
