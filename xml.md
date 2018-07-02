# Pretty Print CLI
## uses libxml2
`xmllint --format metadata.xml > my-pretty-metadata.xml`

# Remove Child
`doc.removeChild(doc.firstChild.nextSibling.nextSibling.nextSibling)`

# Get doc element text
`doc.firstChild.textContent`

# Change Element text
`doc.firstChild.textContent = "http://bogus.com";`
