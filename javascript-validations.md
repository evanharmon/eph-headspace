# JAVASCRIPT VALIDATIONS

## Check typeof
`typeof obj === "undefined"`
```
Undefined    "undefined"
Null    "object" (see below)
Boolean    "boolean"
Number    "number"
String    "string"
Symbol (new in ECMAScript 2015)    "symbol"
Function object (implements [[Call]] in ECMA-262 terms)    "function"
Any other object    "object"
```

## Check For Array
don't use typeof
`if (Array.isArray(myArr))`

# Check if Object
note have to exclude null first
`if (varName !== null && typeof varName === 'object')`

# Check if NaN
`isNan("010")`

# Check for null undefined NaN emptry string 0 false
`if (value) { }`
Evaluates to true if value is not:
* null
* undefined
* NaN
* empty string("")
* 0
* false

# Truthy
```
if (true)
if ({})
if ([])
if (42)
if ("foo")
if (new Date())
if (-42)
if (3.14)
if (-3.14)
if (Infinity)
if (-Infinity)
```

# Falsy
```
if (false)
if (null)
if (undefined)
if (0)
if (NaN)
if ('')
if ("")
if (document.all) [1]
```
