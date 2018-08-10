# ANGULAR 1.5 DYNAMIC DIRECTIVE

## Dynamically add directive attribute with value
```
<td
  md-cell
  ng-repeat="featureInstance in list"
  ng-if="featureInstance.ID"
  ng-attr-block-ui="{{ currentData.inputtype === 'checkbox' ? 'checkbox' : undefined }}">
```
