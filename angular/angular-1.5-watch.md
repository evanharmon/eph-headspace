# ANGULAR 1.5 WATCH

## Watch a Controller as Syntax Variable
```
$scope.$watch(angular.bind(this, function() {
     return this.varName;
}), function (newVal) {
    console.log('newVal', newVal);
});
```
or
```
$scope.$watch('myCtrlr.Selection', function (newVal) {
     console.log('newVal', newVal);
});
```
