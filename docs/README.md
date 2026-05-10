# 設計書 - Docsify Demo

このドキュメントは、Markdown で書かれた設計書を GitHub Pages + Docsify で公開する例です。

## 特徴

- 📝 **Markdown で執筆**：見たままが公開ドキュメント
- 🔍 **検索機能**：左下の検索ボックスで全文検索可能
- 📱 **レスポンシブ**：モバイルでも見やすい
- ⚡ **シンプル**：ビルドプロセス不要、git push で自動反映
- 🎨 **見やすいレイアウト**：左サイドバーで目次が常に表示

## クイックスタート

1. リポジトリを編集
2. Markdown ファイルを追加・修正
3. `git push`
4. GitHub Pages で自動公開

## リポジトリ構成

```
docs-demo/
  └── docs/
      ├── index.html          ← Docsify 設定
      ├── _sidebar.md         ← 目次構成
      ├── README.md           ← このファイル
      └── sections/
          ├── overview.md
          ├── design.md
          ├── api.md
          └── implementation.md
```

## 今後の運用

1. **Markdown を編集** → `.md` ファイルを編集
2. **新しいセクションを追加** → `sections/` に新規ファイル作成
3. **目次を更新** → `_sidebar.md` に追加
4. **git push** → GitHub Pages が自動更新

---

**非エンジニアのクライアントにも優しい、見やすいドキュメントサイトです。**
