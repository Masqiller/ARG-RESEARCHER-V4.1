# EQUATOR Reporting Guidelines — 研究設計與報告指南映射

## Purpose
EQUATOR Network（Enhancing the QUAlity and Transparency Of health Research）報告指南速查。協助 research_architect_agent 在方法論設計階段選擇適當的報告 checklist，以及 report_compiler_agent 在撰寫階段確保報告完整性。

---

## 1. 研究設計 → 報告指南映射表

| 研究設計 | 主要報告指南 | 適用情境 |
|----------|------------|---------|
| 系統性回顧 / Meta-analysis | **PRISMA** | 整合多篇研究的文獻回顧 |
| 隨機對照試驗（RCT） | **CONSORT** | 隨機分派的介入實驗 |
| 觀察性研究（cohort, case-control, cross-sectional） | **STROBE** | 非介入性的量化觀察研究 |
| 質性研究 | **COREQ** | 訪談、焦點團體、觀察 |
| 品質改進研究 | **SQUIRE** | 系統性品質改善專案報告 |
| 診斷準確性研究 | STARD | 診斷工具評估 |
| 預後研究 | TRIPOD | 預測模型建構與驗證 |
| 個案報告 | CARE | 單一或少數個案深度報告 |
| 經濟評估 | CHEERS | 成本效益分析 |
| 混合方法研究 | GRAMMS | 質量混合設計 |
| 動物研究 | ARRIVE | 動物實驗 |
| 網絡 Meta-analysis | PRISMA-NMA | 多重比較的 meta-analysis |
| Scoping review | PRISMA-ScR | 範疇回顧（較系統性回顧寬鬆） |

---

## 2. PRISMA — 系統性回顧精簡 Checklist

**全名**：Preferred Reporting Items for Systematic Reviews and Meta-Analyses
**版本**：PRISMA 2020（最新版）

### 核心報告項目

| # | 項目 | 說明 | 必要性 |
|---|------|------|--------|
| 1 | **Title** | 明確標示為系統性回顧（含或不含 meta-analysis） | 必要 |
| 2 | **Abstract** | 結構化摘要（背景、目的、方法、結果、結論） | 必要 |
| 3 | **Registration** | 註冊編號與平台（如 PROSPERO） | 強烈建議 |
| 4 | **Eligibility criteria** | PICOS 或 PEO 格式的納入/排除標準 | 必要 |
| 5 | **Information sources** | 搜尋的資料庫與日期 | 必要 |
| 6 | **Search strategy** | 至少一個資料庫的完整搜尋策略 | 必要 |
| 7 | **Selection process** | 篩選流程（幾位審查者、如何解決歧見） | 必要 |
| 8 | **Data extraction** | 資料萃取方法 | 必要 |
| 9 | **Risk of bias** | 偏誤風險評估工具與結果 | 必要 |
| 10 | **Synthesis methods** | 統合方法（narrative / meta-analytic） | 必要 |
| 11 | **PRISMA flow diagram** | 文獻篩選流程圖 | 必要 |
| 12 | **Results** | 各研究特徵、偏誤評估、統合結果 | 必要 |
| 13 | **Discussion** | 證據確定性、限制、與既有知識的關係 | 必要 |
| 14 | **Funding** | 資金來源與利益衝突 | 必要 |

### PRISMA Flow Diagram 模板

```
Records identified (n = )
├── Database searching (n = )
└── Other sources (n = )
         ↓
Duplicates removed (n = )
         ↓
Records screened (n = )
├── Excluded (n = )
         ↓
Reports sought for retrieval (n = )
├── Not retrieved (n = )
         ↓
Reports assessed for eligibility (n = )
├── Excluded, with reasons (n = )
│   ├── Reason 1 (n = )
│   ├── Reason 2 (n = )
│   └── Reason 3 (n = )
         ↓
Studies included in review (n = )
├── In qualitative synthesis (n = )
└── In quantitative synthesis (meta-analysis) (n = )
```

---

## 3. CONSORT — 隨機對照試驗精簡 Checklist

**全名**：Consolidated Standards of Reporting Trials
**版本**：CONSORT 2010 + extensions

### 核心報告項目

