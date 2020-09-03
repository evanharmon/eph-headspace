# OPENSSL GENERAL

## Decode Base64

```console
openssl base64 -d -in <infile> -out <outfile>
```

## Encode Base64

```console
openssl base64 -in <infile> -out <outfile>
```

## View Thumbprint

```console
openssl x509 -in CERT_FILE -serial -noout
```

## View Serial

```console
openssl x509 -in CERT_FILE -fingerprint -noout
```

## Generate RSA Private Key

```console
openssl genrsa -out filename 2048
```
