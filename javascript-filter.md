# JAVASCRIPT FILTERING

## Resources

## Chained Filter for nested JSON

`v.invoices.filter(i => i.Lines.filter(l => qty -= l.Quantity));`

## Use filtered array item then return array item

```
const bills = v.getBilledNonOverrunLines().filter(l => {
     qty += l.Quantity;
     total += l.TotalSell;
     return l;
});
```

# Filter based on allowed Key names

```
const allowed = ['IpRanges', 'IpProtocol', 'FromPort', 'ToPort'];
const filtered = Object.keys(prefixes[0])
  .filter(key => {
    return allowed.includes(key);
  }, {});
```

## Find Items In Array Missing From Another Array

```javascript
const missing = group1.filter(i => !group2.includes(i))
```
