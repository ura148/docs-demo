# フォルダ構造設計

## 標準フォルダ構成（3層構造）

```
docs/
├── index.html                       # Docsify 設定（全体共通）
├── .nojekyll                        # GitHub Pages Jekyll 無効化
├── _sidebar.md                      # 全体の目次（トップレベル）
├── _navbar.md                       # グローバルナビゲーション
├── README.md                        # トップページ
│
├── salesforce/                      # プロジェクト1
│   ├── _sidebar.md                  # Salesforce 専用サイドバー
│   ├── README.md                    # プロジェクト概要
│   ├── architecture.md              # アーキテクチャ設計
│   ├── flows.md                     # 業務フロー（Mermaid）
│   └── apis.md                      # API仕様
│
├── heroku/                          # プロジェクト2
│   ├── _sidebar.md                  # Heroku 専用サイドバー
│   └── README.md                    # プロジェクト概要
│
└── common/                          # 共通ドキュメント
    ├── features.md                  # 機能一覧
    ├── glossary.md                  # 用語集
    ├── standards.md                 # 開発標準
    └── faq.md                       # よくある質問
```

---

## フォルダ設計のポイント

### 1. プロジェクトフォルダの命名規則

| ケース | 命名例 | 備考 |
|--------|--------|------|
| プロダクト名 | `salesforce/`, `heroku/` | 推奨 |
| チーム名 | `backend/`, `frontend/` | 対応可 |
| 機能領域 | `auth/`, `payment/` | 対応可 |

### 2. ファイル命名規則

```
良い例：
- README.md (プロジェクト概要)
- architecture.md (設計書)
- api-spec.md (API仕様)
- deployment-guide.md (デプロイガイド)

避けるべき例：
- readMe.md (大文字混在)
- 設計書.md (日本語ファイル名)
- doc1.md, doc2.md (無意味な名前)
```

### 3. ファイルの分割粒度

**小分割（推奨）** - ファイル数多め
- メリット：各ファイルが小さく、編集しやすい。ページ内TOC がすっきり
- デメリット：ファイル数が増える

```
- architecture.md
- database-schema.md
- api-endpoints.md
- error-handling.md
```

**大括り** - ファイル数少なめ
- メリット：ファイル数が少ない
- デメリット：一つのファイルが大きくなり、ページ内TOCが長くなる

---

## サブサイドバー（`_sidebar.md`）の配置

### パターン1：階層的なサイドバー（推奨）

各プロジェクトフォルダに `_sidebar.md` を置く。

```
docs/
├── _sidebar.md                  # 全体目次
├── salesforce/
│   ├── _sidebar.md              # Salesforce 専用（自動切り替え）
│   ├── README.md
│   └── ...
└── heroku/
    ├── _sidebar.md              # Heroku 専用（自動切り替え）
    ├── README.md
    └── ...
```

**動作**：
- `https://.../` → 全体サイドバー表示
- `https://.../salesforce/` → Salesforce サイドバー自動切り替え
- `https://.../heroku/` → Heroku サイドバー自動切り替え

### パターン2：グローバルサイドバーのみ

すべてのページで同じサイドバーを表示。

```
docs/
├── _sidebar.md                  # すべてのページで表示
├── salesforce/
│   ├── README.md
│   └── ...
└── heroku/
    ├── README.md
    └── ...
```

**メリット**：シンプル  
**デメリット**：サイドバーが長くなりがち

---

## プロジェクト追加時の手順

### 新規プロジェクト「NewProject」を追加する場合

```bash
# 1. フォルダ作成
mkdir docs/newproject

# 2. ファイル作成
touch docs/newproject/README.md
touch docs/newproject/_sidebar.md

# 3. _sidebar.md に内容を追加
cat > docs/newproject/_sidebar.md << 'EOF'
- [← トップに戻る](/)

- **NewProject**
  - [概要](newproject/README.md)
  - [アーキテクチャ](newproject/architecture.md)
  - [フロー](newproject/flows.md)
EOF

# 4. 全体の _sidebar.md に追加
# - **NewProject**
#   - [概要](newproject/README.md)

# 5. _navbar.md に追加
#   - [NewProject](newproject/)

# 6. git commit & push
git add docs/newproject
git commit -m "Add NewProject"
git push
```

---

## ベストプラクティス

> [!TIP]
> 既存プロジェクトをテンプレートとして、フォルダごとコピーして新規プロジェクトを作成するのが効率的です。

> [!IMPORTANT]
> `_sidebar.md` は各階層で1つだけ有効。ネストすることはできません。

> [!NOTE]
> 共通ドキュメント（用語集、規約）は `common/` フォルダで一元管理。複数プロジェクトから参照可能です。
