# SAML FLOW
Terms:
- Identity Provider (IP)
- Service Provider (SP)
- Single Sign On (SSO_)

Helpful Links:
(https://blog.surf.nl/en/saml-for-dummies/)
(https://en.wikipedia.org/wiki/SAML_2.0)

## Flow Example 1:
- user logs in to their company (IP - could be a website or AD etc)
- user has access to many apps like SalesForce without having to type
  username/password again anywhere

## Conversation between end user’s web browser, SP, and IP
- User tries to reach SP from the browser
- SP generates SAML request
- SP re-directs to Partner’s SSO url at IP
- IP parses SAML request, authenticates user, generates SAML response
- IP returns encoded SAML response to browser, browser sends SAML response
  to ACS url at SP
- ACS url at SP verifies SAML Response
- User is logged in to SP
