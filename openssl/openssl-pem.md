# OPENSSL PEM

## Error on opening if file is actually DER
unable to load certificate
12626:error:0906D06C:PEM routines:PEM_read_bio:no
start line:pem_lib.c:647:Expecting: TRUSTED CERTIFICATE View DER encoded
Certificate

## View PEM Certificate in Console
`$ openssl x509 -in spCert.pem -inform PEM -noout -text`
