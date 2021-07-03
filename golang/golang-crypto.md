# GOLANG CRYPTO

## Summary

Notes on using the crypto package in golang

## Resources

- [Crypto Package](https://golang.org/pkg/crypto/sha256/)

## Create Hex Encoded SHA256

```golang
package main

import (
    "crypto/sha1"
    "encoding/hex"
)

func main() {
    s := "sha1 this string"
    h := sha1.New()
    h.Write([]byte(s))
    sha1_hash := hex.EncodeToString(h.Sum(nil))
}
```
