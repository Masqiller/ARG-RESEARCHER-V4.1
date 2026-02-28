# Preregistration Template — OSF 標準 21 項預註冊模板

## Purpose
基於 OSF Standard Pre-Data Collection Registration 格式的填空模板。研究者在資料蒐集前填寫此模板，完成後上傳至預註冊平台（如 OSF Registries）。

---

## 使用說明

1. 在資料蒐集**之前**填寫此模板
2. `[必填]` 標記為必要項目，`[選填]` 為建議但非必要
3. 若某項目不適用，請寫「不適用」並簡述原因
4. 填寫完成後，至 [OSF Registries](https://osf.io/registries) 建立預註冊
5. 預註冊一旦提交即不可修改（可設定 embargo period）

---

## A. Study Information（研究資訊）

### 1. Title [必填]
> 研究標題（Study Title）

```
[填入描述性研究標題]
```

### 2. Authors [必填]
> 研究團隊（Research Team）

| 姓名 | 機構 | 角色 | ORCID |
|------|------|------|-------|
| [姓名] | [機構] | [PI / Co-PI / RA] | [ORCID] |
| [姓名] | [機構] | [角色] | [ORCID] |

### 3. Research Questions [必填]
> 主要研究問題（Main Research Questions）

```
RQ1: [填入主要研究問題]
RQ2: [填入次要研究問題，如有]
```

### 4. Hypotheses [必填]
> 預先陳述的假設（Pre-specified Hypotheses）
> 請明確陳述方向性預測（directional prediction）

```
H1: [填入假設 1，含預期方向]
    例：接受 X 處理的學生在 Y 測驗上的分數顯著高於控制組

H2: [填入假設 2，如有]

H3: [填入假設 3，如有]
```

---

## B. Design Plan（研究設計）

### 5. Study Type [必填]
> 研究設計類型（Study Design）

- [ ] Experiment（實驗研究）
  - [ ] Between-subjects
  - [ ] Within-subjects
  - [ ] Mixed design
  - [ ] Factorial design: ___ x ___
- [ ] Observational study（觀察性研究）
  - [ ] Cross-sectional
  - [ ] Longitudinal / Cohort
  - [ ] Case-control
- [ ] Survey（調查研究）
- [ ] Other: [說明]

```
[詳細描述研究設計]
```

### 6. Randomization [選填]
> 隨機化程序（Randomization Procedure）

```
隨機化方法：[簡單隨機 / 分層隨機 / 集群隨機 / 區組隨機 / 不適用]
隨機化單位：[個人 / 班級 / 學校 / 不適用]
隨機化工具：[亂數表 / 電腦程式 / 抽籤 / 不適用]
分配比例：[1:1 / 2:1 / 其他]
```

### 7. Blinding [選填]
> 盲法（Blinding / Masking）

```
盲法程度：[無盲法 / 單盲 / 雙盲 / 三盲]
被遮蔽的對象：[參與者 / 研究者 / 評估者 / 不適用]
盲法維持方式：[說明如何維持盲法]
解盲時機：[說明何時解盲]
```

### 8. Study Design / Conditions [必填]
> 各組別/條件的具體描述

```
實驗組/條件 1：[詳細描述介入內容、時長、頻率]
實驗組/條件 2：[如有]
控制組：[詳細描述控制條件]
```

---

## C. Sampling Plan（抽樣計畫）

### 9. Existing Data [必填]
> 是否使用既有資料（Existing Data Declaration）

- [ ] 尚未蒐集任何資料（Registration prior to creation of data）
- [ ] 已有資料但尚未查看（Registration prior to any human observation of the data）
- [ ] 已查看部分資料（Registration prior to accessing the data）
- [ ] 已使用資料進行初步分析（Registration following analysis of the data）

```
[說明資料狀態與你對資料的了解程度]
```

### 10. Data Collection Procedures [必填]
> 資料蒐集程序

```
蒐集方式：[線上問卷 / 實體問卷 / 訪談 / 實驗 / 檔案資料 / 其他]
蒐集工具：[問卷名稱 / 量表名稱 / 實驗軟體]
蒐集地點：[線上 / 教室 / 實驗室 / 其他]
蒐集時程：[起迄日期]
蒐集者：[誰負責蒐集]
```

### 11. Sample Size [必填]
> 計畫蒐集的樣本數

```
目標樣本數：[N = ]
各組樣本數：[實驗組 n = , 控制組 n = ]
```

### 12. Sample Size Rationale [必填]
> 樣本數決定依據

```
方法：[Power analysis / 先前研究慣例 / 可行性限制 / 其他]

Power analysis 參數（如適用）：
- 效果量（effect size）：[d = / f = / r = ]
- 效果量來源：[先行研究 / meta-analysis / pilot study]
- 顯著水準（alpha）：[.05 / .01]
- 統計檢定力（power）：[.80 / .90]
- 檢定類型：[t-test / ANOVA / regression / 其他]
- 計算工具：[G*Power / R / 其他]
- 計算結果：需要至少 N = [  ] 人

過度蒐集比例：[考慮流失率 ___%, 實際目標 N = ]
```

### 13. Stopping Rule [必填]
> 何時停止蒐集資料

```
停止規則：
- [ ] 達到目標樣本數即停止
- [ ] 達到指定時間即停止（截止日：[日期]）
- [ ] 達到目標 power 即停止（sequential analysis）
- [ ] 其他：[說明]
```

---

## D. Variables（變項）

### 14. Manipulated Variables [必填，實驗研究]
> 操弄/自變項（Independent Variables）

```
自變項 1：[名稱]
操作型定義：[如何操弄]
水準：[水準 1 / 水準 2 / ...]

自變項 2：[如有]
```

### 15. Measured Variables [必填]
> 測量/依變項（Dependent Variables）

```
主要依變項：[名稱]
操作型定義：[如何測量]
測量工具：[量表名稱 / 測驗名稱]
信效度：[引用信效度文獻]

次要依變項：[如有]

共變項/控制變項：[如有]
```

### 16. Indices [必填]
> 各變項的具體計分方式

```
變項 1 計分：
- 題目：[哪些題目]
- 計分方式：[加總 / 平均 / 因素分數 / 其他]
- 反向計分題：[哪些題目需反向計分]
- 處理方式：[如何處理缺漏值]

變項 2 計分：[同上格式]
```

---

## E. Analysis Plan（分析計畫）

### 17. Statistical Models [必填]
> 主要統計分析方法

```
假設 1 的分析：
- 統計方法：[independent t-test / ANOVA / regression / HLM / SEM / 其他]
- 詳細說明：[模型規格，如 DV ~ IV + covariate + (1|cluster)]

假設 2 的分析：[同上格式]
```

### 18. Transformations [選填]
> 資料轉換計畫

```
計畫的轉換：
- [ ] 不進行轉換
- [ ] Log 轉換：適用於 [哪些變項]，觸發條件 [偏態 > ]
- [ ] 標準化（Z-score）
- [ ] 其他：[說明]
```

### 19. Inference Criteria [必填]
> 統計推論標準

```
顯著水準：alpha = [.05 / .01 / .005]
多重比較校正：[Bonferroni / Holm / FDR / 不適用]
效果量報告：[Cohen's d / eta-squared / R² / 其他]
信賴區間：[95% CI / 99% CI]
單尾/雙尾檢定：[雙尾 / 單尾，附理由]
```

### 20. Data Exclusion [必填]
> 資料排除標準

```
排除標準：
- [ ] 注意力檢查未通過（具體標準：[                ]）
- [ ] 作答時間過短/過長（標準：< [  ] 分鐘 或 > [  ] 分鐘）
- [ ] 極端值（定義：[> 3 SD / IQR 方法 / 其他]）
- [ ] 未完成率 > [  ]%
- [ ] 其他：[說明]

排除後處理：
- 報告排除前後的樣本數
- 比較排除樣本與保留樣本的基本特徵
```

### 21. Exploratory Analyses [選填]
> 計畫中的探索性分析

```
探索性分析（非主要假設，但計畫進行）：
1. [分析描述]
2. [分析描述]

這些分析將在論文中明確標記為「探索性」。
```

---

## F. Other（其他）

### 倫理審查 [選填]
```
IRB 審查狀態：[已通過 / 審查中 / 免除 / 不適用]
IRB 編號：[                ]
審查機構：[                ]
```

### 資料可用性 [選填]
```
資料是否公開：[是 / 否 / 部分公開]
資料存放位置：[OSF / Dataverse / 其他]
存放時機：[論文發表後 / 研究完成後 / 其他]
```

### 補充材料 [選填]
```
- [ ] 問卷/量表全文
- [ ] 刺激材料
- [ ] 分析程式碼
- [ ] Power analysis 報告
- [ ] Pilot study 結果
```

---

## 提交前確認

- [ ] 所有 [必填] 項目都已填寫
- [ ] 假設陳述明確且可檢驗
- [ ] 分析方法與假設對應
- [ ] 排除標準在資料蒐集前已確定
- [ ] 已區分驗證性分析與探索性分析
- [ ] 已確認 IRB 審查狀態
- [ ] 已選定預註冊平台（推薦 OSF Registries）

> 填寫完成後，前往 [OSF Registries](https://osf.io/registries) 提交預註冊。
