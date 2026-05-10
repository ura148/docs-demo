# セットアップガイド

Docsify を使用した設計書管理システムを新規プロジェクトに展開するための実装ガイドです。

## 📚 ガイド一覧

### 1. [フォルダ構造設計](setup-guide/folder-structure.md)
プロジェクト複数の場合の推奨フォルダ構成パターン

### 2. [サイドバー設定](setup-guide/sidebar-config.md)
`_sidebar.md` と `_navbar.md` の書き方・カスタマイズ方法

### 3. [プラグイン設定](setup-guide/plugin-setup.md)
`index.html` で使用するプラグインの詳細設定

### 4. [ベストプラクティス](setup-guide/best-practices.md)
運用上のコツ・注意点・トラブルシューティング

---

## 🚀 クイックセットアップ

### 前提条件
- Node.js がインストールされている
- Git リポジトリが初期化されている

### 最小限の手順（5分）

```bash
# 1. Docsify CLI をインストール
npm install -g docsify-cli

# 2. docs フォルダを初期化
docsify init ./docs

# 3. 本サンプルの index.html をコピー（プラグイン設定済み）
# または手動で index.html を編集

# 4. _sidebar.md, _navbar.md を作成

# 5. ローカルプレビュー
docsify serve docs
```

---

## 📋 実装チェックリスト

### フェーズ 1（基本構造）
- [ ] `docs/` フォルダが作成されている
- [ ] `index.html` にプラグイン設定がある
- [ ] `_sidebar.md` が作成されている
- [ ] `_navbar.md` が作成されている
- [ ] `.nojekyll` が `docs/` 直下にある
- [ ] ローカル(`http://localhost:3000`)で動作確認済み

### フェーズ 2（プロジェクト構成）
- [ ] `salesforce/`, `heroku/`, `common/` 等のプロジェクトフォルダが作成
- [ ] 各プロジェクトに `README.md` がある
- [ ] 各プロジェクトに `_sidebar.md`（サブサイドバー）がある
- [ ] `common/` に共通ドキュメント（用語集、規約など）がある

### フェーズ 3（ドキュメント作成）
- [ ] 設計書（Markdown）が `_sidebar.md` に登録されている
- [ ] Mermaid 図が 3～5個含まれている
- [ ] アラート表示（NOTE/WARNING など）が使用されている
- [ ] ページ内TOC が表示されている

### フェーズ 4（デプロイ）
- [ ] GitHub/GitLab でリポジトリ作成
- [ ] Pages 設定（Branch: main, Folder: docs）
- [ ] `git push` で公開確認
- [ ] チーム全体でアクセステスト完了

---

## 💡 Tips

> [!TIP]
> 既存の Markdown ファイルがある場合は、フォルダ構成に合わせて整理し、`_sidebar.md` にリンクを追加するだけで即座に公開できます。

> [!NOTE]
> サンプルの `salesforce/`, `heroku/` フォルダをテンプレートとして使用し、新規プロジェクトフォルダをコピーして始めるのが効率的です。

---

## 📞 サポート

各ガイドの詳細、設定例、Q&A については各ファイルを参照してください。
