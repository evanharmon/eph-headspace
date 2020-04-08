# GOOGLE CLOUD API OAUTH

## Summary

Notes on using OAuth2 in Google Cloud API

## Resources

- [Setup](https://support.google.com/cloud/answer/6158849?hl=en&ref_topic=3473162)
- [FAQ](https://support.google.com/cloud/answer/9110914?hl=en&ref_topic=3473162)
- [Google Sign In Scopes](https://developers.google.com/identity/protocols/googlescopes#google_sign-in)
- [Branding Guidelines](https://developers.google.com/identity/branding-guidelines#top_of_page)
- [Blog On App Verificaton](https://www.nylas.com/blog/google-oauth-app-verification/)
- [Medium Blog On The Verification Headache](https://medium.com/@crspybits/the-google-oauth-review-process-9d1b05f53aea)

### OAuth Token Grants

- [Rate Limits](https://support.google.com/cloud/answer/9028764?hl=en)

### Verification

Avoid using a LOGO if you can, because with no sensitive / restricted scopes you
won't have to do verification.

Checklist for submitting for verification:

- your contact email address
- justification for each scope, including why a narrower scope would be
  insufficient
- All OAuth information matches branding including: project name, support email,
  homepage URL, privacy policy URL
- verify domain with google (likely already done if using GCP tied to GSuite)
- privacy policy page visible to external hits, linked to Google Oauth consent
  screen, and visible to users
- confirm button design matches Google Branding Restrictions
- ALL OAuth production OAuth client credentials must be in a SEPARATE PROJECT
- ALL OAuth clients must be publically testable by google - this is partly why
  it should be a separate project
- make a public video on youtube explaining and walking users through the OAuth
  process for your app. Significantly speeds up verification

### Scopes

Most apps just using [profile email openid] aren't using any sensitive scopes.
Sensitive and Restricted scopes allow access to Google User Data

### Branding Restrictions

- [Incorrect Button Design](https://developers.google.com/identity/branding-guidelines#incorrect)

Google Sign In Button must match padding, dp size for logo and text or it may be
denied / revoked.

### Youtube App Video

- demonstrate the oauth grant process by users and explain each app
  functionality usage of each Oauth client belonging to the project
- video must clearly show the app's details such as app name, OAuth Client Id, etc
- video must show any usage of sensitive or restricted scopes on EACH client

### Support Email

Create a google group for support emails and add every project owner to that
group so the setting can be correct in the OAuth Consent Screen.
