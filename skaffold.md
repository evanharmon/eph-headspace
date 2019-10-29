# SKAFFOLD

## Summary

Notes on using skaffold to make k8s development easier

## Resources

[Docs](https://skaffold.dev/)
[Github](https://github.com/GoogleContainerTools/skaffold)
[Skaffold.yml Reference](https://skaffold.dev/docs/references/yaml/)
[Easy ECR Setup](go get -u github.com/awslabs/amazon-ecr-credential-helper/ecr-login/cli/docker-credential-ecr-login)

## Set Template Fields

[Docs](https://skaffold.dev/docs/how-tos/templating/)

docker example:

```yaml
docker:
  dockerfile: Dockerfile
  buildArgs:
    AWS_ACCESS_KEY_ID: "{{.AWS_ACCESS_KEY_ID }}"
    AWS_SECRET_ACCESS_KEY: "{{.AWS_SECRET_ACCESS_KEY}}"
    AWS_SESSION_TOKEN: "{{.AWS_SESSION_TOKEN}}"
```

## ECR Setup

[install](go get -u github.com/awslabs/amazon-ecr-credential-helper/ecr-login/cli/docker-credential-ecr-login)
ecr cred helper

add to `~/.docker/config.json` file:

```json
{
  "credHelpers": {
    "[account_number].dkr.ecr.[region].amazonaws.com": "ecr-login"
  }
}
```
