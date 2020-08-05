# AWS SDK IOS CREDENTIALS

## Summary

Notes on using access credentials

## Resources

- [Checking Credentials](https://docs.aws.amazon.com/cognito/latest/developerguide/getting-credentials.html#getting-credentials-1.ios-swift)
- [Authorization Modes](https://docs.amplify.aws/sdk/api/graphql/q/platform/ios#authorization-modes)

### Tokens

#### Update Auth Token (JWT)

```swift
func initializeAppSync() {
        do {
            // You can choose the directory in which AppSync stores its persistent cache databases
        let cacheConfiguration = try AWSAppSyncCacheConfiguration()

            // Initialize the AWS AppSync configuration
            let appSyncConfig = try AWSAppSyncClientConfiguration(appSyncServiceConfig: AWSAppSyncServiceConfig(),
                                                                  userPoolsAuthProvider: {
                                                                    class MyCognitoUserPoolsAuthProvider : AWSCognitoUserPoolsAuthProviderAsync {
                                                                        func getLatestAuthToken(_ callback: @escaping (String?, Error?) -> Void) {
                                                                            AWSMobileClient.default().getTokens { (tokens, error) in
                                                                                if error != nil {
                                                                                    callback(nil, error)
                                                                                } else {
                                                                                    callback(tokens?.idToken?.tokenString, nil)
                                                                                }
                                                                            }
                                                                        }
                                                                    }
                                                                    return MyCognitoUserPoolsAuthProvider()}(),
                                                                  cacheConfiguration: cacheConfiguration)

            // Initialize the AWS AppSync client
            appSyncClient = try AWSAppSyncClient(appSyncConfig: appSyncConfig)
        } catch {
            print("Error initializing appsync client. \(error)")
        }
    }
```
