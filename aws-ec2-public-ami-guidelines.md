# AWS PUBLIC AMI GUIDELINES
(https://aws.amazon.com/articles/9001172542712674)

## Guidelines
- disable services and protocols that authenticate users in clear text
(e.g. Telnet and FTP)
- do not start unnecessary network services on launch. Only administrative
services (SSH/RDP) and the services required for your application should be
started
- securely delete all AWS credentials from disk and configuration files
- securely delete any third-party credentials from disk and configuration files
- securely delete any additional certificates or key material from the system
- ensure that software installed on your AMI does not have default internal
accounts and passwords (e.g. database servers with a default admin username and
password)
- ensure that the system does not violate the Amazon Web Services Acceptable
Use Policy. Examples include open SMTP relays or proxy servers

## Unix/Linux Specific Guidelines
- configure sshd to allow only public key authentication. This can be done by
setting `PubkeyAuthentication yes` and `PasswordAuthentication no` in
sshd_config
- generate a unique SSH host key on instance creation. If you are using
cloud-init in your AMI, it can handle this for you automatically
- remove and disable passwords for all user accounts so that passwords cannot be
used to log in and user accounts do not have a default password. This can be
done by running `passwd -l <USERNAME>` for each account
- Securely delete all user SSH public and private key pairs
- Securely delete the shell history and system log files that contain sensitive
data

## Windows Specific Guidelines
- ensure at all enabled user accounts have new randomly generated passwords on
instance creation. The EC2 Config Service can be set to do this for the
Administrator account on the next boot, but you must explicitly enable this
before bundling the image
- ensure that the guest account is disabled
- clear the Windows event log
- do not join the instance to a Windows domain
- do not enable any file share points that are accessible by unauthenticated
users. It is recommended to completely disable file shares
