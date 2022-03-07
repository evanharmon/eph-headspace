# OPENSSL CONVERT

## Convert a certificate from PEM to DER
`$ openssl x509 -in input.crt -inform PEM –out output.crt -outform DER`

## Convert a certificate from DER to PEM
`$ openssl x509 -in input.crt -inform DER -out output.crt -outform PEM`

## Convert a key from PEM to DER
`$ openssl rsa -in input.key -inform PEM -out output.key -outform DER`

## Convert a key from DER to PEM
`$ openssl rsa -in input.key -inform DER -out output.key -outform PEM`

## Convert a PKCS#12 file (.pfx .p12) containing a private key / cert to PEM
You can add -nocerts to only output the private key or add -nokeys to only
output the certificates
`$ openssl pkcs12 -in keyStore.pfx -out keyStore.pem -nodes`

## Convert a PEM certificate file and a private key to PKCS#12 (.pfx .p12)
```
$ openssl pkcs12 \
    -export \
    -out certificate.pfx \
    -inkey privateKey.key \
    -in certificate.crt \
    -certfile CACert.cr
```
