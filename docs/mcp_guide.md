# MCP (Model Context Protocol) Guide

MCPは、AIエージェントに外部ツールやデータソースへのアクセス権を与えるためのオープンな標準プロトコルです。

---

## 1. なぜMCPが必要か？

AIエージェント（Claude Desktop, Cursor, Gemini CLI等）は、デフォルトではローカルファイルやインターネットの一部にしかアクセスできません。MCPを使用することで、以下のような拡張が可能になります：
- **Web検索:** TavilyやGoogle Search API経由での最新情報の取得。
- **データベース:** SQLデータベースからの直接的なデータ抽出。
- **開発ツール:** Snykによるセキュリティスキャンや、GitHubとの高度な連携。

---

## 2. セットアップ方法 (VS Code / Cursor)

現在、多くのIDE拡張機能がMCPをサポートしており、`settings.json` を直接編集しなくてもGUIで設定できるようになっています。

### クイック追加
- 多くのエージェント拡張機能（Cline, Roo Code等）では、npmパッケージ名を指定するだけでサーバーを追加できます。
  - 例: `@modelcontextprotocol/server-puppeteer` (ブラウザ操作用)
- Node.js環境が必要です（Windowsの場合は nvm などの利用を推奨）。

---

## 3. 推奨されるMCPサーバー

| サーバー名 | 用途 |
|---|---|
| `tavily-mcp` | AIに最適化された高速なWeb検索 |
| `google-maps` | 場所や住所情報の取得 |
| `github` | リポジトリの操作、Issueの読み書き |
| `sequential-thinking` | AIに複雑な推論を段階的に行わせる |

---

## 4. (参考) 技術的な背景

LLMの進化には、Transformerの登場（2017）から始まり、スケーリング則（2020）、RLHFによる人間への適応（2022）、そしてChain-of-Thought（2022）といった技術革新が寄与しています。MCPは、これらの強力な知能を「外部世界」と接続するための最後のピースといえます。
