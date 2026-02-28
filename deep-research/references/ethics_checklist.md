# Research Ethics Checklist — AI-Assisted Research

## Purpose
Comprehensive ethics checklist for AI-assisted academic research. Used by the ethics_review_agent.

## 1. AI Disclosure

### Mandatory Disclosure Elements
- [ ] AI tools used are named (e.g., "Claude," "GPT-4," "Gemini")
- [ ] Scope of AI involvement specified:
  - [ ] Literature search assistance
  - [ ] Source screening
  - [ ] Evidence synthesis
  - [ ] Draft writing
  - [ ] Editing/revision
  - [ ] Data analysis
  - [ ] Translation
- [ ] Human oversight described (who reviewed what, at which stages)
- [ ] AI limitations acknowledged (potential hallucination, knowledge cutoff, etc.)
- [ ] AI version/date noted (for reproducibility)

### Disclosure Statement Template
```
AI Disclosure: This research was conducted with assistance from [AI Tool Name]
(version/date). AI was used for [specific tasks]. All findings were verified
against cited sources by [human role]. The research team maintains full
responsibility for the accuracy and interpretation of all content.
```

### Where to Place Disclosure
- In the methodology section (detailed)
- In the abstract or author note (brief)
- In footnotes for specific AI-generated analyses

## 2. Attribution Integrity

### Citation Ethics
- [ ] Every factual claim has at least one supporting citation
- [ ] No fabricated or hallucinated references
  - Verification: Spot-check minimum 20% of references for existence
  - Cross-check DOIs, publication years, author names
- [ ] Paraphrasing is genuine (not just rearranging words)
- [ ] Direct quotes are exact and attributed
- [ ] Ideas are attributed to original authors, not intermediary sources
- [ ] Self-citation is proportionate (not excessive or exclusionary)

### AI-Specific Attribution Risks
| Risk | Description | Mitigation |
|------|-------------|-----------|
| Hallucinated references | AI generates plausible but non-existent citations | Verify every reference against database |
| Merged citations | AI combines details from multiple sources | Cross-check each citation element |
| Incorrect authors | AI assigns wrong authors to works | Verify author names against actual publications |
| Wrong year | AI uses incorrect publication year | Cross-check against database records |
| Ghost citations | References listed but never cited in text | Audit reference list against in-text citations |

## 3. Dual-Use Assessment

### Screening Questions
1. Could this research be used to harm individuals or communities?
2. Does it reveal vulnerabilities that could be exploited?
3. Could it be used to develop surveillance or control mechanisms?
4. Does it provide information that could be weaponized?
5. Could it be used to discriminate against specific groups?

### Risk Levels and Responses

| Level | Action Required |
|-------|----------------|
| None | No additional action |
| Low | Brief note in limitations |
| Moderate | Responsible Use statement in report |
| High | Prominent warning + limited distribution recommendation |
| Critical | Do not publish without institutional ethics review |

### Responsible Use Statement Template
```
Responsible Use: This research is intended for [stated purpose]. The authors
acknowledge that findings related to [sensitive area] could potentially be
applied in ways not intended by this research. Users of this research are
urged to consider the ethical implications of their applications and to
prioritize [specific ethical principle].
```

## 4. Fair Representation

### Balanced Treatment Checklist
- [ ] Multiple perspectives on contested issues are presented
- [ ] Minority/dissenting viewpoints are not dismissed without engagement
- [ ] Subjects and communities are described accurately
- [ ] Language is respectful and non-stigmatizing
- [ ] Cultural context is acknowledged where relevant
- [ ] Power dynamics are considered (who is studied vs. who studies)
- [ ] Geographic and cultural diversity in sources

### Sensitive Topics
- Indigenous knowledge: Respect OCAP principles (Ownership, Control, Access, Possession)
- Disability: Person-first language unless community prefers identity-first
- Gender/sexuality: Use inclusive, current terminology
- Race/ethnicity: Use preferred terminology of the communities discussed
- Socioeconomic status: Avoid deficit framing
- Mental health: Avoid stigmatizing language

### Representation Audit Questions
1. Whose voices are centered? Whose are missing?
2. Are communities described on their own terms?
3. Is there implicit bias in the framing?
4. Would the subjects/communities recognize themselves in this description?

## 5. Data Ethics

### Data Source Ethics
- [ ] All data sources are legal to use
- [ ] Public data: Confirm public domain or appropriate license
- [ ] Licensed data: Usage complies with license terms
- [ ] Scraped data: Complies with robots.txt and terms of service
- [ ] Personal data: GDPR/privacy law compliance (if applicable)
- [ ] Institutional data: Authorized access confirmed

### Privacy Protection
- [ ] No personally identifiable information (PII) without consent
- [ ] Aggregated data used where possible
- [ ] Small-N groups protected from identification
- [ ] Institutional identities protected when not public
- [ ] Data retention/deletion plan (if primary data collected)

