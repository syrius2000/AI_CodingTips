# AI Coding Tips (2026 Edition)

このリポジトリは、現代のAIエージェント（Gemini CLI, Cursor, Windsurf等）を最大限に活用し、開発効率を極限まで高めるためのベストプラクティスを集約したガイドです。

「AIにコードを書かせる」時代から、**「AIエージェントを指揮し、自律的なワークフローを構築する」**時代への移行をサポートします。

---

## 🚀 核心となる3つのコンセプト

### 1. エージェンティック・ワークフロー (Agentic Workflow)
AIを単なるコード補完ツールとしてではなく、調査・設計・実装・検証を自律的に行う「エージェント」として扱います。
- **Research -> Strategy -> Execution -> Validation** のループを回す。
- 実装前に「計画（Plan）」を立てさせ、人間がレビューする。

### 2. コンテキスト・エンジニアリング (Context Engineering)
AIの性能は「何を知っているか」に依存します。
- `.cursorrules` や `GEMINI.md` を活用し、プロジェクト固有のルールを常時提供。
- 巨大なコンテキスト窓を活かしつつ、ノイズを減らすためのファイル選択。

### 3. MCP (Model Context Protocol) による拡張
AIに「手足（ツール）」を与えます。
- 外部検索、データベース、セキュリティスキャン、自社ツールとの統合。

---

## 📁 ディレクトリ構成

- [`/rules`](./rules/): 各種AIツール向けの指示書テンプレート
  - `GEMINI.md`: Gemini CLI / エージェント向け
  - `.cursorrules`: Cursor専用ルール
  - `.clinerules`: Cline / Roo Code向け
- [`/docs`](./docs/): 詳細なガイドライン
  - `agentic_workflow.md`: 自律的な開発サイクルの回し方
  - `prompt_engineering.md`: 2026年版プロンプトテクニック
  - `mcp_guide.md`: MCPサーバーの活用と設定
- [`/examples`](./examples/): 実践的な設定例とコード

---

## 🛠️ 推奨ツールセット

- **IDE:** [Cursor](https://cursor.com/) - IDEネイティブなエージェント体験
- **CLI:** [Gemini CLI](https://github.com/google-gemini/gemini-cli) - 大規模コンテキストと自動化
- **Utility:** [Tavily](https://tavily.com/) - AI向けの高速Web検索

---

## 🤝 貢献について

このリポジトリは常に最新の知見を反映させることを目的としています。新しいツールや手法についての知見があれば、ぜひプルリクエストをお送りください。
