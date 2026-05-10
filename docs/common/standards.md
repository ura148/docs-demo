# 開発標準・規約

## ファイル命名規則

| 種類 | 規則 | 例 |
|------|------|----|
| Markdown | 小文字・ハイフン区切り | `api-spec.md` |
| フォルダ | 小文字・ハイフン区切り | `project-a/` |

## Markdown 記述規則

### 見出し
- H1（`#`）はファイルに1つのみ
- H2（`##`）でセクション分割
- H3（`###`）で詳細項目

### コードブロック
- 言語を必ず指定する

```markdown
```python
# 良い例
def hello():
    print("Hello")
```
```

### アラート表示

> [!NOTE]
> 補足情報に使用

> [!TIP]
> 推奨事項・ヒントに使用

> [!IMPORTANT]
> 重要な情報に使用

> [!WARNING]
> 注意が必要な情報に使用

## Git コミットメッセージ規則

```
<種類>: <変更内容>

例：
docs: Update API specification
fix: Correct typo in glossary
feat: Add Project-B overview
```

## レビュープロセス

```mermaid
graph LR
    A[ドラフト作成] --> B[セルフレビュー]
    B --> C[チームレビュー]
    C -->|修正あり| B
    C -->|承認| D[マージ・公開]
```
