# DATE UNIX

## Summary

Notes on working with unix timestamps / dates

## Resources

- [Linux Date Formats](https://www.thegeekstuff.com/2013/05/date-command-examples/)

## Convert Unix To String Date Format

```console
date -r 1558099332
```

## MM-DD-YYYY Save File

```console
$(date +%F).csv
```

## ISO 8601 Date Format

```console
date '+%Y-%m-%d'
```

## UTC Timestamp

```zsh
date +%FT%T
```

## UTC Timestamp + ms

example output: `2018-01-24T04:06:51.178Z`

```bash
date --utc +%FT%T.%3NZ
```
