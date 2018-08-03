# OPENSSL GENERAL

## Decode Base64
`$ openssl base64 -d -in <infile> -out <outfile>`

## Encode Base64
`$ openssl base64 -in <infile> -out <outfile>`

## View Thumbprint
`$ openssl x509 -in CERT_FILE -serial -noout`

## View Serial
`$ openssl x509 -in CERT_FILE -fingerprint -noout`

## Generate RSA Private Key
`$ openssl genrsa -out filename 2048`
