# JAVASCRIPT SPREAD REST OPERATORS
[article]
(http://www.datchley.name/es6-rest-spread-defaults-and-destructuring/)

## Spread Array Parameters Out Single-File
```
let first = [1,2,3];
let second = [4,5,6];
first.push(second); // [1,2,3,[4,5,6]]
first.push(...second); // [1,2,3,4,5,6]
```

## Using Object Spread Operator to Avoid Object.assign()
```
function todoApp(state = initialState, action) {
  switch (action.type) {
    case SET_VISIBILITY_FILTER:
      return Object.assign({}, state, {
        visibilityFilter: action.filter
      })
    default:
      return state
  }
}
```

```
function todoApp(state = initialState, action) {
  switch (action.type) {
    case SET_VISIBILITY_FILTER:
      return { ...state, visibilityFilter: action.filter }
    default:
      return state
  }
}
```

## Rest Operator to Multiply
```
function multiply(multiplier, ...theArgs) {
  return theArgs.map(function (element) {
    return multiplier * element;
  });
}

const arr = multiply(2, 1, 2, 3);
console.log(arr); // [2, 4, 6]
```

## Rest Operator to sum
```
const sumCosts = (...costs) => {
     let sum = 0;
     costs.map(i => sum += i);

     return sum;
};
```

## Rest Operator to average
```
const averageUnitCost = (...costs) => {
     let sum = 0;
     let qty = costs.length;
     costs.map(i => sum += i);

     return sum / qty;
};
```
