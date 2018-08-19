# COOKIES

## Transport
Browser will automatically send cookies on HTTP requests

## Benefits
Good way to secure websites since where user logs in and navigates between links

## Disadvantages
Vulnerable to CSRF attacks
Hard to use on mobile devices

## Secure
Cookies should always be marked secure. Otherwise they could be sidejacked on a
non tls route and leaked as plain text

## Location Of Cookies In Response Object
`response.headers["set-cookie"]`

## Console.log Showing [object object] In Cookies
need to use apply
`this.cookies.set.apply()`
