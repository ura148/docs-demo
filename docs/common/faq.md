# FAQ

## セットアップ

**Q: サイトが表示されない**

GitHub Pages が有効化されているか確認してください。

- Settings → Pages → Branch: `main`, Folder: `docs`
- リポジトリが Public であることを確認

> [!TIP]
> 設定後、反映まで数分かかる場合があります。

---

**Q: サイドバーが表示されない**

`docs/.nojekyll` ファイルが存在するか確認してください。このファイルがないと GitHub Pages が `_sidebar.md` を配信しません。

```bash
touch docs/.nojekyll
git add docs/.nojekyll
git commit -m "Add .nojekyll"
git push
```

---

**Q: Mermaid 図が表示されない**

`index.html` に以下が含まれているか確認してください。

```html
<script src="https://cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/docsify-mermaid@latest/dist/docsify-mermaid.js"></script>
```

---

## 運用

**Q: 新しいドキュメントを追加する方法は？**

1. `docs/` 配下に `.md` ファイルを作成
2. `docs/_sidebar.md` にリンクを追加
3. `git push`

---

**Q: ローカルでプレビューする方法は？**

```bash
npm install -g docsify-cli
docsify serve docs
# http://localhost:3000 でアクセス
```

---

> [!NOTE]
> 他に質問がある場合は GitHub Issues を作成してください。
