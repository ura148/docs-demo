# サイドバー設定

`_sidebar.md` と `_navbar.md` の書き方・カスタマイズ方法。

---

## `_sidebar.md` の基本文法

### 見出しなしリスト（推奨）

```markdown
- [ホーム](/)
- [ドキュメント1](docs/doc1.md)
- [ドキュメント2](docs/doc2.md)
```

### セクションヘッダー付き

```markdown
- [ホーム](/)

- **Salesforce**
  - [概要](salesforce/README.md)
  - [設計](salesforce/architecture.md)
  - [フロー](salesforce/flows.md)

- **Heroku**
  - [概要](heroku/README.md)

- **共通**
  - [用語集](common/glossary.md)
  - [規約](common/standards.md)
```

**セクション記法**：
- `- **セクション名**` で見出しを作成（リンク不要）
- インデントで階層を表現（`  `で1階層、`    `で2階層）

---

## リンクの書き方

### 相対パス

```markdown
- [トップ](/)                               # ドメイン直下
- [サイドバー](setup-guide/sidebar-config.md)  # 同フォルダ
- [共通](../common/glossary.md)             # 上層フォルダ
```

### 注意点

- `index.html` では `pathname` が `/docs-demo` で始まるときだけ `basePath: '/docs-demo/'`、それ以外（`docsify serve` など）は `basePath: '/'` になる。サイドバーは従来どおり相対パスで記載する
- `docs/` フォルダ構造がそのまま URL パスになる

---

## 実装例

### 例1：シンプルな構成（プロジェクト少数）

```markdown
- [ホーム](/)

- **Project-A**
  - [概要](project-a/README.md)
  - [設計](project-a/design.md)

- **Project-B**
  - [概要](project-b/README.md)

- [共通](common/)
```

### 例2：複雑な構成（プロジェクト多数）

```markdown
- [ホーム](/)

- **プロジェクト**
  - **Salesforce**
    - [概要](salesforce/README.md)
    - [アーキテクチャ](salesforce/architecture.md)
    - [フロー](salesforce/flows.md)
  - **Heroku**
    - [概要](heroku/README.md)

- **共通**
  - [用語集](common/glossary.md)
  - [開発標準](common/standards.md)
  - [FAQ](common/faq.md)
```

---

## `_navbar.md`（グローバルナビゲーション）

ページ上部に表示される共通ナビゲーション。

### 基本形式

```markdown
- [ホーム](/)
- プロジェクト
  - [Salesforce](salesforce/)
  - [Heroku](heroku/)
- [共通](common/)
- [GitHub](https://github.com/ura148/docs-demo)
```

### navbar の特徴

- **シンプルに**：3～5個程度の最上位項目に絞る
- **外部リンク対応**：`https://` で始まる URL も記載可能
- **ドロップダウン**：インデントでサブメニューを作成

---

## 改行・空行

### 視認性を高める

```markdown
- [ホーム](/)

- **Salesforce**              # 空行でセクション分け
  - [概要](salesforce/README.md)
  - [設計](salesforce/architecture.md)

- **Heroku**
  - [概要](heroku/README.md)

- **共通**                    # セクション後に空行
  - [用語集](common/glossary.md)
```

---

## よくあるカスタマイズ

### 1. バージョン表示をナビに追加

```markdown
- [ホーム](/)
- v1.0.0
- [GitHub](https://github.com/...)
```

### 2. 各プロジェクトへの戻るリンク

```markdown
# salesforce/_sidebar.md 内
- [← トップに戻る](/)

- **Salesforce**
  - [概要](salesforce/README.md)
  - [設計](salesforce/architecture.md)
```

### 3. サイドバーを非表示にする特定ページ

`_sidebar.md` を作成せず、`index.html` で `loadSidebar: false` にする。

---

## トラブルシューティング

### Q: サイドバーが表示されない

**A:** 以下を確認
- `docs/.nojekyll` が存在するか
- `index.html` で `loadSidebar: '_sidebar.md'` が設定されているか
- ブラウザキャッシュをクリア（Cmd+Shift+R）

### Q: リンク先が「Not Found」になる

**A:** ファイルパスが正しいか確認
- `docs/salesforce/README.md` → `(salesforce/README.md)` でリンク
- `docs/common/glossary.md` → `(common/glossary.md)` でリンク

### Q: サブサイドバーが切り替わらない

**A:** 以下を確認
- プロジェクトフォルダに `_sidebar.md` があるか
- ページを遷移する際、ブラウザの戻る・進むボタンで遷移したか（リロードが必要な場合がある）

---

> [!TIP]
> Markdown ファイルを編集した場合、ブラウザを再読み込み（F5）するだけで反映されます。

> [!NOTE]
> より複雑なナビゲーション（動的生成など）が必要な場合は、JavaScript で `window.$docsify` を拡張可能です。
