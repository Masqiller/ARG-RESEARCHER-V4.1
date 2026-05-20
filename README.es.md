<div align="center">

# Academic Research Graphify (ARG)

**Tu copiloto de investigacion academica con IA**

[![Version](https://img.shields.io/badge/version-v4.0.0-blue)](#)
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](https://opensource.org/licenses/MIT)
[![Agents](https://img.shields.io/badge/agents-38-purple)](#-el-equipo-de-agentes)
[![Skills](https://img.shields.io/badge/skills-4-orange)](#-habilidades-y-modos)
[![Modes](https://img.shields.io/badge/modes-26-red)](#-habilidades-y-modos)

[English](README.md) | [繁體中文](README.zh-TW.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Português](README.pt-BR.md) | [हिन्दी](README.hi.md) | [العربية](README.ar.md) | [Русский](README.ru.md)

---

**38 agentes de IA especializados** en **4 habilidades** y **26 modos** para llevar tu investigacion desde la idea hasta la publicacion.
Compatible con **cualquier agente de IA** — Windsurf, Cursor, Claude Code, GitHub Copilot, Cline, Aider, Continue y mas.

[Inicio rapido](#-inicio-rapido) | [Caracteristicas](#-caracteristicas) | [Arquitectura](docs/ARCHITECTURE.md) | [Guia de configuracion](UNIVERSAL_SETUP.md)

</div>

---

## Por que ARG?

> **La IA es tu copiloto, no el piloto.** ARG no escribe tu paper. Se encarga del trabajo pesado — buscar referencias, formatear citas, verificar datos, comprobar consistencia logica — para que te concentres en lo que realmente requiere tu cerebro.

| Problema | Solucion de ARG |
|----------|----------------|
| Alucinaciones de citas | Verificacion Semantic Scholar API + puertas de integridad |
| Bloqueo de marco | Abogado del Diablo con protocolo de umbral de concesion |
| Servilismo | Puntuacion anti-servilismo (escala 1-5 antes de conceder) |
| Convergencia prematura | Deteccion de intencion + monitoreo de salud del dialogo |
| Fabricacion metodologica | Lista de verificacion de 7 modos en Stage 2.5 y 4.5 |
| Afirmaciones inverificables | Protocolo de citas de tres capas |

---

## Inicio rapido

```bash
git clone https://github.com/Masqiller/ARG-RESEARCHER-V4.1.git ~/ARG-Researcher
```

Abre el repositorio en tu IDE. Los archivos de configuracion se detectan automaticamente:

| Agente | Configuracion | Comandos |
|:-------|:-------------|:---------|
| **Google Antigravity** | `.agents/rules/arg-instructions.md` + `.agents/workflows/arg-*.md` | Comandos `/arg-*` nativos en Agent Manager |
| **Windsurf** | `.windsurf/workflows/arg-*.md` | Workflows nativos `/arg-*` |
| **Cursor** | `.cursor/rules/arg-instructions.mdc` | `/arg-*` en chat |
| **Claude Code** | `.claude/CLAUDE.md` + `commands/` | Comandos nativos `/arg-*` |
| **GitHub Copilot** | `.github/copilot-instructions.md` | `/arg-*` en chat |
| **Cline / Roo Code** | `.clinerules` | `/arg-*` en chat |
| **Aider** | `.aider/conventions.md` | `/arg-*` en chat |
| **Continue** | `.continue/config.json` | `/arg-*` en chat |
| **Otro** | `.ai/instructions.md` | `/arg-*` en chat |

**Pruebalo:** Ejecuta `/arg-plan` y describe un paper en el que estes trabajando.

---

## Caracteristicas

<table>
<tr>
<td width="50%">

### Investigacion Profunda
*13 agentes | 7 modos*

- Exploracion guiada socratica
- Revision sistematica PRISMA
- Verificacion Semantic Scholar API
- Deteccion de intencion
- Monitoreo de salud del dialogo
- Abogado del Diablo cross-model (opcional)
- Verificacion de hechos con jerarquia de evidencia

</td>
<td width="50%">

### Paper Academico
*13 agentes | 11 modos*

- Calibracion de estilo (aprende tu voz)
- Control de calidad de escritura
- Endurecimiento LaTeX (APA 7.0, IEEE, Chicago)
- Agente de visualizacion
- **Agente Maestro de Diagramas** (TikZ/PGFPlots/Mermaid, 13 categorias)
- Coaching de revision y respuesta R&R
- Conversion de formato de citas (5 formatos)

</td>
</tr>
<tr>
<td width="50%">

### Revisor de Papers
*7 agentes | 6 modos*

- EIC + 3 revisores dinamicos + Abogado del Diablo
- Rubricas de calidad 0-100
- Sprint Contract (Fase 1 ciega + Fase 2)
- Protocolo de umbral de concesion
- Modo calibracion (medir FNR/FPR)
- Matriz de trazabilidad R&R

</td>
<td width="50%">

### Pipeline Academico
*Orquestador de 10 etapas*

- Checkpoints adaptativos con confirmacion del usuario
- Puertas de integridad en Stage 2.5 y 4.5 (obligatorias)
- Material Passport con verificacion de afirmaciones
- Observador de profundidad de colaboracion
- Seguimiento de trayectoria de puntuacion
- Evaluacion de colaboracion de 6 dimensiones (1-100)

</td>
</tr>
</table>

---

## Comandos `/arg-*`

| Comando | Que hace |
|:--------|:---------|
| `/arg-full` | Pipeline completo: investigacion → escritura → revision → correccion → final |
| `/arg-plan` | Planificacion socratica capitulo por capitulo |
| `/arg-outline` | Esquema detallado + mapa de evidencia |
| `/arg-abstract` | Resumen bilingue + palabras clave |
| `/arg-revision` | Borrador revisado + respuestas R&R |
| `/arg-revision-coach` | Hoja de ruta de revision + esqueleto de carta de respuesta |
| `/arg-lit-review` | Bibliografia anotada en formato de paper |
| `/arg-format-convert` | Convertir a LaTeX / DOCX / PDF / Markdown |
| `/arg-citation-check` | Informe de errores de citas |
| `/arg-disclosure` | Declaracion de uso de IA segun el venue |
| `/arg-diagram` | Generacion de diagrama estructural (TikZ / Mermaid / PGFPlots) |

---

## Flujo de trabajo recomendado

Para la mejor calidad, ejecuta estos cuatro pasos en orden:

```
Paso 1 — Investigacion profunda
  /deep-research
  → Produce: Bibliografia anotada, Informe de sintesis, Resumen de RQ

         ↓  Pasar literatura + RQ al siguiente paso

Paso 2 — Planificacion del paper
  /arg-plan
  → Produce: Plan de capitulos, Coleccion INSIGHT, Plan de diagramas

         ↓  Pasar plan de capitulos al siguiente paso

Paso 3 — Revision del plan
  /academic-paper-reviewer  (modo quick o guided)
  → Produce: Retroalimentacion estructural, analisis de brechas, prueba de estres logico

         ↓  Incorporar retroalimentacion, luego ejecutar pipeline completo

Paso 4 — Pipeline completo
  /arg-full
  → Produce: Borrador completo → puerta de integridad → revision → correccion → resultado final
```

> **Atajo:** Si tienes prisa, ejecuta `/arg-full` directamente — contiene las 10 etapas internamente.

---

## Formatos soportados

| Categoria | Opciones |
|:----------|:---------|
| **Estilos de cita** | APA 7.0 (por defecto), Chicago, MLA, IEEE, Vancouver |
| **Tipos de paper** | IMRaD, Revision de literatura, Analisis teorico, Estudio de caso, Policy Brief, Paper de conferencia |
| **Formatos de salida** | Markdown, LaTeX, DOCX (Pandoc), PDF (tectonic) |
| **Idiomas** | Ingles, Chino tradicional, resumenes bilingues; deteccion de intencion funciona en cualquier idioma |

---

## Licencia

Licenciado bajo la [Licencia MIT](LICENSE). Libre para usar, modificar y distribuir. Ver [CONTRIBUTORS.md](CONTRIBUTORS.md).
