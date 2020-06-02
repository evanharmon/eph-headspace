# ANGULAR 1.5 INPUTS

## Set Mutually Exclusive checkboxes
```
<div class="form-group nmb">
     <input type="checkbox" ng-model="PaymentMethod" ng-true-value="true" ng-false-value="false">
     <label>Check</label>
     <input type="checkbox" ng-model="PaymentMethod" ng-true-value="false" ng-false-value="true">
     <label>Wire</label>
</div>
```

# Mutually Exclusive - Second Checkbox Default
```
<input type="checkbox" ng-model="PaymentMethod" ng-true-value="true">
<input type="checkbox" ng-model="PaymentMethod" ng-true-value="false">
```
