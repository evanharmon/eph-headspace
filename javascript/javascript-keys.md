# JAVASCRIPT KEYS

## Iterate Through Keys
`Object.keys(Obj).forEach(function(key){ });`

## Iterate Through Keys and Exit On First Match
`Object.keys(Obj).some(function(key){ });`

## Iterate through Array and transform to Object True
```
function transformPaymentOptions(array, obj) {
  return new Promise((resolve, reject) => {
    if (!array || !obj) {
      resolve();
    }

    array.forEach(arrKey => {
      Object.keys(obj).some(objKey => {
        if (objKey === arrKey) {
          obj[objKey] = true;
        }
      });

    });

    resolve();
  });
}
```
