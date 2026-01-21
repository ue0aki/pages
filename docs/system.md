flowchart LR
  U[利用者(ブラウザ)] --> FE[React + TypeScript]
  FE -->|REST API| BE[Node.js + Express]
  BE --> DB[(MongoDB)]
