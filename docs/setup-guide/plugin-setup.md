# プラグイン設定

`index.html` で使用するプラグインの詳細設定。

---

## 最小限の設定

```html
<script>
  window.$docsify = {
    name: 'プロジェクト設計書',
    repo: 'https://github.com/your-account/your-repo',
    loadSidebar: '_sidebar.md',
    basePath: '/repo-name/',
  };
</script>
<script src="https://cdn.jsdelivr.net/npm/docsify@4"></script>
```

---

## 推奨プラグイン一覧

### 1. Search（検索）

**設定**：
```html
<script src="https://cdn.jsdelivr.net/npm/docsify@4/lib/plugins/search.min.js"></script>
```

**`$docsify` オプション**：
```javascript
search: {
  maxAge: 86400000,        // キャッシュ有効期間（ミリ秒）
  paths: 'auto',           // 自動パス検出
  placeholder: '検索...',   // プレースホルダーテキスト
  noData: '検索結果なし',   // 検索なしのメッセージ
  depth: 3                 // 見出し検索の深さ
}
```

### 2. Table of Contents（ページ内目次）

**CSS をロード**：
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/docsify-toc@1/dist/toc.css">
```

**プラグインをロード**：
```html
<script src="https://cdn.jsdelivr.net/npm/docsify-toc@1/dist/toc.js"></script>
```

**`$docsify` オプション**：
```javascript
toc: {
  tocMaxLevel: 3,           // TOCの最大見出しレベル
  target: 'h2, h3'         // 対象となる見出しタグ
}
```

### 3. Emoji（絵文字）

**設定**：
```html
<script src="https://cdn.jsdelivr.net/npm/docsify@4/lib/plugins/emoji.min.js"></script>
```

使用例：`:smile:` → 😊

### 4. Mermaid（図式）

**Mermaid ライブラリ**：
```html
<script src="https://cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js"></script>
```

**Docsify Mermaid プラグイン**：
```html
<script src="https://cdn.jsdelivr.net/npm/docsify-mermaid@latest/dist/docsify-mermaid.js"></script>
```

**`$docsify` オプション**：
```javascript
mermaid: {
  theme: 'default'  // 'default', 'dark', 'forest', 'neutral'
}
```

### 5. Flexible Alerts（アラート）

**設定**：
```html
<script src="https://cdn.jsdelivr.net/npm/docsify-plugin-flexible-alerts@1"></script>
```

**使用方法**：
```markdown
> [!NOTE]
> 補足情報

> [!TIP]
> ヒント

> [!IMPORTANT]
> 重要な情報

> [!WARNING]
> 警告
```

---

## フル設定例

```html
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>設計書</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/docsify@4/themes/vue.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/docsify-toc@1/dist/toc.css">
  <style>
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }
  </style>
</head>
<body>
  <div id="app"></div>
  <script>
    window.$docsify = {
      name: 'プロジェクト設計書',
      repo: 'https://github.com/ura148/docs-demo',
      loadSidebar: '_sidebar.md',
      loadNavbar: '_navbar.md',
      subMaxLevel: 3,
      auto2top: true,
      basePath: '/docs-demo/',
      homepage: 'README.md',
      notFoundPage: false,
      search: {
        maxAge: 86400000,
        paths: 'auto',
        placeholder: '検索...',
        noData: '検索結果なし',
        depth: 3
      },
      toc: {
        tocMaxLevel: 3,
        target: 'h2, h3'
      },
      mermaid: {
        theme: 'default'
      }
    };
  </script>
  <script src="https://cdn.jsdelivr.net/npm/docsify@4"></script>
  <script src="https://cdn.jsdelivr.net/npm/docsify@4/lib/plugins/search.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/docsify@4/lib/plugins/emoji.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/docsify-toc@1/dist/toc.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/docsify-plugin-flexible-alerts@1"></script>
  <script src="https://cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/docsify-mermaid@latest/dist/docsify-mermaid.js"></script>
</body>
</html>
```

---

## オプションプラグイン

### Dark Mode（ダークモード）

```html
<script src="https://cdn.jsdelivr.net/npm/docsify-dark-mode@1"></script>
```

### Tabs（タブ表示）

```html
<script src="https://cdn.jsdelivr.net/npm/docsify-tabs@1"></script>
```

**挙動**: `<!-- tabs:start -->` ～ `<!-- tabs:end -->` で囲んだ部分**だけ**がタブになります。H1 の有無や見出しレベルでは自動ではタブ化されません（明示マークが必須）。

スタイルは現行バンドルで JS から注入されるため、別途 CSS ファイルの読み込みは不要です。

言語別コード例などで活躍します。具体例は [タブ表示サンプル](tabs-sample.md) を参照してください。

```markdown
<!-- tabs:start -->

#### **JavaScript**

```javascript
console.log('hello');
```

#### **Python**

```python
print('hello')
```

<!-- tabs:end -->
```

---

## よくあるカスタマイズ

### 1. テーマの変更

```html
<!-- デフォルト -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/docsify@4/themes/vue.css">

<!-- Buble テーマ -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/docsify@4/themes/buble.css">

<!-- Dark テーマ -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/docsify@4/themes/dark.css">

<!-- Dolphin テーマ -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/docsify@4/themes/dolphin.css">
```

### 2. フォント変更

```html
<style>
  body {
    font-family: 'Helvetica Neue', Arial, sans-serif;  /* 英数字向け */
    /* または */
    font-family: '"Noto Sans JP", sans-serif;          /* 日本語対応 */
  }
</style>
```

### 3. 背景色変更

```html
<style>
  body {
    background-color: #f5f5f5;
  }
</style>
```

---

## トラブルシューティング

### Q: プラグインが読み込まれない

**A:** 以下を確認
- `<script>` タグが正しく記載されているか
- CDN URL が正しいか（`https://` で始まるか）
- ブラウザコンソール（F12 → Console）でエラーを確認

### Q: Mermaid 図が描画されない

**A:** 以下を確認
- Mermaid ライブラリ + Docsify プラグインの両方が読み込まれているか
- Markdown コードブロックが ` ```mermaid ` で始まっているか
- ページをリロードしたか

### Q: 検索が動作しない

**A:** 以下を確認
- `search.min.js` が正しく読み込まれているか
- `paths: 'auto'` が `$docsify` に設定されているか
- ブラウザ開発者ツール → Storage → IndexedDB でキャッシュを削除してリロード

---

> [!TIP]
> CDN が遅い場合は、ローカルに JavaScript ファイルをダウンロードして使用することも可能です。

> [!NOTE]
> プラグインは必要に応じて追加・削除できます。最小限の設定から始めて、必要なものを足していくのがおすすめです。
