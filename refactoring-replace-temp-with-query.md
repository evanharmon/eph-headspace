# REFACTORING REPLACE TEMP WITH QUERY
## Scenario
Using a temp variable to hold result of expression

## Refactor Strategy
Extract the expression into a method. Replace all references to the temp with
the new method. The new method can then be used in other methods
