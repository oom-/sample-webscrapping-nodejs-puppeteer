# Sample
```js
var FS = require('fs');
const puppeteer = require("puppeteer-extra");
const pluginStealth = require("puppeteer-extra-plugin-stealth")
puppeteer.use(pluginStealth())

const SHOWBROWSER = true;
const ChromeUserAgent = "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/78.0.3904.108 Safari/537.36";

puppeteer.launch({ headless: !SHOWBROWSER, userDataDir: './puppeteer_data' }).then(async browser => {
    const page = await browser.newPage()
    await page.setViewport({ width: 1024, height: 1080 })
    await page.setUserAgent(ChromeUserAgent);
    await page.goto('https://www.google.com/');
    await page.waitFor(5000);
});
```