### AI-Specific Data Concerns
- [ ] AI training data biases acknowledged
- [ ] AI knowledge cutoff date noted
- [ ] AI-generated data clearly labeled as such
- [ ] No circular citation (AI cites AI-generated content)

## 6. Conflict of Interest

### Types to Assess
- [ ] Financial: Funding source, consulting relationships
- [ ] Institutional: Author evaluating own institution
- [ ] Intellectual: Author defending own prior work
- [ ] Personal: Relationships with subjects/stakeholders
- [ ] Political: Government-funded research on government policy
- [ ] Commercial: Industry connections or product interests
- [ ] AI-specific: AI tool company influence on research design

### Disclosure Requirement
Any identified conflict must be disclosed in the report, with an assessment of whether it could have influenced the findings.

## 7. Reproducibility Ethics

### Documentation Requirements
- [ ] Search strategies documented (databases, terms, dates)
- [ ] Inclusion/exclusion criteria documented
- [ ] Analytical methods described in replicable detail
- [ ] AI prompts/instructions documented (if relevant)
- [ ] Data processing steps documented
- [ ] Code/scripts shared (if applicable)

### Reproducibility Statement Template
```
Reproducibility: The search strategy, inclusion criteria, and analytical
methods used in this research are documented in [section/appendix]. The
AI-assisted components used [specific prompts/parameters]. Researchers
wishing to replicate or extend this work should note [relevant limitations
or conditions].
```

## 8. Human Subjects Ethics

### 8.1 人類受試者判定

- [ ] 研究是否蒐集、使用、或分析人類相關資料？
- [ ] 若是，資料是否可辨識個人身分？
- [ ] 若資料為已公開去識別化資料，是否向 IRB 確認免審資格？

### 8.2 IRB 審查等級

| 審查等級 | 適用條件 | 審查時程 |
|----------|---------|---------|
| **免除審查（Exempt）** | 公開資料、去識別化資料、匿名問卷（無敏感議題） | 1-2 週 |
| **簡易審查（Expedited）** | 最小風險、非弱勢群體、一般問卷/訪談 | 2-4 週 |
| **完整審查（Full Board）** | 高於最小風險、弱勢群體、敏感議題、欺騙手法 | 4-8 週 |

- [ ] 已判定適用的 IRB 審查等級
- [ ] 已將 IRB 審查時程納入研究計畫時程
- [ ] 研究者已完成研究倫理訓練（CITI 或同等課程）

### 8.3 知情同意

- [ ] 知情同意書包含研究名稱、目的、程序、風險、益處
- [ ] 明確說明參與的自願性（可隨時退出、不受懲罰）
- [ ] 提供研究者與 IRB 聯繫方式
- [ ] 特殊情境處理：
  - [ ] 線上問卷：電子同意（點選「我同意」）
  - [ ] 錄音/錄影：獨立勾選項目
  - [ ] 未成年人：法定代理人同意 + 受試者 assent
  - [ ] 原住民研究：部落知情同意 + 個人知情同意

### 8.4 數據脫敏

- [ ] 移除直接識別碼（姓名、學號、身分證號）
- [ ] 評估間接識別碼風險（系所 + 年級 + 性別組合）
- [ ] 小樣本辨識風險評估（小型系所可能反推個人）
- [ ] 質性引述移除可辨識細節
- [ ] 資料儲存加密與存取權限控管
- [ ] 訂定資料保存期限與銷毀程序

### 8.5 弱勢群體保護

| 群體 | 額外保護措施 |
|------|------------|
| **未成年人** | 法定代理人同意 + 適齡 assent form |
| **身心障礙者** | 評估同意能力、提供無障礙同意程序 |
| **學生（研究者為教師）** | 避免權力關係影響自願性、第三方代為招募 |
| **原住民** | 部落諮詢與同意、尊重 OCAP 原則 |
| **經濟弱勢** | 報酬不得構成不當誘因 |
| **受刑人** | 額外 IRB 審查、確保非強制參與 |

- [ ] 已識別研究涉及的弱勢群體
- [ ] 已規劃對應的額外保護措施
- [ ] IRB 審查等級已考量弱勢群體因素

> 詳細 IRB 決策樹與台灣流程：見 `references/irb_decision_tree.md`

---

## Quick Audit Checklist (Final Gate)

Before delivery, confirm ALL items:

- [ ] AI disclosure present and accurate
- [ ] All references spot-checked (minimum 20%)
- [ ] No fabricated citations detected
- [ ] Dual-use assessment completed
- [ ] Fair representation reviewed
- [ ] Data sources legally and ethically used
- [ ] Conflicts of interest disclosed
- [ ] Reproducibility documentation provided
- [ ] Writing is inclusive and respectful
- [ ] Report benefits stated audience without causing foreseeable harm
- [ ] 涉及人類受試者的研究是否已規劃 IRB 審查？
