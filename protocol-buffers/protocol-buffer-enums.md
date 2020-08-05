# PROTOCOL BUFFER ENUMS
always make the first value `unknown` since it will be the default

## Default
first item in the enum

## Changes
`reserved` keyword can be used

## Example
```
enum DayOfTheWeek {
  DAY_OF_THE_WEEK_UNSPECIFIED = 0;
  MONDAY = 1;
  TUESDAY = 2;
  WEDNESDAY = 3;
  THURSDAY = 4;
  FRIDAY = 5;
  SATURDAY = 6;
  SUNDAY = 7;
}
```
