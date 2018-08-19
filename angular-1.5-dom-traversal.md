# ANGULAR 1.5 DOM TRAVERSAL

## Make sure Debug is turned on in Angular App
```
app.config(['$compileProvider', function ($compileProvider) {
 $compileProvider.debugInfoEnabled(true);
}]);
```

## Check Scope
Highlight HTML element in 'elements' of dev tools, then in console section
`$($0).scope()`

## Evaluate Binding Expressions
ng-bind attribute, great for directives and checking ng-model value
`$($0).data()`

## Interact with Services / Inject Service
in console
```
var e = angular.element($0)
var http = e.injector().get("http")
http.get("foo.json")
```

## ng-options for simple array
`ng-options="o as o for o in states"`

## Get data scope from element
Uses jquery
`$(elem).data();`

## Check modules and requires in Chrome
`console.log(angular.module('ModuleYouWantToInspect').requires);`

## Get Root of Scope
`$($0).scope().$root`

## Get Controller
`$($0).controller()`

## Check if scope has property/function
`$($0).parent().scope().hasOwnProperty('foo')`

## Get Isolate Scope
`$($0).isolateScope()`

## Get inherited data
don't need to set debug to true
`angular.element($0).inheritedData()`
