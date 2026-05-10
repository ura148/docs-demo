# API 仕様

## エンドポイント一覧

### GET /api/documents

ドキュメント一覧を取得します。

**リクエスト**
```
GET /api/documents?page=1&limit=10
```

**レスポンス**
```json
{
  "status": "success",
  "data": [
    {
      "id": "doc-001",
      "title": "プロジェクト概要",
      "updated_at": "2026-05-10"
    }
  ],
  "pagination": {
    "page": 1,
    "limit": 10,
    "total": 5
  }
}
```

### GET /api/documents/:id

特定のドキュメントを取得します。

**リクエスト**
```
GET /api/documents/doc-001
```

**レスポンス**
```json
{
  "status": "success",
  "data": {
    "id": "doc-001",
    "title": "プロジェクト概要",
    "content": "# プロジェクト概要\n\n...",
    "updated_at": "2026-05-10"
  }
}
```

## エラーハンドリング

### 400 Bad Request
```json
{
  "status": "error",
  "code": "INVALID_PARAM",
  "message": "Invalid page parameter"
}
```

### 404 Not Found
```json
{
  "status": "error",
  "code": "NOT_FOUND",
  "message": "Document not found"
}
```

## レート制限

- **制限値**：1時間あたり 1000 リクエスト
- **ヘッダ**：`X-RateLimit-Remaining` で残数を確認可能

> [!WARNING]
> レート制限を超えた場合は 429 Too Many Requests が返ります。

> [!TIP]
> 開発時は `X-RateLimit-Remaining` ヘッダを監視してください。
