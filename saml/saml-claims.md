# SAML CLAIMS
Claims are essentially a Microsoft concept

Helpful Links
[What are claims](https://msdn.microsoft.com/en-us/library/ff359101.aspx)
(http://stackoverflow.com/questions/23116029/claims-and-saml2-confusion)
signed statements made about an identity by ADFS and interpreted by Windows Identity Foundation (WIF) e.g. Mobile = 12345678

## Windows Identity Foundation (WIF) use
WIF takes base SAML assertion information and returns a claims object to the application

## ADFS - anonymous user with authorized access
Just use role claims
