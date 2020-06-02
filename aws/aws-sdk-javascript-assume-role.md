# AWS JS SDK Assume Role

### Assume Role Example

```javascript
const AWS = require('aws-sdk')
const ini = require('ini')
const fs = require('fs')

fs.readFileSync(`${process.env.HOME}/.aws/config`, 'utf-8')

// SDK doesn't provide assumeRole MFA for other accounts in config like GO sdk
const awsProfile = 'company-dev'
if (awsProfile) {
  try {
    const HOME = process.env.HOME
    const configFile = fs.readFileSync(`${HOME}/.aws/config`, 'utf-8')
    const configIni = ini.parse(configFile)
    const awsProfileConfig = configIni[`profile ${awsProfile}`]
    if (awsProfileConfig && awsProfileConfig.role_arn) {
      const roleArn = awsProfileConfig.role_arn
        .replace(/:/g, '_')
        .replace(/[^A-Za-z0-9\-_]/g, '-')
      const awsCliCacheFilename = `${awsProfile}--${roleArn}`
      const awsCliCachePath = `${HOME}/.aws/cli/cache/${awsCliCacheFilename}.json`
      const cacheFile = fs.readFileSync(awsCliCachePath, 'utf-8')
      const awsCliCache = JSON.parse(cacheFile)

      const sts = new AWS.STS()
      AWS.config.credentials = sts.credentialsFrom(awsCliCache, awsCliCache)
    }
  } catch (err) {
    console.log(err)
  }
}
```
