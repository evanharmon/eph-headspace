# JAVASCRIPT DATES

## Set Date Timestamp One Hour Ahead

```javascript
new Date(new Date().getTime() + 60 * 60 * 1000);
```

## Display Date Object as GMT

```javascript
new Date().toGMTString();
```

## Display Date Object as ISO

```javascript
new Date().toISOString();
```

## Check if Valid Date

```javascript
dt instanceof Date;
```

## Get Start of Month

MomentJS is easiest - remember it's 0 based index

```javascript
const dt = moment().startOf("month");
```

## New Date to ZULU string

```javascript
new Date().toJSON();
```

## SAP / Couchbase Formats

```javascript
const cbFormat = ‘MM/DD/YYYY’;
const sapFormat = ‘YYYYMMDD’;
moment(startDate, cbFormat).format(sapFormat)
```

## Get Unix Timestamp

```javascript
new Date().valueOf();
```

may need to limit to 10 digits for int

```javascript
new Date()
  .valueOf()
  .toString()
  .substring(0, 10);
```

## Create New Date Object From UNIX Timestamp Int

timestamp will be 10 digits instaed of 14, add padded 0s

```javascript
const ts = 1559088000;
new Date(parseInt(`${ts}0000`));
```

## Check If Date Object

[SO](https://stackoverflow.com/questions/643782/how-to-check-whether-an-object-is-a-date)

```javascript
const dt = new Date(1557931407000);
console.log(dt instanceof Date);
```
