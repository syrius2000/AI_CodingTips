# Agent Hooks & Automation

フック（Hooks）システムを利用して、AIエージェントの動作を制御したり、外部ツールと連携させたりする方法を解説します。

---

## 1. フックとは？

エージェントのライフサイクル（実行前、実行後、エラー時等）にカスタムスクリプトを挿入する仕組みです。これにより、エージェントに「ガードレール」を設けたり、自動化を加速させたりできます。

## 2. 主要なフックイベント

| イベント | タイミング | 主な用途 |
|---|---|---|
| `BeforeTool` | ツール実行の直前 | セキュリティスキャン、書き込み内容の検証 |
| `AfterTool` | ツール実行の直後 | 関連ドキュメントの自動更新、結果のパース |
| `SessionStart` | セッション開始時 | 最新のJiraチケットやGit差分の注入 |
| `Notification` | 通知発生時 | SlackやTeamsへの進行状況の転送 |

---

## 3. 設定例 (`settings.json`)

エージェントの設定ファイルにフックを定義します。

```json
{
  "hooks": {
    "BeforeTool": [
      {
        "matcher": "write_file",
        "type": "command",
        "command": "node ./scripts/secret-checker.js",
        "description": "APIキーがファイルに含まれていないかチェックする"
      }
    ],
    "Notification": [
      {
        "type": "command",
        "command": "python3 ./scripts/notify-slack.py",
        "description": "人間による承認が必要な場合に通知を送る"
      }
    ]
  }
}
```

---

## 4. 高度な連携ワークフロー

### CI/CDとの統合
GitHub Actions 等で `gemini` をヘッドレスモードで起動し、PRの自動レビューやドキュメント生成をフック経由で実行させます。

### セキュリティガードレール
`BeforeTool` フックで許可されていないライブラリの追加や、特定ファイルの編集を物理的にブロックし、エージェントに代替案を考えさせます。

### 自動ドキュメント同期
`AfterTool` でコードの変更を検知し、即座に関連する `README.md` や技術仕様書を AI に更新させることで、ドキュメントの鮮度を保ちます。
