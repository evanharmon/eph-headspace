# ANGULAR 1.5 SERVICES

## Log an Angular Service
```
var elem = angular.element(document.getElementById('controller'));
console.log("$scope: ", elem.scope());
console.log("$sce: ", elem.injector().get('$sce'));
```

## Don't Rename Injected Services in Files
makes it harder to debug
```
export default function AckService(tooLongServiceName) {
  let _svc = tooLongServiceName;
}
```
