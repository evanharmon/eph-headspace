# GOOGLE CLOUD CONFIG CLI

## Create New Configuration
only alpha numeric, numbers, or hyphens allowed
```console
$ gcloud config configurations create my-new-config
```
## List Configurations
```console
$ gcloud config configurations list
```

## Set Configuration Property
```console
$ gcloud config set account evan@evanharmon.me
```

## Set NonCore Configuration Property
```console
$ gcloud config set compute/zone us-east4-a
```
