<div align="center">

# Academic Research Graphify (ARG)

**Dein KI-gesteuerter akademischer Forschungs-Copilot**

[![Version](https://img.shields.io/badge/version-v4.0.0-blue)](#)
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](https://opensource.org/licenses/MIT)
[![Agents](https://img.shields.io/badge/agents-38-purple)](#-funktionen)
[![Skills](https://img.shields.io/badge/skills-4-orange)](#-faehigkeiten-und-modi)
[![Modes](https://img.shields.io/badge/modes-26-red)](#-faehigkeiten-und-modi)

[English](README.md) | [繁體中文](README.zh-TW.md) | [Español](README.es.md) | [Français](README.fr.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Português](README.pt-BR.md) | [हिन्दी](README.hi.md) | [العربية](README.ar.md) | [Русский](README.ru.md)

---

**38 spezialisierte KI-Agenten** in **4 Faehigkeiten** und **26 Modi** — von der Idee bis zur Veroeffentlichung.
Kompatibel mit **jedem KI-Coding-Agenten** — Windsurf, Cursor, Claude Code, GitHub Copilot, Cline, Aider, Continue u.v.m.

[Schnellstart](#-schnellstart) | [Funktionen](#-funktionen) | [Architektur](docs/ARCHITECTURE.md) | [Einrichtung](UNIVERSAL_SETUP.md)

</div>

---

## Warum ARG?

> **KI ist dein Copilot, nicht der Pilot.** ARG schreibt dein Paper nicht. Es erledigt die Routinearbeit — Referenzen suchen, Zitate formatieren, Daten verifizieren, logische Konsistenz pruefen — damit du dich auf das konzentrieren kannst, was wirklich dein Gehirn braucht.

| Problem | ARGs Loesung |
|---------|-------------|
| Zitat-Halluzinationen | Semantic Scholar API-Verifizierung + Integritaets-Gates |
| Frame-Lock | Advocatus Diaboli mit Konzessions-Schwellenwert-Protokoll |
| Sykophanz | Anti-Sykophanz-Bewertung (1-5 Skala vor jeder Konzession) |
| Vorzeitige Konvergenz | Absichtserkennung + Dialog-Gesundheitsmonitoring |
| Methodenfabrikation | 7-Modi-Blockliste bei Stage 2.5 & 4.5 |

---

## Schnellstart

```bash
git clone https://github.com/Masqiller/ARG-RESEARCHER-V4.1.git ~/ARG-Researcher
```

Oeffne das Repository in deiner IDE. Konfigurationsdateien werden automatisch erkannt:

| Agent | Konfiguration | Befehle |
|:------|:-------------|:--------|
| **Google Antigravity** | `.agents/rules/arg-instructions.md` + `.agents/workflows/arg-*.md` | Native `/arg-*` im Agent Manager |
| **Windsurf** | `.windsurf/workflows/arg-*.md` | Native `/arg-*` Workflows |
| **Cursor** | `.cursor/rules/arg-instructions.mdc` | `/arg-*` im Chat |
| **Claude Code** | `.claude/CLAUDE.md` + `commands/` | Native `/arg-*` Befehle |
| **GitHub Copilot** | `.github/copilot-instructions.md` | `/arg-*` im Chat |
| **Andere** | `.ai/instructions.md` | `/arg-*` im Chat |

**Teste es:** Fuehre `/arg-plan` aus und beschreibe ein Paper, an dem du arbeitest.

---

## Funktionen

<table>
<tr>
<td width="50%">

### Tiefenforschung
*13 Agenten | 7 Modi*

- Sokratische gefuehrte Exploration
- PRISMA systematische Uebersicht
- Semantic Scholar API-Verifizierung
- Absichtserkennung
- Dialog-Gesundheitsmonitoring
- Cross-Model Advocatus Diaboli (optional)

</td>
<td width="50%">

### Akademisches Paper
*13 Agenten | 11 Modi*

- Stil-Kalibrierung (lernt deine Stimme)
- Schreibqualitaetskontrolle
- LaTeX-Haertung (APA 7.0, IEEE, Chicago)
- Visualisierungsagent
- **Diagramm-Master-Agent** (TikZ/PGFPlots/Mermaid, 13 Kategorien)
- Revisions-Coaching & R&R-Antwort
- Zitat-Format-Konvertierung (5 Formate)

</td>
</tr>
<tr>
<td width="50%">

### Paper-Reviewer
*7 Agenten | 6 Modi*

- EIC + 3 dynamische Reviewer + Advocatus Diaboli
- 0-100 Qualitaetsrubriken
- Sprint Contract (blinde Phase 1 + Phase 2)
- Kalibrierungsmodus (FNR/FPR messen)

</td>
<td width="50%">

### Akademische Pipeline
*10-Stufen-Orchestrator*

- Adaptive Checkpoints mit Benutzerbestaetigung
- Integritaets-Gates bei Stage 2.5 & 4.5 (obligatorisch)
- Material Passport mit Behauptungsverifizierung
- 6-Dimensionen-Kollaborationsbewertung (1-100)

</td>
</tr>
</table>

---

## `/arg-*` Befehle

| Befehl | Beschreibung |
|:-------|:-------------|
| `/arg-full` | Vollstaendige Pipeline: Forschung → Schreiben → Review → Revision → Finalisierung |
| `/arg-plan` | Sokratische Kapitel-fuer-Kapitel-Planung |
| `/arg-outline` | Detaillierte Gliederung + Evidenzkarte |
| `/arg-abstract` | Zweisprachige Zusammenfassung + Schluesselwoerter |
| `/arg-revision` | Ueberarbeiteter Entwurf + R&R-Antworten |
| `/arg-lit-review` | Annotierte Bibliographie im Paper-Format |
| `/arg-format-convert` | Konvertierung in LaTeX / DOCX / PDF / Markdown |
| `/arg-revision-coach` | Revisions-Roadmap + Antwortbrief-Skelett |
| `/arg-citation-check` | Zitierfehlerbericht |
| `/arg-disclosure` | KI-Nutzungserklaerung |
| `/arg-diagram` | Strukturdiagramm-Generierung (TikZ / Mermaid / PGFPlots) |

---

## Empfohlener Workflow

Fuer die beste Qualitaet diese vier Schritte in Reihenfolge ausfuehren:

```
Schritt 1 — Tiefenforschung
  /deep-research
  → Ergebnis: Annotierte Bibliographie, Synthesebericht, RQ-Zusammenfassung

         ↓  Literatur + RQ an naechsten Schritt weitergeben

Schritt 2 — Papierplanung
  /arg-plan
  → Ergebnis: Kapitelplan, INSIGHT-Sammlung, Diagrammplan

         ↓  Kapitelplan an naechsten Schritt weitergeben

Schritt 3 — Planpruefung
  /academic-paper-reviewer  (quick oder guided Modus)
  → Ergebnis: Strukturelles Feedback, Argumentationsluecken, Logik-Stresstest

         ↓  Feedback einarbeiten, dann vollstaendige Pipeline starten

Schritt 4 — Vollstaendige Pipeline
  /arg-full
  → Ergebnis: Vollstaendiger Entwurf → Integritaetscheck → Review → Revision → Endergebnis
```

> **Abkuerzung:** Wenn du wenig Zeit hast, starte direkt mit `/arg-full` — es enthaelt intern alle 10 Stufen.

---

## Lizenz

Lizenziert unter der [MIT-Lizenz](LICENSE). Frei nutzbar, aenderbar und verteilbar. Siehe [CONTRIBUTORS.md](CONTRIBUTORS.md).
