# ANGULAR 1.5 OC LAZY LOAD

## Lazy Load a Controller
```
  resolve: {
        deps: ['$q', function($q) {
            var deferred = $q.defer();
            require.ensure([], function (require) {
                $controllerProvider.register("HomepageController", require('./controllers/HomepageController'));
                deferred.resolve();
            }, '_homepage');
            return deferred.promise;
        }]
    }
```
