# ANGULAR 1.5 BLOCK-UI

## Basic block-ui config with no overlay
```
import 'angular-block-ui';
angular
    .module('myModule', ['blockUI'])
    .config(function (blockUIConfig) {
        // disable auto blocking on all $http service calls
        blockUIConfig.autoBlock = false;
        // disable auto injecting block on <body>
        blockUIConfig.autoInjectBodyBlock = false;
        // blank overlay
        blockUIConfig.template = '<div></div>';
    })

# Basic use in html
# block-ui grouping is 'main' below
<div block-ui="main"></div>

# Basic useage in js files
blockUI.start()
blockUI.stop()
```
