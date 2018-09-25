# GOOGLE CLOUD IAM CLI

## Create Service Account
```console
gcloud iam service-accounts create my-dev-group \
  --display-name "my development group"
```

## Create Keys
```console
gcloud iam service-accounts keys create my-dev-group \
  --iam-account my-dev-group@admin.iam.gserviceaccount.com
```
