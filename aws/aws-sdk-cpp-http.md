# AWS SDK CPP HTTP

## Summary

Notes on making http requests in C++ with sdk

## Resources

- [SO Example](https://stackoverflow.com/questions/40457692/aws-sdk-cpp-how-to-use-curlhttpclient)

## Example Request

```cpp
using namespace Aws::Client;
using namespace Aws::Http;

static std::shared_ptr<HttpClientFactory> MyClientFactory; // My not be needed
static std::shared_ptr<HttpClient> MyHttpClient;

// ... jump ahead to method body ...

ClientConfiguration clientConfiguration;
MyHttpClient = CreateHttpClient(clientConfiguration);
Aws::String uri("https://example.org");
std::shared_ptr<HttpRequest> req(
               CreateHttpRequest(uri,
                                 verb, // i.e. HttpMethod::HTTP_POST
                                 Utils::Stream::DefaultResponseStreamFactoryMethod));
req.AddContentBody(body); //<= remember `body' should be `std::shared_ptr<Aws::IOStream>',
                          //   and can be created with `Aws::MakeShared<Aws::StringStream>("")';
req.SetContentLength(body_size);
req.SetContentType(body_content_type);
std::shared_ptr<HttpResponse> res = MyHttpClient->MakeRequest(*req);
HttpResponseCode resCode = res->GetResponseCode();
if (resCode == HttpResponseCode::OK) {
  Aws::StringStream resBody;
  resBody << res->GetResponseBody().rdbuf();
  rejoiceAndBeMerry();
} else {
  gotoPanicStations();
}
```
