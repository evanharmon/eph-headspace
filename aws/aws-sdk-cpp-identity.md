# AWS SDK CPP IDENTITIES

## Summary

Notes on managing cognito identties in C++ with sdk

## Resources

- [Example SDK Tests](https://github.com/aws/aws-sdk-cpp/tree/master/aws-cpp-sdk-identity-management-tests/auth)

## Create Custom AWS Credentials Provider From Credentials

```cpp
auto accessKeyId = credentials.GetAccessKeyId();
const char * cnstAccessKeyId = accessKeyId.c_str();

auto secretKey = credentials.GetSecretKey();
const char * cnstSecretKey = secretKey.c_str();

auto sessionToken = credentials.GetSessionToken();
const char * cnstSessionToken = sessionToken.c_str();
std::shared_ptr<Aws::Auth::AWSCredentialsProvider> provider = Aws::MakeShared<Aws::Auth::SimpleAWSCredentialsProvider>(
        "CustomCredsProvider", cnstAccessKeyId, cnstSecretKey, cnstSessionToken);
auto provCreds = provider->GetAWSCredentials();
```
