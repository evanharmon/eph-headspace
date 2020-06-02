# HTML QUERY SELECTOR

## Search DOM for CSS class selectors and return first result
```
<div class="row"/>
document.querySelector("div.row")
```

## Search DOM for CSS class selectors and return all results
```
<div class="row"/>
document.querySelectorAll("div.row")
```

## Search DOM for attributes and return all results
```
<input typeahead=""/>
document.querySelectorAll("[typeahead]")
```

## Search DOM for multiple attributes and return all results
`document.querySelectorAll('ul[typeahead-popup][aria-hidden="false"]')`

## Iterate over Nodelist
```
let forEachNode = (array, callback, scope) => {
  for (var i = 0; i < array.length; i++) {
    callback.call(scope, i, array[i]);
  }
};

let hidePopups = elem => {
  const popupList = popupQuery(bodyElem);
  forEachNode(popupList, (index, value) => {
    scope.activeIdx = -1;
    scope.matches = [];
    scope.$apply();
  });
};
```
