# vercel-github-involves

## セットアップ

### リポジトリ

```bash
git clone https://github.com/AsaiToshiya/vercel-github-involves.git
cd vercel-github-involves
npm install
```

### シンボリック リンク

```bash
sudo mkdir -p /opt/google/chrome
sudo ln -s /usr/bin/chromium-browser /opt/google/chrome/chrome
```

### Vercel

```bash
$ node ./node_modules/vercel/dist/index.js login to.asai.60@gmail.com
Vercel CLI 24.2.5
We sent an email to to.asai.60@gmail.com. Please follow the steps provided inside it and make sure the security code matches Wicked Frog.
> Success! Email authentication complete for to.asai.60@gmail.com
Congratulations! You are now logged in. In order to deploy something, run `vercel`.
💡  Connect your Git Repositories to deploy every branch push automatically (https://vercel.link/git).
```

```bash
$ node ./node_modules/vercel/dist/index.js link
> UPDATE AVAILABLE Run `npm i vercel@latest` to install Vercel CLI 25.1.0
> Changelog: https://github.com/vercel/vercel/releases/tag/vercel@25.1.0
Vercel CLI 24.2.5
? Set up “~/bin/vercel-github-involves”? [Y/n] y
? Which scope should contain your project? asaitoshiya
? Found project “asaitoshiya/vercel-github-involves”. Link to it? [Y/n] y
✅  Linked to asaitoshiya/vercel-github-involves (created .vercel)
```

### crontab

```bash
0 * * * * cd /home/pi/bin/vercel-github-involves && npm run deploy > /dev/null 2>&1
```

## npm スクリプト

```
$ npm run
Lifecycle scripts included in vercel-github-involves@1.0.0:
  test
    echo "Error: no test specified" && exit 1

available via `npm run-script`:
  prebuild
    rm -rf public && mkdir public
  build
    octo-image involves --absolute-time AsaiToshiya && mv -f involves.png ./public
  deploy
    npm run build && vercel --prod

```