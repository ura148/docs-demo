# docs-demo

GitHub Pages + Docsify を使用した、Markdown 技術設計書の共有例。

## 🚀 クイックスタート

### オンライン版（公開サイト）

```
https://ura148.github.io/docs-demo/
```

ブラウザで上記 URL にアクセスするだけで、見やすいドキュメントサイトが表示されます。

### ローカルプレビュー（開発用）

```bash
# Docsify CLI をインストール
npm install -g docsify-cli

# ローカルサーバーを起動
docsify serve docs

# ブラウザで http://localhost:3000 にアクセス
```

---

## 📁 ファイル構成

```
docs-demo/
├── README.md                    ← このファイル
├── .gitignore
└── docs/
    ├── index.html               ← Docsify 設定
    ├── _sidebar.md              ← 目次構成
    ├── README.md                ← トップページ
    └── sections/
        ├── overview.md          ← プロジェクト概要
        ├── design.md            ← システム設計書
        ├── api.md               ← API 仕様
        └── implementation.md    ← 実装ガイド
```

---

## ✨ 特徴

- ✅ **Markdown で執筆**：見たままがドキュメント
- ✅ **GitHub Pages で無料公開**
- ✅ **左サイドバーで目次が常に表示**
- ✅ **全文検索機能**
- ✅ **バージョン管理（Git）**
- ✅ **ビルドプロセス不要**
- ✅ **git push で自動更新**

---

## 📖 使い方

### ドキュメントの追加

1. `docs/sections/` に新しい `.md` ファイルを作成
2. `docs/_sidebar.md` に追加
3. `git push`

### ドキュメントの編集

1. `.md` ファイルを編集
2. `git push`
3. GitHub Pages が自動更新（数秒～1分）

### ローカルでテスト

```bash
docsify serve docs
```

---

## 🔧 GitHub Pages の設定

1. リポジトリの **Settings** → **Pages**
2. **Branch**：`main`
3. **Folder**：`docs`
4. Save

---

## 📚 詳細は docs/README.md を参照

ドキュメントサイトにアクセスして、詳細な設定方法と実装ガイドを確認できます。

---

## 🤝 サポート

問題が発生した場合は、GitHub Issues を作成してください。

---

**非エンジニアのクライアントにも優しい、見やすいドキュメントサイトです。**
