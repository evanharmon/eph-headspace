# APPIUM WEB APP TESTING

## Summary

Notes on using appium with nodejs for mobile web app testing

## Resources

[Getting Started](http://appium.io/docs/en/about-appium/getting-started/)
[Mobile Web Testing](http://appium.io/docs/en/writing-running-appium/web/mobile-web/)

## WEBDRIVER.io

[Getting Started WDIO](https://webdriver.io/docs/gettingstarted.html)
[Appium Service](http://appium.io/docs/en/writing-running-appium/web/mobile-web/)

#### Base Appium Server Config

[Github Example](https://github.com/webdriverio/appium-boilerplate/blob/master/config/wdio.android.browser.conf.js)

```javascript
const opts = {
  port: 4723,
  capabilities: {
    platformName: "Android",
    platformVersion: "8.0",
    deviceName: "Android Emulator",
    app: "/path/to/the/downloaded/ApiDemos.apk",
    automationName: "UiAutomator2"
  }
};

const client = wdio.remote(opts);
```
