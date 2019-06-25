# GOLANG DATE TIME

## Current Time

`t := time.Now()`

## Formatting

```
t := time.Now()
fmt.Println(t.Format("20060102150405"))
```

as Go uses following constants to format date,refer here

```
const (
  stdLongMonth = "January"
  stdMonth = "Jan"
  stdNumMonth = "1"
  stdZeroMonth = "01"
  stdLongWeekDay = "Monday"
  stdWeekDay = "Mon"
  stdDay = "2"
  stdUnderDay = "_2"
  stdZeroDay = "02"
  stdHour = "15"
  stdHour12 = "3"
  stdZeroHour12 = "03"
  stdMinute = "4"
  stdZeroMinute = "04"
  stdSecond = "5"
  stdZeroSecond = "05"
  stdLongYear = "2006"
  stdYear = "06"
  stdPM = "PM"
  stdpm = "pm"
  stdTZ = "MST"
  stdISO8601TZ = "Z0700" // prints Z for UTC
  stdISO8601ColonTZ = "Z07:00" // prints Z for UTC
  stdNumTZ = "-0700" // always numeric
  stdNumShortTZ = "-07" // always numeric
  stdNumColonTZ = "-07:00" // always numeric
)
```

## Current Zulu Time

`t.Format(time.RFC3339)`

## Timer

```golang
duration := time.Duration(10) * time.Second
time.Sleep(duration)
```
