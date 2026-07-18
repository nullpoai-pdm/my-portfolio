# 15_MyPortfolio プロジェクト固有ルール

このファイルは `15_MyPortfolio` プロジェクト限定の指示。`/Users/sayaka/Cursor/CLAUDE.md`（モノレポ共通）に追加して適用される。

## リポジトリ情報

- **正リポジトリ:** `https://github.com/nullpoai-pdm/my-portfolio`（GitHub Pages 有効）
- **公開URL:** `https://nullpoai-pdm.github.io/my-portfolio/`
- git 操作は `/Users/sayaka/Cursor/15_MyPortfolio/` 内で実行。操作前に `git rev-parse --show-toplevel` を確認する。

## 法務ページの管理（クロスリポジトリ例外）

このリポジトリは **他アプリのプライバシーポリシー・利用規約の静的ページ** を一元ホスティングする役割を担う。これは意図的な例外であり、認められた連携である。

### ディレクトリ構成

```
legal/
  index.html          ← アプリ一覧（管理用）
  gifmaker/
    privacy.html
    terms.html
  <次のアプリ>/
    privacy.html
    terms.html
```

### アプリごとのURL

| アプリ | プライバシーポリシー | 利用規約 |
|---|---|---|
| GIF Maker | `.../legal/gifmaker/privacy.html` | `.../legal/gifmaker/terms.html` |

### 運用ルール

- 新しいアプリを追加するたびに `legal/<app-slug>/` ディレクトリを作成し、`legal/index.html` にリンクを追記する
- `app-slug` は小文字・ハイフン区切り（例: `gifmaker`, `study-studio`）
- 法務ページの内容が変わったとき（会社情報・連絡先・機能変更など）は必ずこのリポジトリも更新する
- アプリのコード・アセット・設計書はこのリポジトリに置かない

### 禁止事項

- アプリの `.ipa` / `.xcodeproj` / Swift ファイルをこのリポジトリにコミットしない
- 複数アプリの法務コミットを1つにまとめない（アプリごとに別コミット）
- `my-portfolio` の `git` 操作を `GifMaker` リポジトリの操作と同時に行わない

## Push 前の必須チェック

- このリポジトリのローカル `user.email` が no-reply アドレスになっていることを確認する
