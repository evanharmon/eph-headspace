# SSH SSHD_CONFIG

## Line To Change To Disable Password Logins
`PasswordAuthentication no`

## Centos: Lines To Change To Disable Password Logins
```bash
PubkeyAuthentication yes
AuthorizedKeyFile .ssh/authorized_keys
PasswordAuthentication no
ChallengeResponseAuthentication no
```
