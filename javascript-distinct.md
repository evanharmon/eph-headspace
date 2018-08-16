# JAVASCRIPT DISTINCT

## Single Property Distinct For Array of Objects
```
let unique = {};
let distinct = [];
array.forEach(x => {
  if (!unique[x.age]) {
    distinct.push(x.age);
    unique[x.age] = true;
  }
});
```

## removeDuplicates
```
function removeDuplicates(myArr, prop1, prop2) {
  return myArr.filter((obj, pos, arr) => {
    const check = arr
      .map(mapObj => `${mapObj[prop1]}-${mapObj[prop2]}`)
      .indexOf(`${obj[prop1]}-${obj[prop2]}`) === pos;
    return check;
    });
    const uniqueMileage = removeDuplicates(
      orderMiles,
      'OrderNo',
      'Location',
      'Method'
    );
}
```
