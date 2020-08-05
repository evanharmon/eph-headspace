# SAML REDIRECTS

## Saml Redirect Process GET
- Same reponse must attach sig and sigalg as diff query params
- If signed, destination attribute must exist with assert url
- Saml response should be a 302 redirect to assert url
- Http post is different than re-direct assert

## Same redirect process POST
- Uses html form with same query as hidden value