| # | 項目 | 說明 |
|---|------|------|
| 1 | **Title & Abstract** | 標示為 RCT；結構化摘要 |
| 2 | **Background** | 科學背景與試驗理由 |
| 3 | **Objectives** | 具體目的或假設 |
| 4 | **Trial design** | 設計類型（平行、交叉、階乘等）與分配比例 |
| 5 | **Participants** | 納入標準、場域、資料蒐集地點 |
| 6 | **Interventions** | 每組介入措施的具體描述（含如何、何時實施） |
| 7 | **Outcomes** | 主要與次要結局測量，含定義與時間點 |
| 8 | **Sample size** | 樣本數計算方法（power analysis） |
| 9 | **Randomisation** | 隨機序列產生方法、分配隱藏機制 |
| 10 | **Blinding** | 盲法實施（誰被遮蔽、如何實施） |
| 11 | **Statistical methods** | 統計分析方法、ITT/PP 分析 |
| 12 | **Flow diagram** | 參與者流程圖（recruitment → allocation → follow-up → analysis） |
| 13 | **Results** | 每組結果、效果量與精確度（CI） |
| 14 | **Harms** | 不良事件或副作用 |
| 15 | **Limitations** | 偏誤來源、不精確性、多重比較 |
| 16 | **Registration** | 試驗註冊編號 |

### 高教研究適用說明

教育領域的 RCT（如教學法比較實驗）常面臨：
- 無法完全隨機化（cluster randomization 更常見）
- 難以實施盲法（教師/學生知道分組）
- 建議使用 **CONSORT-SPI**（Social and Psychological Interventions extension）

---

## 4. STROBE — 觀察性研究精簡 Checklist

**全名**：Strengthening the Reporting of Observational Studies in Epidemiology
**適用**：Cohort studies, case-control studies, cross-sectional studies

### 核心報告項目

| # | 項目 | 說明 |
|---|------|------|
| 1 | **Title & Abstract** | 指出研究設計類型 |
| 2 | **Background** | 科學背景、研究理由 |
| 3 | **Objectives** | 具體目的、預先設定的假設 |
| 4 | **Study design** | 明確說明研究設計（cohort / case-control / cross-sectional） |
| 5 | **Setting** | 場域、地點、相關日期（recruitment, exposure, follow-up） |
| 6 | **Participants** | 納入標準、資料來源、樣本選取方式 |
| 7 | **Variables** | 結果變項、暴露變項、潛在干擾因子、效果修飾因子 |
| 8 | **Data sources** | 各變項的資料來源與測量方法 |
| 9 | **Bias** | 處理潛在偏誤來源的方式 |
| 10 | **Study size** | 樣本數的決定方式 |
| 11 | **Statistical methods** | 統計方法（含干擾因子處理、缺失值處理） |
| 12 | **Results** | 描述性統計、主要結果（含效果量、CI、p-value） |
| 13 | **Discussion** | 關鍵發現、限制、推論性、與其他研究的一致性 |
| 14 | **Funding** | 資金來源 |

### 高教研究適用說明

高教常見的觀察性研究：
- 學生學習成效橫斷面調查 → cross-sectional STROBE
- 畢業生就業追蹤 → cohort STROBE
- 退學風險因素分析 → case-control STROBE

---

## 5. COREQ — 質性研究精簡 Checklist

**全名**：Consolidated Criteria for Reporting Qualitative Research
**適用**：訪談、焦點團體

### 核心報告項目（32 項，分 3 大領域）

#### Domain 1: 研究團隊與反身性

| # | 項目 | 說明 |
|---|------|------|
| 1 | **Interviewer/facilitator** | 誰進行訪談或主持焦點團體 |
| 2 | **Credentials** | 研究者資歷 |
| 3 | **Occupation** | 研究者的職業身分 |
| 4 | **Gender** | 研究者性別 |
| 5 | **Experience & training** | 質性研究經驗與訓練 |
| 6 | **Relationship with participants** | 研究者與參與者的關係 |
| 7 | **Participant knowledge** | 參與者對研究的了解程度 |

#### Domain 2: 研究設計

| # | 項目 | 說明 |
|---|------|------|
| 8 | **Methodological orientation** | 理論框架（如 grounded theory, phenomenology） |
| 9 | **Sampling** | 抽樣策略與方式 |
| 10 | **Method of approach** | 如何接觸參與者 |
| 11 | **Sample size** | 參與者人數 |
| 12 | **Non-participation** | 拒絕參與的人數與原因 |
| 13 | **Setting** | 訪談地點 |
| 14 | **Presence of non-participants** | 訪談時是否有非參與者在場 |
| 15 | **Description of sample** | 參與者基本資料 |
| 16 | **Interview guide** | 訪談大綱是否使用、是否先行測試 |
| 17 | **Repeat interviews** | 是否進行重複訪談 |
| 18 | **Audio/visual recording** | 是否錄音/錄影 |
| 19 | **Field notes** | 是否撰寫田野筆記 |
| 20 | **Duration** | 訪談時長 |
| 21 | **Data saturation** | 是否討論資料飽和 |
| 22 | **Transcripts returned** | 逐字稿是否回饋給參與者 |

