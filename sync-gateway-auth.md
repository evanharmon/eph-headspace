# SYNC GATEWAY AUTH

## User/Guest
If using the public api, and no auth setup, assumes user/guest
https://developer.couchbase.com/documentation/mobile/current/guides/sync-gateway/authorizing-users/index.html
Any request to the Public REST API that does not have an Authorization header
or a session cookie is treated as coming from the GUEST account

## After you disable GUEST for SG, you have to post a new user
```
POST
{
    "name": "bob",
    "password": "pass",
    "admin_roles": ["admin"],
    "": ""
}
```
