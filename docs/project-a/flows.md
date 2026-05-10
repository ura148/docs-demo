# 業務フロー

## 承認ワークフロー

```mermaid
graph TD
    A[申請作成] --> B{承認者確認}
    B -->|承認| C[完了]
    B -->|却下| D[差し戻し]
    D --> A
```

**説明**：
- Step 1: 申請者が申請を作成
- Step 2: 承認者が内容確認
- Step 3: 承認→完了、却下→差し戻し

---

## Salesforce オブジェクト関係図

```mermaid
erDiagram
    ACCOUNT ||--o{ OPPORTUNITY : has
    OPPORTUNITY ||--o{ OPPORTUNITY_LINE_ITEM : contains
    OPPORTUNITY_LINE_ITEM }o--|| PRODUCT2 : references
```

---

## 外部API連携フロー

```mermaid
sequenceDiagram
    participant Salesforce
    participant 外部API
    participant DB

    Salesforce->>外部API: リクエスト送信
    外部API->>DB: データ取得
    DB-->>外部API: 結果返却
    外部API-->>Salesforce: レスポンス返却
```

---

## プロジェクトスケジュール

```mermaid
gantt
    title 実装ロードマップ
    dateFormat  YYYY-MM-DD
    section Phase 1
    基本構造セットアップ     :done, p1, 2026-05-01, 2026-05-07
    section Phase 2
    Mermaid図式化           :active, p2, 2026-05-08, 2026-05-14
    section Phase 3
    UI改善・プラグイン追加   :p3, 2026-05-15, 2026-05-21
```

---

> [!IMPORTANT]
> フロー図は実際の業務仕様に合わせて更新してください。

> [!NOTE]
> Mermaid の記法については [公式ドキュメント](https://mermaid.js.org/) を参照してください。
