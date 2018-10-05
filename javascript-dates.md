# JAVASCRIPT DATES

## Set Date Timestamp One Hour Ahead
```javascript
new Date((new Date()).getTime() + (60 * 60 * 1000));
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
dt instanceof Date
```

## Get Start of Month
MomentJS is easiest - remember it's 0 based index
```javascript
const dt = moment().startOf('month')
```

## New Date to ZULU string
```javascript
new Date().toJSON()
```

## SAP / Couchbase Formats
```javascript
const cbFormat = ‘MM/DD/YYYY’;
const sapFormat = ‘YYYYMMDD’;
moment(startDate, cbFormat).format(sapFormat)
```
## Get Unix Timestamp
```javascript
new Date().valueOf()
```
