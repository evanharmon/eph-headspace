# ANGULAR 1.5 EMITS

## Emits
```
myApp.config(['$provide', function ($provide) {
  $provide.decorator('$rootScope', function ($delegate) {
    var _emit = $delegate.$emit;

    $delegate.$emit = function () {
      console.log.apply(console, arguments);
      _emit.apply(this, arguments);
    };

    return $delegate;
  });
}]);
```
