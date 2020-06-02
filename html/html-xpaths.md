# HTML XPATHS

## Find element tag
`"//*[local_name(.)='AuthnRequest']"`

## Find by attribute value
`'//md-dialog/md-toolbar/div/h2[@translate="select.your.product"]'`

## Get innerHTML
`'//span[.="Main and Feeders"]'`

## Following / Next Element
`'//label-form[@label-content="System"]/following::div[1]/se-dropdown/div/div[@role="button"]'/`

## Get element by text containing or innerHTML
`//md-dialog/md-toolbar/div/span[text()="${label}"]]`

## Use contains for class / text
`'//button[contains(text(), "Device Options")]'`
