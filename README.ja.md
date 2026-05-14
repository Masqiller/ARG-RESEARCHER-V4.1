<div align="center">

# Academic Research Graphify (ARG)

**AI駆動の学術研究コパイロット**

[![Version](https://img.shields.io/badge/version-v4.0.0-blue)](#)
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](https://opensource.org/licenses/MIT)
[![Agents](https://img.shields.io/badge/agents-37-purple)](#-機能)
[![Skills](https://img.shields.io/badge/skills-4-orange)](#-スキルとモード)
[![Modes](https://img.shields.io/badge/modes-25-red)](#-スキルとモード)

[English](README.md) | [繁體中文](README.zh-TW.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [한국어](README.ko.md) | [Português](README.pt-BR.md) | [हिन्दी](README.hi.md) | [العربية](README.ar.md) | [Русский](README.ru.md)

---

**37の専門AIエージェント**が**4つのスキル**と**25のモード**で、研究のアイデアから論文出版まで支援します。
**あらゆるAIコーディングエージェント**に対応 — Windsurf、Cursor、Claude Code、GitHub Copilot、Cline、Aider、Continue等。

[クイックスタート](#-クイックスタート) | [機能](#-機能) | [アーキテクチャ](docs/ARCHITECTURE.md) | [セットアップ](UNIVERSAL_SETUP.md)

</div>

---

## なぜARG？

> **AIはコパイロットであり、パイロットではありません。** ARGは論文を代筆しません。面倒な作業 — 文献検索、引用フォーマット、データ検証、論理一貫性チェック — を処理し、あなたが本当に頭を使うべきことに集中できるようにします。

| 問題 | ARGの解決策 |
|------|-----------|
| 引用ハルシネーション | Semantic Scholar API検証 + 整合性ゲート |
| フレームロック | 悪魔の代弁者 + 譲歩閾値プロトコル |
| 迎合性 | 反迎合スコアリング（譲歩前に1-5スケール） |
| 早期収束 | 意図検出 + 対話健全性モニタリング |
| 方法論捏造 | Stage 2.5 & 4.5での7モードブロッキングチェックリスト |

---

## クイックスタート

```bash
git clone https://github.com/Masqiller/ARG-Researcher.git ~/ARG-Researcher
```

IDEでリポジトリを開きます。設定ファイルは自動検出されます：

| エージェント | 設定 | コマンド |
|:------------|:-----|:--------|
| **Windsurf** | `.windsurf/workflows/arg-*.md` | ネイティブ `/arg-*` ワークフロー |
| **Cursor** | `.cursor/rules/arg-instructions.mdc` | チャットで `/arg-*` |
| **Claude Code** | `.claude/CLAUDE.md` + `commands/` | ネイティブ `/arg-*` コマンド |
| **GitHub Copilot** | `.github/copilot-instructions.md` | チャットで `/arg-*` |
| **その他** | `.ai/instructions.md` | チャットで `/arg-*` |

**テスト：** `/arg-plan` を実行し、執筆中の論文を説明してください。

---

## 機能

<table>
<tr>
<td width="50%">

### 深層研究
*13エージェント | 7モード*

- ソクラテス式ガイド付き探索
- PRISMAシステマティックレビュー
- Semantic Scholar API検証
- 意図検出（探索型 vs. 目標志向型）
- 対話健全性モニタリング

</td>
<td width="50%">

### 学術論文
*12エージェント | 10モード*

- スタイルキャリブレーション
- 執筆品質チェック
- LaTeX強化（APA 7.0、IEEE、Chicago）
- 可視化エージェント
- 改訂コーチング & R&R対応

</td>
</tr>
<tr>
<td width="50%">

### 論文レビュア
*7エージェント | 6モード*

- EIC + 3名の動的レビュア + 悪魔の代弁者
- 0-100品質ルーブリック
- Sprint Contract（ブラインド第1相 + 第2相）
- キャリブレーションモード

</td>
<td width="50%">

### アカデミックパイプライン
*10段階オーケストレータ*

- ユーザー確認付き適応チェックポイント
- Stage 2.5 & 4.5の整合性ゲート（必須）
- Material Passport
- 6次元協力品質評価（1-100）

</td>
</tr>
</table>

---

## `/arg-*` コマンド

| コマンド | 説明 |
|:--------|:-----|
| `/arg-full` | 完全パイプライン：研究 → 執筆 → レビュー → 改訂 → 最終化 |
| `/arg-plan` | ソクラテス式章ごとの計画 |
| `/arg-outline` | 詳細アウトライン + エビデンスマップ |
| `/arg-abstract` | バイリンガル要旨 + キーワード |
| `/arg-revision` | 改訂原稿 + R&R回答 |
| `/arg-lit-review` | 論文形式の注釈付き書誌 |
| `/arg-format-convert` | LaTeX / DOCX / PDF / Markdownへの変換 |
| `/arg-citation-check` | 引用エラーレポート |
| `/arg-disclosure` | AI使用開示声明 |

---

## ライセンス

[MITライセンス](LICENSE)の下でライセンスされています。商用利用を含め、自由に使用・変更・配布できます。[CONTRIBUTORS.md](CONTRIBUTORS.md)を参照。
