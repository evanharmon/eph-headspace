# JAVA KEYTOOL

## Check a Stand-Alone Certificate
`keytool -printcert -v -file mydomain.crt`

## Create New Keystore
```
keytool -genkey
  -alias mydomain
  -keyalg RSA
  -keystore KeyStore.jks
  -keysize 2048
```

## Change KeyStore Alias
```
keytool -changealias
  --keystore KeyStore.jks
  -alias oldalias
  -destalias newalias
```

## Import CA Cert to Java Keystore
Alias should be different from domain name
```
keytool -import
  -trustcacerts
  -alias my_specific_app_domain
  -file mydomain.crt
  -keystore keystore.jks
```

## Delete a Certificate from a Keystore
`keytool -delete -alias mydomain -keystore keystore.jks`

## Change a Java KeyStore Password
`keytool -storepasswd -new new_storepass -keystore keystore.jks`

## Common Errors
"keytool error: java.lang.Exception: Public keys in reply and keystore don't match"
(http://blog.donlangham.com/2013/06/java-keytool-dont-let-alias-fool-you.html)
Don't use the domain value in the alias value. ie. -alias home-domain cn=harmon.com
