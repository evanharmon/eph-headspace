# JAVASCRIPT ARRAYS

## Filter Nested Array of Objects

```javascript
arr.reduce((a, b) => a.concat(b)).filter(obj => obj.id == ID)
```

## Ensure a reduce returns an array

```javascript
return [myarray].reduce((acc, curr) => {})
```

## Concat Array

`[].concat([1,2,3]);` WONT WORK

```javascript
let arr1 = []
let arr2 = [1, 2, 3]
arr2.concat(arr1)
```

## Flatten nested array

`const orderList = orders.reduce((a, b) => a.concat(b.location));`

## Reduce and avoid mutations

`const orderList = orders.reduce((a,b) => [...results, acc]);`

## Flatten nested array to new array

`const orderList = orders.reduce((a, b) => a.concat(b.location), []);`

## Array indexOf on Objects

have to use findIndex instead

```javascript
const target = { name: 'Josh' }
const targetKeys = Object.keys(target)
const index = test.findIndex(entry => {
  const keys = Object.keys(entry)
  return (
    keys.length == targetKeys.length &&
    keys.every(key => target.hasOwnProperty(key) && entry[key] === target[key])
  )
})
```

## Create Array of values from Array of Objects

`items.map(i => i.OrderNo);`

## Return a new array from a reduce

Have to return array item every iteration!!

```javascript
const orderIds = wcRes.body.results.reduce((arr, doc) => {
  if (doc.id && doc.id !== '_user/GUEST') {
    arr.push(doc.id)
  }
  return arr
}, [])
```

## Extra ways

```javascript
;[...set]
;[...set.keys()]
;[...set.values()]
Array.from(set)
Array.from(set.keys())
Array.from(set.values())
```

## Easier to read indexOf check

instead of OrderNo.indexOf(i.doc.OrderID) !== -1

```javascript
OrderNo.includes(i.doc.OrderID)
```

## Stringify Array of Strings

yes it is this simple

```javascript
;['one', 'two', 'three'].toString()
```
