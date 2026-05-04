# Scoped Guidelines (Example)

特定のディレクトリ（例：`src/components`）に特化した高度な指示を `GEMINI.md` に記述する例です。

## 指針

- すべてのコンポーネントは `Functional Component` として定義すること。
- 命名規則は `PascalCase` を使用すること。
- プロパティには必ず `Interface` を定義すること。
- 副作用（Side Effects）は最小限に抑え、可能な限り `Custom Hooks` に抽出すること。

## 検証ステップ

1. ファイルを作成したら、即座に `npm test` でコンポーネントのレンダリングテストを実行する。
2. `eslint` を実行し、アクセシビリティ（aria-*）の警告がないか確認する。

## 特殊ルール

- `any` 型の使用は禁止。
- インラインスタイルは避け、Tailwind CSS クラスを使用すること。
