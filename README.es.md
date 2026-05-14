<div align="center">

# Academic Research Graphify (ARG)

**Tu copiloto de investigacion academica con IA**

[![Version](https://img.shields.io/badge/version-v4.0.0-blue)](#)
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](https://opensource.org/licenses/MIT)
[![Agents](https://img.shields.io/badge/agents-37-purple)](#-el-equipo-de-agentes)
[![Skills](https://img.shields.io/badge/skills-4-orange)](#-habilidades-y-modos)
[![Modes](https://img.shields.io/badge/modes-25-red)](#-habilidades-y-modos)

[English](README.md) | [繁體中文](README.zh-TW.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Português](README.pt-BR.md) | [हिन्दी](README.hi.md) | [العربية](README.ar.md) | [Русский](README.ru.md)

---

**37 agentes de IA especializados** en **4 habilidades** y **25 modos** para llevar tu investigacion desde la idea hasta la publicacion.
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
git clone https://github.com/Masqiller/ARG-Researcher.git ~/ARG-Researcher
```

Abre el repositorio en tu IDE. Los archivos de configuracion se detectan automaticamente:

| Agente | Configuracion | Comandos |
|:-------|:-------------|:---------|
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
*12 agentes | 10 modos*

- Calibracion de estilo (aprende tu voz)
- Control de calidad de escritura
- Endurecimiento LaTeX (APA 7.0, IEEE, Chicago)
- Agente de visualizacion
- Coaching de revision y respuesta R&R
- Conversion de formato de citas (5 formatos)
- Protocolo anti-fuga
- Verificacion VLM de figuras

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
