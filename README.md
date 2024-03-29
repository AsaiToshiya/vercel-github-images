# vercel-github-images

## セットアップ

### リポジトリ

```bash
git clone https://github.com/AsaiToshiya/vercel-github-images.git
cd vercel-github-images
npm install
```

### シンボリック リンク

```bash
sudo mkdir -p /opt/google/chrome
sudo ln -s /usr/bin/chromium-browser /opt/google/chrome/chrome
```

### Vercel

#### ログイン

```bash
$ node ./node_modules/vercel/dist/index.js login to.asai.60@gmail.com
Vercel CLI 24.2.5
We sent an email to to.asai.60@gmail.com. Please follow the steps provided inside it and make sure the security code matches Wicked Frog.
> Success! Email authentication complete for to.asai.60@gmail.com
Congratulations! You are now logged in. In order to deploy something, run `vercel`.
💡  Connect your Git Repositories to deploy every branch push automatically (https://vercel.link/git).
```

#### プロジェクトの作成

```bash
$ node ./node_modules/vercel/dist/index.js project add vercel-github-images
Vercel CLI 28.16.2
> Success! Project vercel-github-images added (asaitoshiya) [494ms]
```

#### リンク

```bash
$ node ./node_modules/vercel/dist/index.js link
> UPDATE AVAILABLE Run `npm i vercel@latest` to install Vercel CLI 25.1.0
> Changelog: https://github.com/vercel/vercel/releases/tag/vercel@25.1.0
Vercel CLI 24.2.5
? Set up “~/bin/vercel-github-images”? [Y/n] y
? Which scope should contain your project? asaitoshiya
? Found project “asaitoshiya/vercel-github-images”. Link to it? [Y/n] y
✅  Linked to asaitoshiya/vercel-github-images (created .vercel)
```

### crontab

```bash
0 * * * * export PATH=/usr/local/bin/:$PATH; cd /home/pi/bin/vercel-github-images && npm run deploy > /dev/null 2>&1
```

## npm スクリプト

```bash
$ npm run
Lifecycle scripts included in vercel-github-images@1.0.0:
  test
    echo "Error: no test specified" && exit 1

available via `npm run-script`:
  prebuild
    rm -rf public && mkdir public
  build
    octo-image involves --absolute-time --exclude-user AsaiToshiya --sort updated AsaiToshiya && octo-image contribution-graph AsaiToshiya && mv -f involves.png contribution-graph.png ./public
  deploy
    npm run build && vercel --prod

```