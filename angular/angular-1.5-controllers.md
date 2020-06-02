# ANGULAR 1.5 CONTROLLERS

## Add a Controller to Another Controller
```
function ($controller) {
   $controller('OtherController as otherCtrl', {$scope: $scope});
   let baseCtrl = $scope.otherCtrl;
}
```
