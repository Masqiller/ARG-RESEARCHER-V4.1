<div align="center">

# Academic Research Graphify (ARG)

**Votre copilote IA pour la recherche academique**

[![Version](https://img.shields.io/badge/version-v4.0.0-blue)](#)
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](https://opensource.org/licenses/MIT)
[![Agents](https://img.shields.io/badge/agents-37-purple)](#-fonctionnalites)
[![Skills](https://img.shields.io/badge/skills-4-orange)](#-competences-et-modes)
[![Modes](https://img.shields.io/badge/modes-25-red)](#-competences-et-modes)

[English](README.md) | [繁體中文](README.zh-TW.md) | [Español](README.es.md) | [Deutsch](README.de.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Português](README.pt-BR.md) | [हिन्दी](README.hi.md) | [العربية](README.ar.md) | [Русский](README.ru.md)

---

**37 agents IA specialises** dans **4 competences** et **25 modes** pour mener votre recherche de l'idee a la publication.
Compatible avec **tout agent IA** — Windsurf, Cursor, Claude Code, GitHub Copilot, Cline, Aider, Continue et plus.

[Demarrage rapide](#-demarrage-rapide) | [Fonctionnalites](#-fonctionnalites) | [Architecture](docs/ARCHITECTURE.md) | [Guide d'installation](UNIVERSAL_SETUP.md)

</div>

---

## Pourquoi ARG ?

> **L'IA est votre copilote, pas le pilote.** ARG n'ecrit pas votre article. Il gere le travail fastidieux — recherche de references, formatage des citations, verification des donnees, controle de coherence logique — pour que vous vous concentriez sur ce qui necessite reellement votre cerveau.

| Probleme | Solution ARG |
|----------|-------------|
| Hallucinations de citations | Verification API Semantic Scholar + portes d'integrite |
| Verrouillage de cadre | Avocat du Diable avec protocole de seuil de concession |
| Servilite | Notation anti-servilite (echelle 1-5 avant concession) |
| Convergence prematuree | Detection d'intention + surveillance de sante du dialogue |
| Fabrication methodologique | Liste de verification a 7 modes aux Stages 2.5 et 4.5 |
| Affirmations inverifiables | Protocole de citation a trois couches |

---

## Demarrage rapide

```bash
git clone https://github.com/Masqiller/ARG-Researcher.git ~/ARG-Researcher
```

Ouvrez le depot dans votre IDE. Les fichiers de configuration sont detectes automatiquement :

| Agent | Configuration | Commandes |
|:------|:-------------|:----------|
| **Windsurf** | `.windsurf/workflows/arg-*.md` | Workflows natifs `/arg-*` |
| **Cursor** | `.cursor/rules/arg-instructions.mdc` | `/arg-*` dans le chat |
| **Claude Code** | `.claude/CLAUDE.md` + `commands/` | Commandes natives `/arg-*` |
| **GitHub Copilot** | `.github/copilot-instructions.md` | `/arg-*` dans le chat |
| **Autre** | `.ai/instructions.md` | `/arg-*` dans le chat |

**Testez :** Executez `/arg-plan` et decrivez un article sur lequel vous travaillez.

---

## Fonctionnalites

<table>
<tr>
<td width="50%">

### Recherche approfondie
*13 agents | 7 modes*

- Exploration guidee socratique
- Revue systematique PRISMA
- Verification API Semantic Scholar
- Detection d'intention
- Surveillance de sante du dialogue
- Avocat du Diable cross-model (optionnel)

</td>
<td width="50%">

### Article academique
*12 agents | 10 modes*

- Calibration de style (apprend votre voix)
- Controle qualite d'ecriture
- Durcissement LaTeX (APA 7.0, IEEE, Chicago)
- Agent de visualisation
- Coaching de revision et reponse R&R
- Conversion de format de citation (5 formats)

</td>
</tr>
<tr>
<td width="50%">

### Reviseur d'articles
*7 agents | 6 modes*

- EIC + 3 reviseurs dynamiques + Avocat du Diable
- Rubriques de qualite 0-100
- Sprint Contract (Phase 1 aveugle + Phase 2)
- Mode calibration (mesurer FNR/FPR)

</td>
<td width="50%">

### Pipeline academique
*Orchestrateur a 10 etapes*

- Points de controle adaptatifs
- Portes d'integrite aux Stages 2.5 et 4.5 (obligatoires)
- Material Passport avec verification des affirmations
- Evaluation de collaboration a 6 dimensions (1-100)

</td>
</tr>
</table>

---

## Commandes `/arg-*`

| Commande | Description |
|:---------|:-----------|
| `/arg-full` | Pipeline complet : recherche → ecriture → revision → correction → finalisation |
| `/arg-plan` | Planification socratique chapitre par chapitre |
| `/arg-outline` | Plan detaille + carte des preuves |
| `/arg-abstract` | Resume bilingue + mots-cles |
| `/arg-revision` | Brouillon revise + reponses R&R |
| `/arg-lit-review` | Bibliographie annotee en format article |
| `/arg-format-convert` | Convertir en LaTeX / DOCX / PDF / Markdown |
| `/arg-citation-check` | Rapport d'erreurs de citations |
| `/arg-disclosure` | Declaration d'utilisation de l'IA |

---

## Formats supportes

| Categorie | Options |
|:----------|:--------|
| **Styles de citation** | APA 7.0 (defaut), Chicago, MLA, IEEE, Vancouver |
| **Types d'article** | IMRaD, Revue de litterature, Analyse theorique, Etude de cas, Policy Brief |
| **Formats de sortie** | Markdown, LaTeX, DOCX (Pandoc), PDF (tectonic) |

---

## Licence

Sous [Licence MIT](LICENSE). Libre d'utilisation, modification et distribution. Voir [CONTRIBUTORS.md](CONTRIBUTORS.md).
