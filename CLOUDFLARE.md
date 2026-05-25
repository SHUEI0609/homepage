# Cloudflare Pages 運用メモ

このAstroサイトはCloudflare Pagesで公開できます。

## Cloudflare Pagesの設定

- Framework preset: `Astro`
- Build command: `npm run build`
- Build output directory: `dist`
- Root directory: リポジトリ直下

## Git連携で公開する場合

1. GitHubなどにこのプロジェクトをpushします。
2. Cloudflare Dashboardで `Workers & Pages` からPagesプロジェクトを作成します。
3. リポジトリを選択し、上記のBuild設定を入力します。
4. Production branchは `HomePage` を指定します。
5. デプロイ後、必要に応じてカスタムドメインを接続します。

ローカルでGitHubへpushする例:

```bash
git init -b HomePage
git add .
git commit -m "Initial Astro site"
git remote add origin <GitHub repository URL>
git push -u origin HomePage
```

## ローカルから手動デプロイする場合

```bash
npm run deploy
```

初回実行時はCloudflareへのログインが求められます。
このプロジェクトではWranglerのログを `./.wrangler/logs` に出すようにしています。
本番ブランチ名はCloudflare Pages作成時に指定した `HomePage` です。

## 参考

- Cloudflare Pages Astro guide: https://developers.cloudflare.com/pages/framework-guides/deploy-an-astro-site/
- Cloudflare Pages build configuration: https://developers.cloudflare.com/pages/configuration/build-configuration/
