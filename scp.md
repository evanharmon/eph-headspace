# SCP

## Summary

notes on using SCP

## Resources

- [SCP Guide For RaspberryPi](https://www.raspberrypi.org/documentation/remote-access/ssh/scp.md)

## Use Identify File With SCP

- [Link](https://www.techrepublic.com/article/how-to-use-secure-copy-with-ssh-key-authentication/)

```console
scp -i ~/.ssh/id_rsa.pub FILENAME USER@SERVER:/home/USER
```

## Copy Multiple Files

```console
scp myfile1.txt myfile2.txt pi@raspberrypi.local:
```
