# NODE XML PARSING

## Modules
(https://github.com/jindw/xmldom)
(https://github.com/yaronn/xpath.js)

## Parse XML
```
const dom = require("xmldom").DOMParser;
const doc = new dom().parseFromString(xml);
```

## xPath - find element tag
`"//*[local_name(.)='AuthnRequest']"`

## Get Nodes to manipulate
[0] index as multiple elements can exist
```
const nodes = select(doc, xpath);
const id = nodes[0].getAttribute("ID");
```

## Replace XML
```
const replaceXml = (xml, xpath, newXml) => {
    // GET FULL XML NODE
    const doc = new dom().parseFromString(xml);
    let parentNode = select(doc, "//*")[0];

    // GET OLD NODE TO BE REPLACED
    const oldNode = select(doc, xpath)[0];

    // GET NEW NODE FROM NEW XML
    const newDoc = new dom().parseFromString(newXml);
    const newNode = select(newDoc, "//*")[0];

    // REPLACE OLD XML WITH NEW XML
    parentNode.replaceChild(newNode, oldNode);
    return doc.toString();
};
```

## Change an Element Value
```
const doc = new dom().parseFromString(resXml);
const xpath = "//*[local-name(.)='Response']/*[local-name(.)='Issuer']";
const newXml =
  "<saml2:Issuer
      xmlns:saml2='urn:oasis:names:tc:SAML:2.0:assertion'
      Format='urn:oasis:names:tc:SAML:2.0:nameid-format:entity'
   >http:bogus.com</saml2:Issuer>";
const xml = replaceXml(xml, xpath, newXml); ## See function in this file
```

## Remove a Child node
```
const doc = new dom().parseFromString(resXml);
// find parent node
const response = doc.firstChild.nextSibling;
// find specific child node to remove
const assertion = response.firstChild.nextSibling.nextSibling.nextSibling;
response.removeChild(assertion);
response.firstChild.nextSibling.nextSibling.nextSibling.toString());
const xml = response.toString();
```
