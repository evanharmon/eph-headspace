# AWS IOT PLATFORM

## Summary

Notes on using the AWS IoT platform device registry

## Resources

- [AWS Register Device Walkthrough](https://docs.aws.amazon.com/iot/latest/developerguide/register-device.html)
- [AWS IoT Root CA Download](https://docs.aws.amazon.com/iot/latest/developerguide/server-authentication.html#server-authentication-certs)
- [RaspberryPi Certs Location Guide](https://docs.aws.amazon.com/iot/latest/developerguide/sdk-tutorials.html)

## Device Certs

AWS IoT Root CA must be downloaded from link in Resources section

4 certs must placed on the device

- AWS IoT Root CA
- Cert
- public key
- private key

On RaspberryPi, certs should be moved / scp'd / downloaded to
`/home/pi`.

example scp from mac

```console
scp myfile.txt pi@raspberry.local
```
