# AWS COGNITO USER POOL FAQS

## Summary

Frequently asked questions for Cognito User Pools

## Resources

- [FAQs](https://aws.amazon.com/cognito/faqs/)

## FAQs

### How Do I Search All Users By Sub ID?

- have to paginate through all users and check if sub ID matches

### How Do I Join Google / Facebook As One User?

have to link using a pre-sign up cognito trigger lambda

### How Do I Add Groups To Users On Sign Up?

use a post-confirmation cognito trigger lambda

### How Do I Find Identity ID By User ID?

No API exists that maps user id to identity id. Has to be managed manually
via a mapping table / database.

### How Do I Track Identity ID Per User?

custom attribute on user pool, manually written to by app

### How Do I Search All Users For An Attribute?

- have to paginate thru ALL users and collect results
