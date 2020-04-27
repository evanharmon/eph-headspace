# AUTH NATIVE VS BROWSER

## Summary

Notes on using Native mobile vs browser based authentication

## Resources

- [Auth0](https://auth0.com/docs/design/browser-based-vs-native-experience-on-mobile)
- [RFC-8252](https://www.rfc-editor.org/rfc/rfc8252.txt)
- [Google Sign In SDK](https://developers.googleblog.com/2016/08/modernizing-oauth-interactions-in-native-apps.html)
- [Google Blocking Embedded View Logins](https://auth0.com/blog/google-blocks-oauth-requests-from-embedded-browsers/)
- [AWS SDK](https://docs.aws.amazon.com/aws-mobile/latest/developerguide/mobile-hub-add-aws-mobile-user-sign-in.html)
- [SFSafariViewController Docs](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller)
- [SFAuthenticationSession](https://developer.apple.com/documentation/safariservices/sfauthenticationsession)

## Sessions

Native: each app must log in separately

## Security

- Browser based login requires a registered callback url for additional
  security against phishing
- External User Agents are preferred (RFC-8252)
- Embedded User Agent allows native app to copy user credentials and cookies

## Google

Google sign in no longer allows webviews / embedded user-agents

## AWS

AWS sdk's are using google sign in v4 or later which does not support web views

## IOS

use [SFSafariViewController](https://www.oauth.com/oauth2-servers/oauth-native-apps/use-system-browser/)
