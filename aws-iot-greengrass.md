# AWS IOT GREENGRASS

## Summary

Notes on using greengrass. Allows running Lambdas locally. AWS IoT SDK is
required

## Resources

- [Getting Started Tutorial - RaspberryPi](https://docs.aws.amazon.com/greengrass/latest/developerguide/setup-filter.rpi.html)

## Check Dependencies

```console
cd /home/pi/Downloads
mkdir greengrass-dependency-checker-GGCv1.10.x
cd greengrass-dependency-checker-GGCv1.10.x
wget https://github.com/aws-samples/aws-greengrass-samples/raw/master/greengrass-dependency-checker-GGCv1.10.x.zip
unzip greengrass-dependency-checker-GGCv1.10.x.zip
cd greengrass-dependency-checker-GGCv1.10.x
sudo modprobe configs
sudo ./check_ggc_dependencies | more
```
