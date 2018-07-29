# SSL TLS CERTIFICATES
[Best Practices]
(https://spaces.internet2.edu/display/InCFederation/X.509+Certificates+in+Metadata)

## Create Self Signed Keys/Cert for Metadata
do not use -nodes option if you want to set a passphrase
```
openssl req -new -x509 -newkey rsa:2048 -keyout key.pem -days 3650 \
     -subj "/CN=hostname.example.org" -out cert.pem -nodes
```
