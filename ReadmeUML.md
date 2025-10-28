## 背景:

MCP設定で settings.json を直接編集するのが面倒という声が多い。
拡張機能やGUIで簡単に設定できる方法が紹介されている。



### 拡張機能でツール追加:

MCP対応ツールは拡張機能で簡単に導入可能。
例：Tavily（デフォルト）、Bing、Mermaid（Marpと併用）



### MCP Serverの追加方法:

npmパッケージ名を入力するだけで追加可能。
例：@modelcontextprotocol/server-puppeteer
Server IDは任意で設定可能。
対象ワークスペースを選択すると mcp.json に自動追加される。



### 前提条件:

Node.js環境が必要（WindowsならNode Version Manager推奨）



### 利点:

JSON編集不要で設定可能。
GUI操作で初心者にも優しい。
複数ツールを簡単に切り替え可能。


## iita記事「https://qiita.com/penicillin0/items/93898ce5b688103f03f6」の内容を日本語で箇条書きにまとめ、PlantUML形式とMermaid形式で図式化したものです



以下は、Qiita記事「VS Code なら Agent で使える MCP/tools は json 触らなくても入れられる」の内容を箇条書きで要約し、PlantUML形式とMermaid形式で図式化したものです


5つの技術革新とその影響（箇条書き）


- Transformer（2017）

  LLMの基盤アーキテクチャ
  並列処理と長距離依存関係の学習を可能にした


- スケーリング則（2020）

  モデルサイズ・データ量・計算量と性能の関係を数式化
  「大きくすれば強くなる」ことを経験則から理論化


- GPT-3（2020）

  1750億パラメータで創発的能力を実証
  Few-shot Learningを可能にした


- RLHF（2022）

  人間のフィードバックによる強化学習
  実用的な対話能力を獲得する決め手となった


- Chain-of-Thought（2022）

  「ステップバイステップで考える」プロンプト設計
  推論能力を大幅に向上させた
