# OPENSSL LINKING

## Summary

Notes on linking openssl for make

## Fixes Below Error

your binary is not an allowed client of /usr/lib/libcrypto.dylib

```console
sudo ln -s /usr/local/Cellar/openssl@1.1/1.1.1g/lib/libcrypto.1.1.dylib /usr/local/lib/libcrypto.dylib
sudo ln -s /usr/local/Cellar/openssl@1.1/1.1.1g/lib/libssl.1.1.dylib /usr/local/lib/libssl.dylib
cmake -DOPENSSL_CRYPTO_LIBRARY="/usr/local/lib/libcrypto.dylib" -DOPENSSL_SSL_LIBRARY=/usr/local/lib/libssl.dylib
```
