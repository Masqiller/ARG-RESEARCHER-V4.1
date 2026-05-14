<div align="center">

# Academic Research Graphify (ARG)

**AI 기반 학술 연구 코파일럿**

[![Version](https://img.shields.io/badge/version-v4.0.0-blue)](#)
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](https://opensource.org/licenses/MIT)
[![Agents](https://img.shields.io/badge/agents-37-purple)](#-기능)
[![Skills](https://img.shields.io/badge/skills-4-orange)](#-스킬-및-모드)
[![Modes](https://img.shields.io/badge/modes-25-red)](#-스킬-및-모드)

[English](README.md) | [繁體中文](README.zh-TW.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [日本語](README.ja.md) | [Português](README.pt-BR.md) | [हिन्दी](README.hi.md) | [العربية](README.ar.md) | [Русский](README.ru.md)

---

**37개의 전문 AI 에이전트**가 **4개의 스킬**과 **25개의 모드**로 연구 아이디어부터 논문 출판까지 지원합니다.
**모든 AI 코딩 에이전트**와 호환 — Windsurf, Cursor, Claude Code, GitHub Copilot, Cline, Aider, Continue 등.

[빠른 시작](#-빠른-시작) | [기능](#-기능) | [아키텍처](docs/ARCHITECTURE.md) | [설정 가이드](UNIVERSAL_SETUP.md)

</div>

---

## 왜 ARG인가?

> **AI는 코파일럿이지 파일럿이 아닙니다.** ARG는 논문을 대신 써주지 않습니다. 참고문헌 검색, 인용 서식, 데이터 검증, 논리적 일관성 확인 등 번거로운 작업을 처리하여 당신이 진짜 두뇌가 필요한 일에 집중할 수 있게 합니다.

| 문제 | ARG의 해결책 |
|------|------------|
| 인용 환각 | Semantic Scholar API 검증 + 무결성 게이트 |
| 프레임 잠금 | 악마의 대변인 + 양보 임계값 프로토콜 |
| 아첨성 | 반아첨 점수 (양보 전 1-5 척도) |
| 조기 수렴 | 의도 감지 + 대화 건강도 모니터링 |
| 방법론 조작 | Stage 2.5 & 4.5의 7모드 차단 체크리스트 |

---

## 빠른 시작

```bash
git clone https://github.com/Masqiller/ARG-Researcher.git ~/ARG-Researcher
```

IDE에서 레포를 엽니다. 설정 파일이 자동으로 감지됩니다:

| 에이전트 | 설정 | 명령어 |
|:---------|:-----|:-------|
| **Windsurf** | `.windsurf/workflows/arg-*.md` | 네이티브 `/arg-*` 워크플로 |
| **Cursor** | `.cursor/rules/arg-instructions.mdc` | 채팅에서 `/arg-*` |
| **Claude Code** | `.claude/CLAUDE.md` + `commands/` | 네이티브 `/arg-*` 명령어 |
| **GitHub Copilot** | `.github/copilot-instructions.md` | 채팅에서 `/arg-*` |
| **기타** | `.ai/instructions.md` | 채팅에서 `/arg-*` |

**테스트:** `/arg-plan`을 실행하고 작성 중인 논문을 설명하세요.

---

## 기능

<table>
<tr>
<td width="50%">

### 심층 연구
*13 에이전트 | 7 모드*

- 소크라테스식 가이드 탐구
- PRISMA 체계적 리뷰
- Semantic Scholar API 검증
- 의도 감지 (탐색형 vs. 목표 지향형)
- 대화 건강도 모니터링

</td>
<td width="50%">

### 학술 논문
*12 에이전트 | 10 모드*

- 스타일 캘리브레이션 (당신의 문체 학습)
- 작성 품질 검사
- LaTeX 강화 (APA 7.0, IEEE, Chicago)
- 시각화 에이전트
- 수정 코칭 & R&R 응답

</td>
</tr>
<tr>
<td width="50%">

### 논문 리뷰어
*7 에이전트 | 6 모드*

- EIC + 3명의 동적 리뷰어 + 악마의 대변인
- 0-100 품질 루브릭
- Sprint Contract (블라인드 1단계 + 2단계)
- 캘리브레이션 모드 (FNR/FPR 측정)

</td>
<td width="50%">

### 학술 파이프라인
*10단계 오케스트레이터*

- 사용자 확인이 필요한 적응형 체크포인트
- Stage 2.5 & 4.5 무결성 게이트 (필수)
- Material Passport
- 6차원 협업 품질 평가 (1-100)

</td>
</tr>
</table>

---

## `/arg-*` 명령어

| 명령어 | 설명 |
|:-------|:-----|
| `/arg-full` | 전체 파이프라인: 연구 → 작성 → 리뷰 → 수정 → 최종화 |
| `/arg-plan` | 소크라테스식 장별 계획 |
| `/arg-outline` | 상세 개요 + 증거 맵 |
| `/arg-abstract` | 이중 언어 초록 + 키워드 |
| `/arg-revision` | 수정 원고 + R&R 응답 |
| `/arg-lit-review` | 논문 형식의 주석 참고문헌 |
| `/arg-format-convert` | LaTeX / DOCX / PDF / Markdown 변환 |
| `/arg-citation-check` | 인용 오류 보고서 |
| `/arg-disclosure` | AI 사용 공개 성명 |

---

## 라이선스

[MIT 라이선스](LICENSE)에 따라 라이선스됩니다. 상업적 사용 포함 자유롭게 사용, 수정 및 배포 가능. [CONTRIBUTORS.md](CONTRIBUTORS.md) 참조.
