# ANGULAR 1.5 COMMON PROBLEMS

## Input is Creating Strings Out of Numbers
the reason i was getting them back as strings, is my property was new, meaning
not set. Two options were to initialize the property to 0 so that angular
would recognize it as a number or add a `ng-init` to the field

## Input is not changing to blank when disabled
```
  // initialize fields on radio, clear fields on de-selected radio
  $scope.$watch(angular.bind(this, function() {
    return this.Selection;
  }), function (newVal) {
    if (newVal === 'costOverrun') {
      v.unitCost = '';
      v.unposted.originalQtyUnitCost = angular.copy(v.lineItem.UnitCost);
      v.unposted.unitCostOverrun = angular.copy(v.lineItem.UnitCost);
    }

    if (newVal === 'unitCost') {
      v.unitCost = v.lineItem.UnitCost;
      v.unposted.originalQtyUnitCost = '';
      v.unposted.unitCostOverrun = '';
    }
  });
```

# EncodeUriSegment is not a Function
You have version conflicts in your npm/bower installs. Different angular
versions - might be due to dependencies in package.json not being locked down
