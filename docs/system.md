```mermaid
flowchart LR
  U[利用者\n(PC/スマホのブラウザ)] -->|HTTPS| FE[フロントエンド\nReact + TypeScript]

  FE -->|REST API / JSON| BE[バックエンド\nNode.js + Express]
  BE -->|CRUD| DB[(MongoDB\n食品・期限・栄養データ)]

  subgraph External[外部データ（任意）]
    NDB[食品成分データ\n(例: 日本食品標準成分表など)]
  end

  BE -->|検索/参照| NDB

  BE -->|期限通知用データ生成| FE
  FE -->|期限が近い食品を表示\n栄養サマリを表示| U
