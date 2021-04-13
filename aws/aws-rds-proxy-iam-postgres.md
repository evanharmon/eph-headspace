# AWS RDS AURORA

## Summary

Notes on using rds proxy IAM mode on postgres

## Resources

- [RDS Signer](https://docs.aws.amazon.com/AWSJavaScriptSDK/latest/AWS/RDS/Signer.html)

## Get Signed Token

```javascript
const getToken = async () => {
  const signer = new AWS.RDS.Signer({
    credentials: new AWS.SharedIniFileCredentials({ profile: 'default' }),
    region: Region,
    hostname: '',
    port: 5432,
    username: '',
  })
  return new Promise((resolve, reject) => {
    signer.getAuthToken({}, (err, token) => {
      if (err) {
        console.error(err)
        reject(err)
      } else {
        resolve(token)
      }
    })
  })
}
```

## Connect With Token

```javascript
const connect = async () => {
  const token = await getToken() // see example in this doc
  const client = new Client({
    host: 'dev-rds-proxy-tls.proxy-xxxxxxx.us-east-1.rds.amazonaws.com',
    port: 5432,
    ssl: true,
    user: 'dev_rds_user',
    database: 'master_rds',
    password: token,
  })

  client.connect()
  client.query('SELECT NOW()', (err, res) => {
    console.log(err, res)
    client.end()
  })
}
```

## IAM Authentication failed

Error: The IAM authentication failed for the role postgres. Check the IAM token for this role and try again.
Turned on RDS proxy enhanced logging to see better error messages. Checked in cloudwatch log groups.

-[Policy Reqs](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.IAMDBAuth.IAMPolicy.html)
