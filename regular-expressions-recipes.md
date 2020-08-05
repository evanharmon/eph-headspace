# REGEX RECIPES

## Summary

Regular expression recipes

## Internet Protocol (IP)

### IPv4 /26 CIDR Block

`^([0-9]{1,3}).([0-9]{1,3}).([0-9]{1,3}).([0!64!128])\/26$`

### IPv4 /24 CIDR Block

`^(([01]?[0-9]?[0-9]|2[0-4][0-9]|25[0-5])).(([01]?[0-9]?[0-9]|2[0-4][0-9]|25[0-5])).(([01]?[0-9]?[0-9]|2[0-4][0-9]|25[0-5])).([0])\/24$`

### IPv4 /22 CIDR Block

`^(([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])\.){3}([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])(\/([0-9]|[1-2][0-9]|3[0-2]))$`

### 0 000 to 255

`^([01]?[0-9]?[0-9]|2[0-4][0-9]|25[0-5])$`

### 0 000 to 127

`^(0?[0-9]?[0-9]|1[01][0-9]|12[0-7])$`

### IPv6 Address

`^s*((([0-9A-Fa-f]{1,4}:){7}([0-9A-Fa-f]{1,4}|:))|(([0-9A-Fa-f]{1,4}:){6}(:[0-9A-Fa-f]{1,4}|((25[0-5]|2[0-4]d|1dd|[1-9]?d)(.(25[0-5]|2[0-4]d|1dd|[1-9]?d)){3})|:))|(([0-9A-Fa-f]{1,4}:){5}(((:[0-9A-Fa-f]{1,4}){1,2})|:((25[0-5]|2[0-4]d|1dd|[1-9]?d)(.(25[0-5]|2[0-4]d|1dd|[1-9]?d)){3})|:))|(([0-9A-Fa-f]{1,4}:){4}(((:[0-9A-Fa-f]{1,4}){1,3})|((:[0-9A-Fa-f]{1,4})?:((25[0-5]|2[0-4]d|1dd|[1-9]?d)(.(25[0-5]|2[0-4]d|1dd|[1-9]?d)){3}))|:))|(([0-9A-Fa-f]{1,4}:){3}(((:[0-9A-Fa-f]{1,4}){1,4})|((:[0-9A-Fa-f]{1,4}){0,2}:((25[0-5]|2[0-4]d|1dd|[1-9]?d)(.(25[0-5]|2[0-4]d|1dd|[1-9]?d)){3}))|:))|(([0-9A-Fa-f]{1,4}:){2}(((:[0-9A-Fa-f]{1,4}){1,5})|((:[0-9A-Fa-f]{1,4}){0,3}:((25[0-5]|2[0-4]d|1dd|[1-9]?d)(.(25[0-5]|2[0-4]d|1dd|[1-9]?d)){3}))|:))|(([0-9A-Fa-f]{1,4}:){1}(((:[0-9A-Fa-f]{1,4}){1,6})|((:[0-9A-Fa-f]{1,4}){0,4}:((25[0-5]|2[0-4]d|1dd|[1-9]?d)(.(25[0-5]|2[0-4]d|1dd|[1-9]?d)){3}))|:))|(:(((:[0-9A-Fa-f]{1,4}){1,7})|((:[0-9A-Fa-f]{1,4}){0,5}:((25[0-5]|2[0-4]d|1dd|[1-9]?d)(.(25[0-5]|2[0-4]d|1dd|[1-9]?d)){3}))|:)))(%.+)?s*`

### IPv6 CIDR Block

