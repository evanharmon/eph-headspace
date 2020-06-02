# AWS EC2 OS
Customer is responsible for patching / updating OS!

## Features
- full root access for customer
- AWS does not have any access rights to your instance or guest OS

## Recommended Security Best Practices
- disabling password-only access to guests
- use MFA (SSHv2 at the very least)
- employ privilege escalation mechanism with logging on a per-user basis

## Linux Example Of Best Practices
- use certificate-based SSHv2 access
- disable remote root login
- use command-line logging
- use 'sudo' for privilege escalation
- generate your own key pairs to guarantee uniqueness, not shared with other
customers, not shared / known by AWS

