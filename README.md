# My-Account-API Azure App Service demo

添付の `index.html` を Azure App Service の Node.js Web アプリとして公開できる構成にしたサンプルです。

## ファイル
- `public/index.html`: Auth0 SPA、My Account API、Passkey 登録デモ
- `server.js`: 静的配信、公開設定 API、`/health`
- `package.json`: Azure が実行する `npm start`

## Azure App Service の環境変数
`AUTH0_DOMAIN`、`AUTH0_CLIENT_ID`、`AUTH0_AUDIENCE`、`MY_ACCOUNT_API_BASE` を設定してください。例は `.env.example` にあります。Client Secret や API Token は登録・公開しないでください。

## Auth0 Application
公開先が `https://<app-name>.azurewebsites.net` の場合、同じ URL を Allowed Callback URLs、Allowed Logout URLs、Allowed Web Origins に登録します。カスタムドメインを使う場合はそのオリジンも登録してください。

## GitHub と Azure
ZIP を展開し、中身を GitHub リポジトリ直下へアップロードします。Azure Portal の App Service > Deployment Center で GitHub、対象リポジトリ、`main` ブランチを選択してください。

## ローカル確認
```bash
npm install
# .env.example の値を環境変数として設定
npm start
```
`http://localhost:8080` を開き、`/health`、ログイン、プロフィール表示、Passkey 登録を確認します。ローカル URL も Auth0 の許可 URL に追加してください。
