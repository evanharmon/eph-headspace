# SCP

## Summary
notes on using SCP

## Use Identify File With SCP
[Link](https://www.techrepublic.com/article/how-to-use-secure-copy-with-ssh-key-authentication/)
```console
scp -i ~/.ssh/id_rsa.pub FILENAME USER@SERVER:/home/USER/FILENAME
```
