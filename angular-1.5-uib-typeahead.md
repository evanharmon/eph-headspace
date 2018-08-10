# ANGULAR 1.5 UIB-TYPEAHEAD

## Use different object properties for selection and display in a directive
(https://angular-ui.github.io/bootstrap/)
```
<input
  type="text"
  ng-model="ngModel"
  uib-typeahead="a.Id as a.Id + ' ' + a.Name for a in refreshOpts($viewValue) | orderBy: 'Name'"
  />
```
