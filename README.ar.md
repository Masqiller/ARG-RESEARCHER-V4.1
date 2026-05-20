<div align="center">

# Academic Research Graphify (ARG)

**مساعدك البحثي الأكاديمي المدعوم بالذكاء الاصطناعي**

[![Version](https://img.shields.io/badge/version-v4.0.0-blue)](#)
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](https://opensource.org/licenses/MIT)
[![Agents](https://img.shields.io/badge/agents-38-purple)](#-الميزات)
[![Skills](https://img.shields.io/badge/skills-4-orange)](#-المهارات-والأوضاع)
[![Modes](https://img.shields.io/badge/modes-26-red)](#-المهارات-والأوضاع)

[English](README.md) | [繁體中文](README.zh-TW.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Português](README.pt-BR.md) | [हिन्दी](README.hi.md) | [Русский](README.ru.md)

---

**38 وكيل ذكاء اصطناعي متخصص** عبر **4 مهارات** و**26 وضعاً** لنقل بحثك من الفكرة إلى النشر.
متوافق مع **أي وكيل برمجة بالذكاء الاصطناعي** — Windsurf وCursor وClaude Code وGitHub Copilot وCline وAider وContinue والمزيد.

[البدء السريع](#-البدء-السريع) | [الميزات](#-الميزات) | [البنية](docs/ARCHITECTURE.md) | [دليل الإعداد](UNIVERSAL_SETUP.md)

</div>

---

## لماذا ARG؟

> **الذكاء الاصطناعي هو مساعد الطيار وليس الطيار.** ARG لن يكتب ورقتك البحثية. إنه يتعامل مع العمل الشاق — البحث عن المراجع وتنسيق الاستشهادات والتحقق من البيانات وفحص الاتساق المنطقي — حتى تتمكن من التركيز على ما يتطلب فعلاً عقلك.

| المشكلة | حل ARG |
|---------|--------|
| هلوسات الاستشهاد | التحقق عبر Semantic Scholar API + بوابات النزاهة |
| قفل الإطار | محامي الشيطان + بروتوكول عتبة التنازل |
| التملق | تسجيل مضاد للتملق (مقياس 1-5 قبل أي تنازل) |
| التقارب المبكر | كشف النية + مراقبة صحة الحوار |
| تلفيق المنهجية | قائمة فحص 7 أوضاع في Stage 2.5 و4.5 |

---

## البدء السريع

```bash
git clone https://github.com/Masqiller/ARG-RESEARCHER-V4.1.git ~/ARG-Researcher
```

افتح المستودع في بيئة التطوير الخاصة بك. يتم اكتشاف ملفات التكوين تلقائياً:

| الوكيل | التكوين | الأوامر |
|:-------|:--------|:--------|
| **Google Antigravity** | `.agents/rules/arg-instructions.md` + `.agents/workflows/arg-*.md` | أوامر `/arg-*` أصلية في Agent Manager |
| **Windsurf** | `.windsurf/workflows/arg-*.md` | سير عمل أصلية `/arg-*` |
| **Cursor** | `.cursor/rules/arg-instructions.mdc` | `/arg-*` في المحادثة |
| **Claude Code** | `.claude/CLAUDE.md` + `commands/` | أوامر أصلية `/arg-*` |
| **GitHub Copilot** | `.github/copilot-instructions.md` | `/arg-*` في المحادثة |
| **غيره** | `.ai/instructions.md` | `/arg-*` في المحادثة |

**اختبار:** نفّذ `/arg-plan` وصف ورقة بحثية تعمل عليها.

---

## الميزات

<table>
<tr>
<td width="50%">

### البحث المعمق
*13 وكيل | 7 أوضاع*

- استكشاف سقراطي موجه
- مراجعة منهجية PRISMA
- التحقق عبر Semantic Scholar API
- كشف النية (استكشافي vs. موجه نحو الهدف)
- مراقبة صحة الحوار

</td>
<td width="50%">

### الورقة الأكاديمية
*13 وكيل | 11 وضعاً*

- معايرة الأسلوب (يتعلم صوتك)
- فحص جودة الكتابة
- تقوية LaTeX (APA 7.0, IEEE, Chicago)
- وكيل التصور البصري
- **وكيل الرسوم البيانية الرئيسي** (TikZ/PGFPlots/Mermaid, 13 فئة)
- تدريب على المراجعة واستجابة R&R

</td>
</tr>
<tr>
<td width="50%">

### مراجع الأوراق
*7 وكلاء | 6 أوضاع*

- رئيس التحرير + 3 مراجعين ديناميكيين + محامي الشيطان
- معايير جودة 0-100
- Sprint Contract (المرحلة 1 عمياء + المرحلة 2)
- وضع المعايرة (قياس FNR/FPR)

</td>
<td width="50%">

### خط الأنابيب الأكاديمي
*منسق من 10 مراحل*

- نقاط تفتيش تكيفية مع تأكيد المستخدم
- بوابات نزاهة في Stage 2.5 و4.5 (إلزامية)
- Material Passport
- تقييم جودة التعاون 6 أبعاد (1-100)

</td>
</tr>
</table>

---

## أوامر `/arg-*`

| الأمر | الوصف |
|:------|:------|
| `/arg-full` | خط أنابيب كامل: بحث → كتابة → مراجعة → تعديل → إنهاء |
| `/arg-plan` | تخطيط سقراطي فصلاً بفصل |
| `/arg-outline` | مخطط تفصيلي + خريطة أدلة |
| `/arg-abstract` | ملخص ثنائي اللغة + كلمات مفتاحية |
| `/arg-revision` | مسودة معدلة + ردود R&R |
| `/arg-lit-review` | ببليوغرافيا مشروحة بتنسيق ورقة بحثية |
| `/arg-format-convert` | تحويل إلى LaTeX / DOCX / PDF / Markdown |
| `/arg-revision-coach` | خارطة طريق المراجعة + هيكل رسالة الرد |
| `/arg-citation-check` | تقرير أخطاء الاستشهاد |
| `/arg-disclosure` | بيان استخدام الذكاء الاصطناعي |
| `/arg-diagram` | إنشاء مخطط بياني هيكلي (TikZ / Mermaid / PGFPlots) |

---

## سير العمل الموصى به

لأفضل جودة، نفّذ هذه الخطوات الأربع بالترتيب:

```
الخطوة 1 — بحث عميق
  /deep-research
  → ينتج: بيبليوغرافيا موضّحة، تقرير توليفي، ملخص RQ

         ↓  نقل المراجع + RQ إلى الخطوة التالية

الخطوة 2 — تخطيط الورقة
  /arg-plan
  → ينتج: خطة الفصول، مجموعة INSIGHT، خطة الرسوم

         ↓  نقل خطة الفصول إلى الخطوة التالية

الخطوة 3 — مراجعة الخطة
  /academic-paper-reviewer  (وضع quick أو guided)
  → ينتج: ملاحظات هيكلية، تحليل ثغرات الحجج، اختبار ضغط منطقي

         ↓  ادمج الملاحظات، ثم شغّل خط الأنابيب الكامل

الخطوة 4 — خط الأنابيب الكامل
  /arg-full
  → ينتج: مسودة كاملة → بوابة نزاهة → مراجعة → تعديل → نتيجة نهائية
```

> **اختصار:** إذا كان الوقت ضيقاً، شغّل `/arg-full` مباشرةً — يحتوي داخلياً على جميع المراحل العشر.

---

## الرخصة

مرخص بموجب [رخصة MIT](LICENSE). حر الاستخدام والتعديل والتوزيع بما في ذلك الاستخدام التجاري. انظر [CONTRIBUTORS.md](CONTRIBUTORS.md).
