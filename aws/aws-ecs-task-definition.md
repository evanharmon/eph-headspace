# AWS ECS TASK DEFINITION

## Summary

Notes on working with ECS task definitions in AWS

## Resources

- [ECS Secrets](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/specifying-sensitive-data-secrets.html)

## Secrets
pull key value from secrets manager

```json
{
  "containerDefinitions": [{
    "secrets": [{
      "name": "<environment_variable_name>",
      "valueFrom": "arn:aws:secretsmanager:<region>:<account_id>:secret:<secret_name>:<json_key>::"
    }]
  }]
}
```

## Support Exec In To Farge
```json
"linuxParameters": {
  "initProcessEnabled": true
}
```
