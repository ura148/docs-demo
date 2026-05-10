# 実装ガイド

## セットアップ手順

### 1. リポジトリのクローン

```bash
git clone https://github.com/ura148/docs-demo.git
cd docs-demo
```

### 2. Docsify のインストール（オプション：ローカルプレビュー用）

```bash
npm install -g docsify-cli
```

### 3. ローカルプレビュー

```bash
docsify serve docs
```

ブラウザで `http://localhost:3000` にアクセス。

### 4. GitHub Pages の有効化

1. リポジトリの **Settings** → **Pages**
2. **Branch** を `main` に設定
3. **Folder** を `docs` に設定
4. Save

数分待つと、`https://ura148.github.io/docs-demo/` で公開されます。

---

## Markdown の書き方

### 見出し

```markdown
# 見出し1
## 見出し2
### 見出し3
```

### リスト

```markdown
- 項目1
- 項目2
  - ネストされた項目
```

### コードブロック

````markdown
```python
def hello():
    print("Hello, World!")
```
````

### テーブル

```markdown
| 列1 | 列2 |
|-----|-----|
| 値1 | 値2 |
| 値3 | 値4 |
```

### リンク

```markdown
[表示テキスト](URL)
[内部ドキュメント](sections/design.md)
```

---

## 新しいドキュメントを追加する

### 1. Markdown ファイルを作成

```bash
touch docs/sections/new-document.md
```

### 2. _sidebar.md に追加

```markdown
- [新しいドキュメント](sections/new-document.md)
```

### 3. コミットして push

```bash
git add .
git commit -m "Add new document"
git push origin main
```

GitHub Pages が自動更新します（数秒～1分で反映）。

---

## トラブルシューティング

### サイトが表示されない

- GitHub Pages が有効化されているか確認
- ブラウザキャッシュをクリア（Ctrl+Shift+R）
- リポジトリが public か確認

### Markdown が表示されない

- ファイル名とパスが正しいか確認
- _sidebar.md のリンクが正しいか確認
- git push されているか確認

---

## ベストプラクティス

1. **コミットメッセージは明確に**
   ```bash
   git commit -m "Update design document"
   ```

2. **画像を追加する場合**
   ```bash
   mkdir docs/images
   # 画像ファイルを追加
   ```
   Markdown では：
   ```markdown
   ![説明](images/example.png)
   ```

3. **定期的に README.md を更新**
   - ドキュメント構成が変わったら更新

4. **プライベートな情報を含めない**
   - API キー、パスワード等は含めない

---

問題が発生した場合は、GitHub Issues を作成してください。
