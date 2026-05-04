# Project Memory & Context (GEMINI.md / MEMORY.md)

AIエージェントにプロジェクトの文脈を永続的に記憶させ、一貫した支援を受けるための仕組みを解説します。

---

## 1. 指示の階層構造 (GEMINI.md)

`GEMINI.md` はエージェントの行動指針を定義します。これは以下の階層で読み込まれ、下層（具体的）な設定が上層（一般的）な設定を補完・上書きします。

| 階層 | パス | 用途 |
|---|---|---|
| **Global** | `~/.gemini/GEMINI.md` | 個人の好み、全プロジェクト共通のトーン、名前 |
| **Root** | `./GEMINI.md` | プロジェクト固有の規約、使用技術、テスト方針 |
| **Scoped** | `./src/module/GEMINI.md` | 特定の機能やディレクトリに特化した高度な指示 |

### Root `GEMINI.md` の例
```markdown
# Project Guidelines
- Framework: Next.js 15
- Testing: Playwright
- Always provide Japanese responses for reasoning.
```

---

## 2. 動的な事実の管理 (MEMORY.md)

`GEMINI.md` が「ルール」であるのに対し、`MEMORY.md` は対話を通じて得られた「事実」や「決定事項」を記録する場所です。

### 運用のベストプラクティス
- **プライベート管理:** 通常は `/Users/user/.gemini/tmp/skills/memory/MEMORY.md` 等に保存し、リポジトリには含めません。
- **インデックス運用:** `MEMORY.md` 自体は軽量なインデックス（目次）として使い、詳細なメモは別ファイル（`docs/architecture_notes.md` 等）にリンクします。
- **自動保存:** ツール（`save_memory` 等）を使用して、エージェントに事実を自律的に記録させます。

---

## 3. コンテキストの最適化

AIのコンテキスト窓を有効に使うために：
- **`/init` コマンド:** プロジェクトをスキャンさせ、最適な初期コンテキストを自動構築させます。
- **`/memory refresh`:** ファイルの変更があった場合、明示的に再読み込みさせて最新の状態を反映させます。
