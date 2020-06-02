# ANGULAR 1.5 PROTRACTOR

## Debug on Chrome Page
`browser.pause()`

## Debug in REPL
`browser.explore()`

## Debug in Node
`browser.debugger()`

## Explore inside a Test
```
it('should have a dialog title', function() {
    browser.explore();
}, 100000);
```

## Explore a page in a REPL without running a test
`$ protractor --elementExplorer`
`browser.get('http://www.angularjs.org');`

## Get element by ngModel
`element(by.model('user'))`

## Get element by binding such as '$scope.person.name'
`element(by.binding('person.name'))`

## Get ng-repeat element
`element.all(by.repeater('option in vm.host')).get(1).click()`

## Force tests to run in a specific order
change specs: array in proctractor.conf.js
```
specs: [
    'test/stories/login.js',
    'test/stories/home/overview.js',
    'test/stories/home/purchase/widget.js'
],
```

## Use Parameters with Protractor CLI
in conf.js file
`params: { baseUrl: 'http://localhost:3000' }`
in spec.js file
`browser.get(browser.params.baseUrl)`
in command line
`$ protractor --params.baseUrl`

## Quick fix for click element errors
aka 'other element would receive the click'
```
browser
  .executeScript('arguments[0].click()', element(by.buttonText('Panelboards')));
```

## Get Inner HTML or Outer HTML
when getText() doesn't work
`element().getAttribute('innerHTML')`

## Get a new chrome instance per spec file
edit protractor.conf file
`capabilities:{ 'shardTestFiles': true }`

## Set / Maximize Browser Window
```
browser.driver.manage().window().setSize(1280,800);
browser.driver.manage().window().maximize();
```

## Config - ways to run tests / browsers
First of all, currently, you have 5 different built-in options/ways to connect
to browser drivers:

- specify seleniumServerJar to start selenium standalone server locally
- specify seleniumAddress to connect to a running selenium server
  (local or remote)
- set sauceUser and sauceKey to connect to Sauce Labs remote selenium server
- set browserstackUser and browserstackKey to use remote Selenium Servers via
  BrowserStack
- use directConnect to connect to Chrome or Firefox directly. There are
  additional chromeDriver and firefoxPath setting that you can use to define
  custom Chrome driver and Firefox application binary locations

## Basic Chrome Setup
```
exports.config = {
    baseUrl: 'http://localhost:3000,
    framework: 'jasmine2',
    capabilities: {
        'browserName': 'chrome'
    },
    multiCapabilities: {
        'browserName': 'chrome'
    },
    specs: [
        path.join(__dirname, 'test', 'e2e', '**/*.spec.js')
    ],
    directConnect: true
}
```
