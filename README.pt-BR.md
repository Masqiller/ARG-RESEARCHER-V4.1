<div align="center">

# Academic Research Graphify (ARG)

**Seu copiloto de pesquisa academica com IA**

[![Version](https://img.shields.io/badge/version-v4.0.0-blue)](#)
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](https://opensource.org/licenses/MIT)
[![Agents](https://img.shields.io/badge/agents-38-purple)](#-funcionalidades)
[![Skills](https://img.shields.io/badge/skills-4-orange)](#-habilidades-e-modos)
[![Modes](https://img.shields.io/badge/modes-26-red)](#-habilidades-e-modos)

[English](README.md) | [繁體中文](README.zh-TW.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [हिन्दी](README.hi.md) | [العربية](README.ar.md) | [Русский](README.ru.md)

---

**38 agentes de IA especializados** em **4 habilidades** e **26 modos** para levar sua pesquisa da ideia a publicacao.
Compativel com **qualquer agente de IA** — Windsurf, Cursor, Claude Code, GitHub Copilot, Cline, Aider, Continue e mais.

[Inicio rapido](#-inicio-rapido) | [Funcionalidades](#-funcionalidades) | [Arquitetura](docs/ARCHITECTURE.md) | [Guia de configuracao](UNIVERSAL_SETUP.md)

</div>

---

## Por que ARG?

> **IA e seu copiloto, nao o piloto.** ARG nao escreve seu artigo. Ele cuida do trabalho pesado — buscar referencias, formatar citacoes, verificar dados, checar consistencia logica — para que voce se concentre no que realmente precisa do seu cerebro.

| Problema | Solucao do ARG |
|----------|---------------|
| Alucinacoes de citacao | Verificacao Semantic Scholar API + portas de integridade |
| Bloqueio de quadro | Advogado do Diabo com protocolo de limiar de concessao |
| Bajulacao | Pontuacao anti-bajulacao (escala 1-5 antes de conceder) |
| Convergencia prematura | Deteccao de intencao + monitoramento de saude do dialogo |
| Fabricacao metodologica | Checklist de 7 modos no Stage 2.5 e 4.5 |

---

## Inicio rapido

```bash
git clone https://github.com/Masqiller/ARG-RESEARCHER-V4.1.git ~/ARG-Researcher
```

Abra o repositorio na sua IDE. Arquivos de configuracao sao detectados automaticamente:

| Agente | Configuracao | Comandos |
|:-------|:------------|:---------|
| **Google Antigravity** | `.agents/rules/arg-instructions.md` + `.agents/workflows/arg-*.md` | Comandos `/arg-*` nativos no Agent Manager |
| **Windsurf** | `.windsurf/workflows/arg-*.md` | Workflows nativos `/arg-*` |
| **Cursor** | `.cursor/rules/arg-instructions.mdc` | `/arg-*` no chat |
| **Claude Code** | `.claude/CLAUDE.md` + `commands/` | Comandos nativos `/arg-*` |
| **GitHub Copilot** | `.github/copilot-instructions.md` | `/arg-*` no chat |
| **Outro** | `.ai/instructions.md` | `/arg-*` no chat |

**Teste:** Execute `/arg-plan` e descreva um artigo em que esta trabalhando.

---

## Funcionalidades

<table>
<tr>
<td width="50%">

### Pesquisa Profunda
*13 agentes | 7 modos*

- Exploracao guiada socratica
- Revisao sistematica PRISMA
- Verificacao Semantic Scholar API
- Deteccao de intencao
- Monitoramento de saude do dialogo

</td>
<td width="50%">

### Artigo Academico
*13 agentes | 11 modos*

- Calibracao de estilo (aprende sua voz)
- Controle de qualidade de escrita
- Endurecimento LaTeX (APA 7.0, IEEE, Chicago)
- Agente de visualizacao
- **Agente Mestre de Diagramas** (TikZ/PGFPlots/Mermaid, 13 categorias)
- Coaching de revisao e resposta R&R

</td>
</tr>
<tr>
<td width="50%">

### Revisor de Artigos
*7 agentes | 6 modos*

- EIC + 3 revisores dinamicos + Advogado do Diabo
- Rubricas de qualidade 0-100
- Sprint Contract (Fase 1 cega + Fase 2)
- Modo calibracao (medir FNR/FPR)

</td>
<td width="50%">

### Pipeline Academico
*Orquestrador de 10 estagios*

- Checkpoints adaptativos com confirmacao do usuario
- Portas de integridade no Stage 2.5 e 4.5 (obrigatorias)
- Material Passport
- Avaliacao de colaboracao de 6 dimensoes (1-100)

</td>
</tr>
</table>

---

## Comandos `/arg-*`

| Comando | O que faz |
|:--------|:----------|
| `/arg-full` | Pipeline completo: pesquisa → escrita → revisao → correcao → finalizacao |
| `/arg-plan` | Planejamento socratico capitulo por capitulo |
| `/arg-outline` | Esboço detalhado + mapa de evidencias |
| `/arg-abstract` | Resumo bilingue + palavras-chave |
| `/arg-revision` | Rascunho revisado + respostas R&R |
| `/arg-lit-review` | Bibliografia anotada em formato de artigo |
| `/arg-format-convert` | Converter para LaTeX / DOCX / PDF / Markdown |
| `/arg-revision-coach` | Roteiro de revisao + esqueleto de carta de resposta |
| `/arg-citation-check` | Relatorio de erros de citacao |
| `/arg-disclosure` | Declaracao de uso de IA |
| `/arg-diagram` | Geracao de diagrama estrutural (TikZ / Mermaid / PGFPlots) |

---

## Fluxo de trabalho recomendado

Para a melhor qualidade, execute estes quatro passos em ordem:

```
Passo 1 — Pesquisa profunda
  /deep-research
  → Produz: Bibliografia anotada, Relatorio de sintese, Resumo da RQ

         ↓  Passar literatura + RQ para o proximo passo

Passo 2 — Planejamento do artigo
  /arg-plan
  → Produz: Plano de capitulos, Colecao INSIGHT, Plano de diagramas

         ↓  Passar plano de capitulos para o proximo passo

Passo 3 — Revisao do plano
  /academic-paper-reviewer  (modo quick ou guided)
  → Produz: Feedback estrutural, analise de lacunas, teste de estresse logico

         ↓  Incorporar feedback, depois executar o pipeline completo

Passo 4 — Pipeline completo
  /arg-full
  → Produz: Rascunho completo → porta de integridade → revisao → correcao → resultado final
```

> **Atalho:** Se estiver com pressa, execute `/arg-full` diretamente — ele contem as 10 etapas internamente.

---

## Licenca

Licenciado sob a [Licenca MIT](LICENSE). Livre para usar, modificar e distribuir. Ver [CONTRIBUTORS.md](CONTRIBUTORS.md).
