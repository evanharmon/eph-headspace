# AWS SDK CPP

## Summary

Notes on working with the aws c++ sdk

## Resources

- [SDK Docs](https://sdk.amazonaws.com/cpp/api/LATEST/class_aws_1_1_transfer_1_1_transfer_manager.html)
- [AWS Build CMAKE](https://docs.aws.amazon.com/sdk-for-cpp/v1/developer-guide/build-cmake.html)

## Getting Started

This setup is particular to docker image `eph-nvim/base:latest` which includes
aws sdk cpp builds in `/root/install`

#### Setup CMAKE

```console
export CMAKE_PREFIX_PATH=""
touch CMakeLists.txt
nvim CMakeLists.txt
```

```
# minimal CMakeLists.txt for the AWS SDK for C++
cmake_minimum_required(VERSION 3.2)

# "my-example" is just an example value.
project(my-example)

# Locate the AWS SDK for C++ package.
# Requires that you build with:
#   -DCMAKE_PREFIX_PATH=/path/to/sdk_install
find_package(AWSSDK REQUIRED COMPONENTS service1 service2 ...)

# The executable name and its sourcefiles
add_executable(my-example my-example.cpp)

# The libraries used by your executable.
# "aws-cpp-sdk-s3" is just an example.
target_link_libraries(my-example ${AWSSDK_LINK_LIBRARIES})

```

#### Build

```console
mkdir build && cd build
cmake3 .. \
  -DBUILD_ONLY=s3 \
  -DBUILD_SHARED_LIBS=OFF \
  -DENABLE_UNITY_BUILD=ON \
  -DCMAKE_BUILD_TYPE=Release \
  -DCMAKE_INSTALL_PREFIX="/root/install"
make
```

multiple sdks

```console
cmake3 .. \
  -DBUILD_ONLY="s3;sts" \
  -DBUILD_SHARED_LIBS=OFF \
  -DENABLE_UNITY_BUILD=ON \
  -DCMAKE_BUILD_TYPE=Release \
  -DCMAKE_INSTALL_PREFIX="/root/install"
make
```

Build from git project folder

```
cmake .. \
-DBUILD_ONLY="s3;cognito-identity;cognito-idp;sts" \
-DBUILD_SHARED_LIBS=OFF \
-DENABLE_UNITY_BUILD=ON \
-DCMAKE_BUILD_TYPE=debug
```

## Build With Failing Tests

```
-DAUTORUN_UNIT_TESTS=OFF
```