#### Domain 3: 分析與發現

| # | 項目 | 說明 |
|---|------|------|
| 23 | **Data analysis** | 分析方法（如 thematic analysis, IPA） |
| 24 | **Software** | 使用的分析軟體 |
| 25 | **Participant checking** | 參與者是否確認研究發現 |
| 26 | **Quotations** | 是否呈現引述以支持主題 |
| 27 | **Data and findings consistency** | 資料與發現的一致性 |
| 28 | **Clarity of major themes** | 主題是否清楚呈現 |
| 29 | **Clarity of minor themes** | 次要主題是否清楚呈現 |

---

## 6. SQUIRE — 品質改進研究精簡 Checklist

**全名**：Standards for QUality Improvement Reporting Excellence
**版本**：SQUIRE 2.0
**適用**：品質改善專案、系統性品質改進、高教品保（QA）研究

### 核心報告項目

| # | 項目 | 說明 |
|---|------|------|
| 1 | **Title** | 指出為品質改進研究 |
| 2 | **Abstract** | 結構化摘要 |
| 3 | **Problem description** | 品質問題的本質與嚴重性 |
| 4 | **Available knowledge** | 已知的相關證據 |
| 5 | **Rationale** | 改進方案的理論基礎 |
| 6 | **Specific aims** | 改進的具體目標（可量化） |
| 7 | **Context** | 改進所在的環境脈絡 |
| 8 | **Intervention(s)** | 改進措施的具體描述 |
| 9 | **Study of the intervention(s)** | 如何評估改進效果 |
| 10 | **Measures** | 結果指標、過程指標、平衡指標 |
| 11 | **Analysis** | 定量/定性分析方法 |
| 12 | **Ethical considerations** | 倫理審查（如適用） |
| 13 | **Results** | 改進結果（含時間序列資料） |
| 14 | **Discussion** | 關鍵發現、與脈絡的關係、可推廣性 |
| 15 | **Limitations** | 研究限制 |

### 高教品保研究特別適用

SQUIRE 對以下高教品保研究特別有參考價值：
- **教學品質改善**：新教學策略的導入與評估
- **課程改革**：課程重新設計的效果追蹤
- **學生支持服務改善**：輔導、諮商、學習支援的系統改善
- **HEEACT 評鑑自我改善**：針對評鑑發現的改善行動與追蹤
- **校務研究（IR）驅動的改善**：基於數據的決策與改善循環

---

## 7. 高等教育研究情境推薦

### 常用指南排行

| 排名 | 指南 | 高教常見使用情境 |
|------|------|----------------|
| 1 | **PRISMA** | 教育政策系統性回顧、教學策略 meta-analysis |
| 2 | **COREQ** | 教師/學生經驗訪談、焦點團體 |
| 3 | **STROBE** | 學生調查、校務資料分析 |
| 4 | **SQUIRE** | 教學品質改善、品保認可 |
| 5 | **CONSORT** | 教學介入實驗（較少見但影響力大） |

### 研究設計快速選擇

```
你的研究類型是？
│
├── 整合既有研究 → PRISMA
│   ├── 系統性回顧 → PRISMA 2020
│   ├── 範疇回顧 → PRISMA-ScR
│   └── Meta-analysis → PRISMA + MOOSE
│
├── 介入實驗 → CONSORT
│   ├── 個人隨機化 → CONSORT 2010
│   ├── 班級/學校隨機化 → CONSORT-Cluster
│   └── 社會/心理介入 → CONSORT-SPI
│
├── 觀察性調查 → STROBE
│   ├── 橫斷面調查 → STROBE-CS
│   ├── 追蹤研究 → STROBE-Cohort
│   └── 回溯比較 → STROBE-CC
│
├── 質性研究 → COREQ
│   ├── 訪談 → COREQ
│   ├── 焦點團體 → COREQ
│   └── 民族誌 → SRQR（替代）
│
└── 品質改善 → SQUIRE
    ├── PDSA 循環 → SQUIRE 2.0
    └── QA/認可改善 → SQUIRE 2.0
```

---

## Quick Reference: 選擇報告指南三步驟

1. **確認研究設計**：你的研究屬於哪種設計類型？
2. **查映射表**：找到對應的報告指南
3. **下載 checklist**：到 [EQUATOR Network](https://www.equator-network.org/) 下載完整 checklist

> 提醒：報告指南是最低標準，不是品質上限。符合 checklist 不代表研究品質高，但不符合 checklist 通常代表報告品質有缺陷。
