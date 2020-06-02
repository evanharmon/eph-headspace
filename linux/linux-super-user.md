# unable to resolve host error

## Make sure /etc/hostname and /etc/hosts match

## Example

nvim #/etc/hostname
127.0.0.1 localhost nvim #/etc/hosts

# Login As Another User Sudo

## Change User - Keep Shell

`$ sudo su - myusername`

# switch to root

`$ sudo -i`
`$ sudo su`

# Run shell as another user

`$ su - ec2-user -c "/home/ec2-user/.nvm/install.sh"`

## Pass Environment Variables With Sudo

[SO](https://unix.stackexchange.com/questions/202383/how-to-pass-environment-variable-to-sudo-su)

```console
export DUMMY=dummy
sudo -Eu bob bash -c 'echo $DUMMY'
```
