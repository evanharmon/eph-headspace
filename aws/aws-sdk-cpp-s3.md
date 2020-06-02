# AWS SDK CPP

## Summary

Notes on working with the aws c++ sdk and s3

## Resources

- [S3 Examples Guide](https://docs.aws.amazon.com/sdk-for-cpp/v1/developer-guide/examples-s3.html)
- [S3 Full Code Examples](https://github.com/awsdocs/aws-doc-sdk-examples/tree/master/cpp)

## Updated Example

- [SO](https://stackoverflow.com/questions/57520608/amazon-example-transfermanager-code-does-not-compile)

```cpp
#include <aws/core/Aws.h>
#include <aws/s3/S3Client.h>
#include <aws/transfer/TransferManager.h>

static const char *ALLOC_TAG = "main";

/*
 * referenced from:
 * https://github.com/aws/aws-sdk-cpp/blob/master/aws-cpp-sdk-transfer-tests/TransferTests.cpp
 */

int main() {
  Aws::SDKOptions options;
  // for debug purpose since transfer mngr fails silently.
  options.loggingOptions.logLevel = Aws::Utils::Logging::LogLevel::Info;
  Aws::InitAPI(options);

  Aws::Client::ClientConfiguration clientConfiguration;
  clientConfiguration.endpointOverride = "https//store-test.example.com";
  clientConfiguration.region = "store-test";

  using namespace Aws::Transfer;
  using namespace Aws::Utils;

  auto s3Client = Aws::MakeShared<Aws::S3::S3Client>(ALLOC_TAG, clientConfiguration);
  auto thread_executor =
      Aws::MakeShared<Threading::PooledThreadExecutor>(ALLOC_TAG, 4);

  Aws::Transfer::TransferManagerConfiguration transferConfig(
      thread_executor.get());
  transferConfig.s3Client = s3Client;

  transferConfig.transferStatusUpdatedCallback =
      [](const TransferManager *,
         const std::shared_ptr<const TransferHandle> &handle) {
        std::cout << "Transfer Status = "
                  << static_cast<int>(handle->GetStatus()) << "\n";
      };

  transferConfig.uploadProgressCallback =
      [](const TransferManager *,
         const std::shared_ptr<const TransferHandle> &handle) {
        std::cout << "Upload Progress: " << handle->GetBytesTransferred()
                  << " of " << handle->GetBytesTotalSize() << " bytes\n";
      };

  auto transferManager = TransferManager::Create(transferConfig);
  auto transferHandle = transferManager->UploadFile(
      "/user/aws/giantFile", "aws_cpp_ga", "giantFile", "text/plain",
      Aws::Map<Aws::String, Aws::String>());

  transferHandle->WaitUntilFinished();
  /* you may need to reset the thread pool before shutdown API */
  thread_executor.reset();
  Aws::ShutdownAPI(options);
  return 0;
}
```
