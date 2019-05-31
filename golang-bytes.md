# GOLANG BYTES

## Summary

Notes on working with bytes and binary data in golang

## Convert Single Byte To Int

`num := int(byte(4))`

## Convert String To Binary Bytes

shorter way `[]byte("PK\x03\x04")`

```golang
func toBinaryBytes(s string) string {
	var buffer bytes.Buffer
	for i := 0; i < len(s); i++ {
		fmt.Fprintf(&buffer, "%b", s[i])
	}
	return fmt.Sprintf("%s", buffer.Bytes())
}
```
