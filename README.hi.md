<div align="center">

# Academic Research Graphify (ARG)

**आपका AI-संचालित शैक्षणिक अनुसंधान सहपायलट**

[![Version](https://img.shields.io/badge/version-v4.0.0-blue)](#)
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](https://opensource.org/licenses/MIT)
[![Agents](https://img.shields.io/badge/agents-38-purple)](#-विशेषताएं)
[![Skills](https://img.shields.io/badge/skills-4-orange)](#-कौशल-और-मोड)
[![Modes](https://img.shields.io/badge/modes-26-red)](#-कौशल-और-मोड)

[English](README.md) | [繁體中文](README.zh-TW.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Português](README.pt-BR.md) | [العربية](README.ar.md) | [Русский](README.ru.md)

---

**38 विशेष AI एजेंट**, **4 कौशल** और **26 मोड** में — आपके शोध को विचार से प्रकाशन तक ले जाते हैं।
**किसी भी AI कोडिंग एजेंट** के साथ संगत — Windsurf, Cursor, Claude Code, GitHub Copilot, Cline, Aider, Continue आदि।

[त्वरित शुरुआत](#-त्वरित-शुरुआत) | [विशेषताएं](#-विशेषताएं) | [आर्किटेक्चर](docs/ARCHITECTURE.md) | [सेटअप गाइड](UNIVERSAL_SETUP.md)

</div>

---

## ARG क्यों?

> **AI आपका सहपायलट है, पायलट नहीं।** ARG आपका पेपर नहीं लिखता। यह कठिन काम संभालता है — संदर्भ खोजना, उद्धरण फॉर्मेट करना, डेटा सत्यापित करना, तार्किक सुसंगतता जांचना — ताकि आप उन चीजों पर ध्यान केंद्रित कर सकें जिनके लिए वास्तव में आपके दिमाग की जरूरत है।

| समस्या | ARG का समाधान |
|--------|-------------|
| उद्धरण मतिभ्रम | Semantic Scholar API सत्यापन + अखंडता द्वार |
| फ्रेम-लॉक | डेविल्स एडवोकेट + रियायत सीमा प्रोटोकॉल |
| चापलूसी | चापलूसी-विरोधी स्कोरिंग (रियायत से पहले 1-5 पैमाना) |
| समयपूर्व अभिसरण | इरादा पहचान + संवाद स्वास्थ्य निगरानी |
| पद्धति गढ़ना | Stage 2.5 और 4.5 पर 7-मोड ब्लॉकिंग चेकलिस्ट |

---

## त्वरित शुरुआत

```bash
git clone https://github.com/Masqiller/ARG-RESEARCHER-V4.1.git ~/ARG-Researcher
```

अपने IDE में रेपो खोलें। कॉन्फ़िगरेशन फ़ाइलें स्वचालित रूप से पहचानी जाती हैं:

| एजेंट | कॉन्फ़िग | कमांड |
|:-------|:---------|:------|
| **Google Antigravity** | `.agents/rules/arg-instructions.md` + `.agents/workflows/arg-*.md` | Agent Manager में नेटिव `/arg-*` कमांड |
| **Windsurf** | `.windsurf/workflows/arg-*.md` | नेटिव `/arg-*` वर्कफ़्लो |
| **Cursor** | `.cursor/rules/arg-instructions.mdc` | चैट में `/arg-*` |
| **Claude Code** | `.claude/CLAUDE.md` + `commands/` | नेटिव `/arg-*` कमांड |
| **GitHub Copilot** | `.github/copilot-instructions.md` | चैट में `/arg-*` |
| **अन्य** | `.ai/instructions.md` | चैट में `/arg-*` |

**परीक्षण:** `/arg-plan` चलाएं और अपने पेपर का वर्णन करें।

---

## विशेषताएं

<table>
<tr>
<td width="50%">

### गहन अनुसंधान
*13 एजेंट | 7 मोड*

- सुकरात शैली गाइडेड अन्वेषण
- PRISMA व्यवस्थित समीक्षा
- Semantic Scholar API सत्यापन
- इरादा पहचान
- संवाद स्वास्थ्य निगरानी

</td>
<td width="50%">

### शैक्षणिक पेपर
*13 एजेंट | 11 मोड*

- शैली अंशांकन (आपकी आवाज सीखता है)
- लेखन गुणवत्ता जांच
- LaTeX सुदृढ़ीकरण (APA 7.0, IEEE, Chicago)
- विज़ुअलाइज़ेशन एजेंट
- **डायग्राम मास्टर एजेंट** (TikZ/PGFPlots/Mermaid, 13 श्रेणियां)
- संशोधन कोचिंग और R&R प्रतिक्रिया

</td>
</tr>
<tr>
<td width="50%">

### पेपर समीक्षक
*7 एजेंट | 6 मोड*

- EIC + 3 गतिशील समीक्षक + डेविल्स एडवोकेट
- 0-100 गुणवत्ता रूब्रिक
- Sprint Contract (ब्लाइंड चरण 1 + चरण 2)
- अंशांकन मोड (FNR/FPR मापें)

</td>
<td width="50%">

### शैक्षणिक पाइपलाइन
*10-चरण ऑर्केस्ट्रेटर*

- उपयोगकर्ता पुष्टि के साथ अनुकूली चेकपॉइंट
- Stage 2.5 और 4.5 अखंडता द्वार (अनिवार्य)
- Material Passport
- 6-आयामी सहयोग गुणवत्ता मूल्यांकन (1-100)

</td>
</tr>
</table>

---

## `/arg-*` कमांड

| कमांड | विवरण |
|:------|:------|
| `/arg-full` | पूर्ण पाइपलाइन: अनुसंधान → लेखन → समीक्षा → संशोधन → अंतिमीकरण |
| `/arg-plan` | सुकरात शैली अध्याय-दर-अध्याय योजना |
| `/arg-outline` | विस्तृत रूपरेखा + साक्ष्य मानचित्र |
| `/arg-abstract` | द्विभाषी सार + कीवर्ड |
| `/arg-revision` | संशोधित पांडुलिपि + R&R उत्तर |
| `/arg-lit-review` | पेपर प्रारूप में एनोटेटेड ग्रंथसूची |
| `/arg-format-convert` | LaTeX / DOCX / PDF / Markdown में रूपांतरण |
| `/arg-revision-coach` | संशोधन रोडमैप + उत्तर पत्र ढांचा |
| `/arg-citation-check` | उद्धरण त्रुटि रिपोर्ट |
| `/arg-disclosure` | AI उपयोग प्रकटीकरण वक्तव्य |
| `/arg-diagram` | संरचनात्मक डायग्राम निर्माण (TikZ / Mermaid / PGFPlots) |

---

## अनुशंसित वर्कफ़्लो

सर्वोत्तम गुणवत्ता के लिए ये चार चरण क्रमशः चलाएं:

```
चरण 1 — गहन शोध
  /deep-research
  → उत्पन्न: एनोटेटेड ग्रंथसूची, संश्लेषण रिपोर्ट, RQ सार

         ↓  साहित्य + RQ अगले चरण को दें

चरण 2 — पेपर नियोजन
  /arg-plan
  → उत्पन्न: अध्याय योजना, INSIGHT संग्रह, डायग्राम योजना

         ↓  अध्याय योजना अगले चरण को दें

चरण 3 — योजना समीक्षा
  /academic-paper-reviewer  (quick या guided मोड)
  → उत्पन्न: संरचनात्मक फीडबैक, तर्क अंतराल विश्लेषण, तार्किक तनाव परीक्षण

         ↓  फीडबैक शामिल करें, फिर पाइपलाइन चलाएं

चरण 4 — पूर्ण पाइपलाइन
  /arg-full
  → उत्पन्न: पूर्ण मसौदा → अखंडता गेट → समीक्षा → संशोधन → अंतिम आउटपुट
```

> **शॉर्टकट:** यदि समय कम है, तो सीधे `/arg-full` चलाएं — इसमें सभी 10 चरण अंदर मौजूद हैं।

---

## लाइसेंस

[MIT लाइसेंस](LICENSE) के तहत लाइसेंस प्राप्त। वाणिज्यिक उपयोग सहित स्वतंत्र रूप से उपयोग, संशोधन और वितरण योग्य। [CONTRIBUTORS.md](CONTRIBUTORS.md) देखें।
