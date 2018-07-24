# SAML OKTA TESTING

## STEPS
### Step 1: Server / Instance / Sandbox
- Get a FQDN domain up and running with a server
- Note sp endpoint
- make sure 80 and 443 are available
- set up GET route for sp-initiated sso
- set up POST route for login

GET (https://lightsail.harmonsoftwaresolutions.com/sso)
POST (https://lightsail.harmonsoftwaresolutions.com/sso)

### Step 2: HTTP Forwarding
Setup nginx or a load balancer to forward https to http

### Step 3: Add Admin App
Single Sign On Url: (https://lightsail.harmonsoftwaresolutions.com/sp)

Audience URI / Entity Id:
(http://lightsail.harmonsoftwaresolutions.com/sso/metadata)

Name ID Format:
EmailAddress

App username:
Email
