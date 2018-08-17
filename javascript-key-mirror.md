# JAVASCRIPT Key Mirror function
```
['Apple', 'Banana', 'Orange'].reduce((m, v) => {
    m[v] = v;
    return m;
  },
  {}
);
```

```
var arry = ["Apple", "Banana", "Orange"];
const map = arry.reduce((obj, str) => {
    obj[str] = str;
    return obj;
  },
  {}
);
```
