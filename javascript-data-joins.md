# JAVASCRIPT DATA JOINS

[JS Joins](http://learnjsdata.com/combine_data.html)

## Efficient Join Function
(http://stackoverflow.com/questions/17500312/is-there-some-way-i-can-join-the-contents-of-two-javascript-arrays-much-like-i/17500836#17500836)
```
function join(lookupTable, mainTable, lookupKey, mainKey, select) {
  var l = lookupTable.length,
  m = mainTable.length,
  lookupIndex = [],
  output = [];
  for (var i = 0; i < l; i++) { // loop through l items
    var row = lookupTable[i];
    lookupIndex[row[lookupKey]] = row; // create an index for lookup table
  }
  for (var j = 0; j < m; j++) { // loop through m items
    var y = mainTable[j];
    var x = lookupIndex[y[mainKey]]; // get corresponding row from lookupTable
    output.push(select(y, x)); // select only the columns you need
  }
  return output;
};
```

## Example Use
```
const result = join(brands, articles, "id", "brand_id", (article, brand) =>
  {
    id: article.id,
    name: article.name,
    weight: article.weight,
    price: article.price,
    brand: (brand !== undefined) ? brand.name : null
  });
console.log(result);
```

# Left Outer Join

```
articles.forEach(article => {
    const result = brands.filter(brand => brand.id === article.brand_id);
    article.brand = (result[0] !== undefined) ? result[0].name : null;
});

```

# Join More Than One Attribute Inner Array
reference outer part above
```
innerArray.filter(innerArrayItem =>
  ((innerArrayItem.idA === outerArrayItem.idA) &&
  (innerArrayItem.idB === outerArrayItem.idB));
);
```
