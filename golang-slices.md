# GOLANG SLICES
(https://blog.golang.org/slices)

## General about Slices
NOT an array
slice describes a piece of an array

## Slice Headers
Contents of a slice can be edited but NOT the header
Copy of header is sent, must return a result parameter to affect header
`func SubtractOneFromLength(slice []byte) []byte { }`
