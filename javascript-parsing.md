# JAVASCRIPT PARSING

## Parse Int - Always Include Radix (Default to 10)
`parseInt(String, 10)`

## Check for a nested property
`const firstname = profile.contact.hasOwnProperty("first_name")`

## Check for and assign a nested property
```
const firstname = profile.contact.hasOwnProperty("first_name")
  ? profile.contact.first_name._
  : ""
```
