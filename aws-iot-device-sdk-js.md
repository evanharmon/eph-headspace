# AWS IOT DEVICE SDK JAVASCRIPT

## Summary

Notes on using the AWS IoT device sdk for javascript

## Resources

- [AWS Install Docs](https://docs.aws.amazon.com/iot/latest/developerguide/iot-device-sdk-node.html)
- [Sample App](https://docs.aws.amazon.com/iot/latest/developerguide/iot-device-sdk-node.html)

## PLEASE READ

Do not install nodejs via `apt-get` until downloading the latest deb
package node version via `curl`

## Install Dependencies

```console
sudo apt-get update -y
sudo apt-get install -y git
```

## Install AWS CLI

```console
sudo apt-get install -y python3-pip
pip3 install awscli --upgrade --user
export PATH=/home/pi/.local/bin:$PATH
```

Configure aws cli

test

```console
aws iot describe-endpoint --endpoint-type iot:Data-ATS
```

## Install NodeJS

```console
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
sudo apt-get install -y nodejs
```

confirm installs

```console
node -v
npm -v
```

## Install SDK

Install is done in the `/home/myusername` directory via a git clone / npm
install

```console
cd $HOME
git clone https://github.com/aws/aws-iot-device-sdk-js.git
cd aws-iot-device-sdk-js
npm install
```
