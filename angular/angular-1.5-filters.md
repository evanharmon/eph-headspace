# ANGULAR 1.5 FILTERS

## Wildcard * Asterisk Search
`uib-typeahead="method.Name for method in v.myMethods | filter: $"`

## Currency beyond 2 decimals
`{{lineItem.UnitCost | currency: order.Currency.Name : 4}}`

## Currency Filtering on Inputs
Remember to change on blur
```
  const currencySymbol = () => {
    if (angular.isDefined(scope.currencySymbol)) {
      return scope.currencySymbol;
    } else {
      return $locale.NUMBER_FORMATS.CURRENCY_SYM;
    }
  };

  if (attr.showcurrency) {
    ctrl.$formatters.push(function (val) {
      if (val && attr.showcurrency) {
        return $filter('currency')(val, currencySymbol(), attr.fraction);
      }

      return val;
    });
  }
```
