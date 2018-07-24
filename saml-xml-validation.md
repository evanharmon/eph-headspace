# SAML XML VALIDATION

## Validate Metadata
(https://wiki.surfnet.nl/display/OpenConext/Validating+SAML2+metadata)
`brew install wget`

### Get Schemas
```
$ wget http://docs.oasis-open.org/security/saml/v2.0/saml-schema-metadata-2.0.xsd
$ wget http://docs.oasis-open.org/security/saml/v2.0/saml-schema-assertion-2.0.xsd
$ wget http://www.w3.org/TR/2002/REC-xmldsig-core-20020212/xmldsig-core-schema.xsd
$ wget http://www.w3.org/TR/2002/REC-xmlenc-core-20021210/xenc-schema.xsd
$ wget http://www.w3.org/2001/xml.xsd
```

### create catalog
`xmlcatalog --create > catalog`

### Below was overwriting catalog entry not appending - i had to manually put
them in to the catalog file

```
$ xmlcatalog --noout \
    --add uri http://docs.oasis-open.org/security/saml/v2.0/saml-schema-metadata-2.0.xsd \
          file:///opt/xml/saml-schema-metadata-2.0.xsd catalog

$ xmlcatalog --noout \
    --add uri http://docs.oasis-open.org/security/saml/v2.0/saml-schema-assertion-2.0.xsd \
          file:///opt/xml/saml-schema-assertion-2.0.xsd catalog

$ xmlcatalog --noout \
    --add uri http://www.w3.org/TR/2002/REC-xmldsig-core-20020212/xmldsig-core-schema.xsd
          file:///opt/xml/xmldsig-core-schema.xsd catalog

$ xmlcatalog --noout \
    --add uri http://www.w3.org/TR/2002/REC-xmlenc-core-20021210/xenc-schema.xsd
          file:///opt/xml/xenc-schema.xsd catalog

$ xmlcatalog --noout \
    --add uri http://www.w3.org/2001/xml.xsd \
          file:///opt/xml/xml.xsd catalog
```

### Set Environment Variable
`$ export XML_CATALOG_FILES=/opt/xml/catalog`

### Validation
```
$ xmllint --noout \
    --schema /opt/xml/saml-schema-metadata-2.0.xsd some_metadata_file.xml
```
