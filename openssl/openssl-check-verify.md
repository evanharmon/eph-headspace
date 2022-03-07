# OPENSSL CHECK VERIFY

## Check a Certificate Signing Request (CSR)
`$ openssl req -text -noout -verify -in CSR.csr`

## Check a private key
`$ openssl rsa -in privateKey.key -check`

## Check a certificate
`$ openssl x509 -in certificate.crt -text -noout`

## Check a PKCS#12 file (.pfx or .p12)
`$ openssl pkcs12 -info -in keyStore.p12`

## Check binary
`$ hexdump -C privateKey.key`

## Online resource to check Cert
(https://www.sslshopper.com/certificate-decoder.html)

## openssl/bio.h can't be found
on mac, openssl is in `/opt/`
```
$ ./configure \
    LDFLAGS='-L/usr/local/opt/openssl/lib' \
    CPPFLAGS='-I/usr/local/opt/openssl/include'
```
