# ANGULAR 1.5 PROVIDERS

## Naming and Using a Provider
Don't add 'Provider' to the end - Angular will do that
```
angular
 .module('productSelector', ['app.core'])
 .provider('envService', envServiceProvider)

export default function config(envServiceProvider) {}
```