`^s*((([0-9A-Fa-f]{1,4}:){7}([0-9A-Fa-f]{1,4}|:))|(([0-9A-Fa-f]{1,4}:){6}(:[0-9A-Fa-f]{1,4}|((25[0-5]|2[0-4]d|1dd|[1-9]?d)(.(25[0-5]|2[0-4]d|1dd|[1-9]?d)){3})|:))|(([0-9A-Fa-f]{1,4}:){5}(((:[0-9A-Fa-f]{1,4}){1,2})|:((25[0-5]|2[0-4]d|1dd|[1-9]?d)(.(25[0-5]|2[0-4]d|1dd|[1-9]?d)){3})|:))|(([0-9A-Fa-f]{1,4}:){4}(((:[0-9A-Fa-f]{1,4}){1,3})|((:[0-9A-Fa-f]{1,4})?:((25[0-5]|2[0-4]d|1dd|[1-9]?d)(.(25[0-5]|2[0-4]d|1dd|[1-9]?d)){3}))|:))|(([0-9A-Fa-f]{1,4}:){3}(((:[0-9A-Fa-f]{1,4}){1,4})|((:[0-9A-Fa-f]{1,4}){0,2}:((25[0-5]|2[0-4]d|1dd|[1-9]?d)(.(25[0-5]|2[0-4]d|1dd|[1-9]?d)){3}))|:))|(([0-9A-Fa-f]{1,4}:){2}(((:[0-9A-Fa-f]{1,4}){1,5})|((:[0-9A-Fa-f]{1,4}){0,3}:((25[0-5]|2[0-4]d|1dd|[1-9]?d)(.(25[0-5]|2[0-4]d|1dd|[1-9]?d)){3}))|:))|(([0-9A-Fa-f]{1,4}:){1}(((:[0-9A-Fa-f]{1,4}){1,6})|((:[0-9A-Fa-f]{1,4}){0,4}:((25[0-5]|2[0-4]d|1dd|[1-9]?d)(.(25[0-5]|2[0-4]d|1dd|[1-9]?d)){3}))|:))|(:(((:[0-9A-Fa-f]{1,4}){1,7})|((:[0-9A-Fa-f]{1,4}){0,5}:((25[0-5]|2[0-4]d|1dd|[1-9]?d)(.(25[0-5]|2[0-4]d|1dd|[1-9]?d)){3}))|:)))(%.+)?s*(\/(d|dd|1[0-1]d|12[0-8]))$`

## At least one character in string

`/^[A-Za-z]+$/`

## Hostname

`^(([a-zA-Z]|[a-zA-Z][a-zA-Z0-9-]*[a-zA-Z0-9]).)*([A-Za-z]|[A-Za-z][A-Za-z0-9-]*[A-Za-z0-9])$`

## Get Numbers

`/\d+/`

## One or more

### Ex. ingress489

`/(ingress)([0-9]+)/`

## Match up to a specific Character

### Ex. sgElasticMapReducemaster:

`/sg[^:]*/`

## Or - Single Digits

`([0!6!8])`

## Or - Multiple Digits

`([0]|6[4]|12[8])`

## WHITESPACE / LINE BREAKS

### Find line/tab whitespace

`/[\R\r\n\t\v\h]/g`

### Match any character including Whitespace

`(?s)(.*?)`

### Match key=value;

`/key=([^;]*);/`

### Isolate TLS Headers for Removal

`var re = /-----BEGIN RSA PRIVATE KEY-----([^-]*)-----END RSA PRIVATE KEY-----/g;`

### Isolate TLS Data between Headers for Extraction

`var re = /-----BEGIN [0-9A-Z ]+-----[^-]*-----END [0-9A-Z ]+-----/g;`

## URL

### test that url query param contains alphanumeric

`/\?id=[0-9]{1}/`

## XML

### Get attribute value between double quotes (ID is example)

`/name="SAMLRequest" value="([^\"\s]*)"/;`

### Get value between tags ignoring attributes

`/\<ds\:Signature([^>]*)\>([\s\S]*?)\<\/ds\:Signature\>/`

## LOGGING

### Unicode Mode (Javascript)

`/^[\uD83D\uDC2A]$/u.test('\uD83D\uDC2A')`
true

`/^[\uD83D\uDC2A]$/.test('\uD83D\uDC2A')`
false

### Concatenate string with Variable

`var re = new RegExp("\\b" + variable + "\\b");`

### Use Env Variable in a RegExp

`var re = new RegExp(`\${envVar}`);`

## Hyphens And Dashes

### Match To First Dash / Hyphen

useful in a replace function to get everything after the hyphen.
Works if string has multiple dashes / hyphens.

`^[^-]*-`

## IDs

### UUID

`[0-9a-fA-F]{8}\-[0-9a-fA-F]{4}\-[0-9a-fA-F]{4}\-[0-9a-fA-F]{4}\-[0-9a-fA-F]{12}`

## Cognito

### Identity ID UUID

`[0-9a-fA-F]{8}\-[0-9a-fA-F]{4}\-[0-9a-fA-F]{4}\-[0-9a-fA-F]{4}\-[0-9a-fA-F]{12}`
