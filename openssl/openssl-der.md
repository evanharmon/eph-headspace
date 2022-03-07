# OPENSSL DER

## Error on openssl out if file is PEM
unable to load certificate
13978:error:0D0680A8:asn1 encoding routines:ASN1_CHECK_TLEN:wrong
tag:tasn_dec.c:1306:

13978:error:0D07803A:asn1 encoding routines:ASN1_ITEM_EX_D2I:nested asn1
error:tasn_dec.c:380:Type=X509

## View PEM Certificate in Console
`$ openssl x509 -in spCert.pem -inform DER -noout -text`
