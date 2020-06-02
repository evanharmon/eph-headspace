# ANGULAR 1.5 DIRECTIVES

## Two-Way Binding
Pass Object or Array to Directive
`scope: { ngModel: '=' }`

## Text Binding
Pass String to Directive (DOM Value binding)
`scope: { labelName: '@'}`

## One-Way Binding
`scope: { oneWayBind: "<" }`

## Pass Expression
`scope: { hideDialog: '&' }`

## Error Cannot Read Property 'length' of Undefined at addDirective
Make sure you are returning the delegate in your decorator
`return $delegate;`

## Get ngModelController From a Nested Directive During Event
`angular.element(e.target).data().$ngModelController`

## TypeError '{' on directive scope objects
caused by using '=' and object name with value {{}}
BAD example
```
scope: { defaultText: '=' };
<input placeholder="{{defaultText}}">
```

## Returning a function is shorthand for 'Link' function

## Add an Attribute to Directive Element
`elem.attr('Name', 'Value/Function')`

## Local Functions Keeping Scope
example html:
```
<div custom-function="functionName({ $item })></div>
scope.functionName({ $item: scope.valueName })
```
