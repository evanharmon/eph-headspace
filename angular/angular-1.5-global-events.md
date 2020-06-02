# ANGULAR 1.5 GLOBAL EVENTS

## Bind to global event
clickHandler is separate function - important to have handler id to turn off
on $destroy
```
const bodyElem = angular.element(document.body);
bodyElem.on('click', clickHandler);
```

## Remember to Release Event Handler on Destroy!!!
`scope.$on('$destroy', () => { elem.off('click', clickHandler); }`
