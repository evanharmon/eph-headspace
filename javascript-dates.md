# JAVASCRIPT DATES

## Set Date Timestamp One Hour Ahead
`new Date((new Date()).getTime() + (60 * 60 * 1000));`

## Display Date Object as GMT
`new Date().toGMTString();`

## Display Date Object as ISO
`new Date().toISOString();`

## Check if Valid Date
`dt instanceof Date`

## Get Start of Month
MomentJS is easiest - remember it's 0 based index
`const dt = moment().startOf('month')`

## New Date to ZULU string
`new Date().toJSON()`

## SAP / Couchbase Formats
```
const cbFormat = ‘MM/DD/YYYY’;
const sapFormat = ‘YYYYMMDD’;
moment(startDate, cbFormat).format(sapFormat)
```
