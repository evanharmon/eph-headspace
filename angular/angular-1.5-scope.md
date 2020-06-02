# ANGULAR 1.5 SCOPE

## Prevent apply digest error / too much firing
`if (!scope.$$phase) scope.$apply(); // directive version`
