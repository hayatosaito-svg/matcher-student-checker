# ビズリク｜学生証チェッカー

Matcher向けの登録フォームです。必須項目は氏名・学部・学年・LINE URL。学生証・紹介者氏名は任意です。

## 公開と登録

GitHub Pagesで画面を配信し、登録内容はビズリクの専用受付APIからGoogle Sheetsへ転記します。学生の入力データや学生証画像はこのリポジトリに保存しません。

## ソースと更新

`matcher-source.zip` は再現可能なVite/Reactソース一式です。GitHub Actionsが展開し、固定した依存関係を導入してテスト・ビルド後に公開します。OCRエンジンと日本語・英語辞書はソースに同梱し、読み取りは利用者のブラウザ内で行います。

ローカルではZIPを展開し、Node.js 22とpnpm 11.19.0で実行します。

```sh
pnpm install --frozen-lockfile --ignore-scripts
pnpm test
pnpm build
```

フォーム変更後は同じ構成でソースZIPを更新してコミットしてください。送信先APIのCORS設定にはGitHub Pagesの正確なoriginを登録しています。
