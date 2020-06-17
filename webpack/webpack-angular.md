# Ways to Expose Angular
```
    plugins: [
          new webpack.ProvidePlugin({
               'angular': 'angular/angular.min.js'
          })]

               { test: /[\/\\]angular\.js$/, loader: 'exports-loader?angular' }

  externals: {
    'angular': 'angular'
  }
```

# Dynamic requires in directives
## have to explicitly require outside of directive
```
require('./templates/first-header-template.html');
require('./templates/second-header-template.html')

export default function DefaultHeaderDirective($rootScope, sessionService) {
     return {
          restrict: 'E',
          template: '<div ng-include="require(template())"></div>',
          replace: true,
          scope: {
               templateName:'@'
          },
          link: function (scope, element, attrs) {
               scope.template = function () {
                    var _templateName = "default";
                    if (scope.templateName) {
                         _templateName = scope.templateName;
                    }
                    return "app/main/directives/templates/" + _templateName + "-header-template.html";
               }
          }
     };
}
```
