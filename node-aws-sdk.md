# NODE AWS SDK

## Set global config for SDK
(http://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/global-config-object.html)
```
AWS.config.accessKeyId = process.env.AWS_ACCESS_KEY;
AWS.config.secretAccessKey = process.env.AWS_SECRET_ACCESS_KEY;
AWS.config.region = process.env.AWS_REGION;

const s3 = new AWS.S3(awsConfig({
  accessKeyId: process.env.AWS_ACCESS_KEY,
  secretAccessKey: process.env.AWS_SECRET_ACCESS_KEY,
  region: process.env.AWS_REGION,
  apiVersion: '2006-03-01' })
);
```
