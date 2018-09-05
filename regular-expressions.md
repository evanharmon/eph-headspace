# REGULAR EXPRESSIONS

## Or
|
`grey|gray`

## Capturing Group
()
`gr(a|e)y`

## Start Of Line
^
`^begin`

## End Of Line
$
`grey$`

## Match Any Single Character
.
`begin.` matches begins

## Match 0 Or 1 Occurrence
?
`colou?r` matches color or colour

## Match 0 Or More Occurrences
*
`ab*c` matches ac, abc, abbc, etc

## Match 1 Or More Occurrences
+
`ab+c` matches abc, abbc, but not ac

## Match Exactly N Times
`{n}`

## Match Min / Max Times
`{min,max}`
