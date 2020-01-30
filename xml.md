# XML

## Summary

Notes on working with lovely but ugly XML

## Resources

- [javadev GH XML to JSON converter online](https://javadev.github.io/xml-to-json/)
- [CodeBeautify XML to JSON Online Converter](https://codebeautify.org/xmltojson)

# Pretty Print CLI

## uses libxml2

`xmllint --format metadata.xml > my-pretty-metadata.xml`

# Remove Child

`doc.removeChild(doc.firstChild.nextSibling.nextSibling.nextSibling)`

# Get doc element text

`doc.firstChild.textContent`

# Change Element text

`doc.firstChild.textContent = "http://bogus.com";`
