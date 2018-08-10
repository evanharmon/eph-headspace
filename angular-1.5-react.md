# ANGULAR 1.5 REACT

## Directive to use React
(https://github.com/ngReact/ngReact)
then call:
```
React.render(
    React.createElement(MyElement, {}),
    element.find('.react-container').get(0)
);
```

## Create module to get data to React
[Flux Stores]
(https://www.bimeanalytics.com/engineering-blog/you-put-your-react-into-my-angular/)
```
module BimeQueryMeasuresStore {
    export var blender: OLAP.CubeModel.Blender;
    export var checkboxModelKey: string;
    export var measuresSearch: string;
};
```

## Use Helper Function Trigger Events to Get Data to react
```
function $broadcast(event: string, ...args: any[]) {
    angular.element('body').injector().invoke([
        '$rootScope',
        '$timeout',
        ($rootScope: ng.IRootScopeService, $timeout: ng.ITimeoutService) =>
        {
            args.unshift(event);
            $timeout(() => {
                $rootScope.$broadcast.apply($rootScope, args);
            });
        }
    ]);
}
```
use
`$broadcast('update_data', {updatedFrom: 'React'})`

Each ng-repeat turns in to a React component which is a list of more React
components
