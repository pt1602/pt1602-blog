---
title: M1 DDEV Chromium
author: pt1602
date: 2022-11-29T08:00:00+00:00
---

On one of my colleagues got the following error on his M1-Macbook while running `bin/build-storefront.sh`.

## Error Message

```shell
V8 engine whims, feature detection in old core-js versions could cause a slowdown up to 100x even if nothing is polyfilled. Some versions have web compatibility issues. Please, upgrade your dependencies to the actual version of core-js.
npm ERR! code 1
npm ERR! path /var/www/html/vendor/shopware/storefront/Resources/app/storefront/node_modules/puppeteer
npm ERR! command failed
npm ERR! command sh /tmp/install-9c2094bf.sh
npm ERR! The chromium binary is not available for arm64.
npm ERR! If you are on Ubuntu, you can install with: 
npm ERR! 
npm ERR!  sudo apt install chromium
npm ERR! 
npm ERR! 
npm ERR!  sudo apt install chromium-browser
npm ERR! 
npm ERR! /var/www/html/vendor/shopware/storefront/Resources/app/storefront/node_modules/puppeteer/lib/cjs/puppeteer/node/BrowserFetcher.js:115
npm ERR!                     throw new Error();
npm ERR!                     ^
npm ERR! 
npm ERR! Error
npm ERR!     at /var/www/html/vendor/shopware/storefront/Resources/app/storefront/node_modules/puppeteer/lib/cjs/puppeteer/node/BrowserFetcher.js:115:27
npm ERR!     at FSReqCallback.oncomplete (node:fs:206:21)
```

As a workaround we added `--ignore-scripts --legacy-peer-deps` to every `npm install` or `npm clean-install` in the `build-storefront.sh`.

