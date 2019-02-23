# PACKER

## Summary

Notes on using hashicorp packer

## Builders

## Docker Builds

#### Attach Volume

```
"volumes": [{ "/tmp/myfolder": "/root/myfolder" }]

```

#### Run Provisioner Script Only On Docker

[SO](https://stackoverflow.com/questions/40132475/packer-sudo-su-condition-for-builders)

```
"provisioners": [{
  "type": "shell",
  "inline": [
    "apt-get install sudo"
  ],
  "only": ["docker"]
}
```

#### Typical Setup For ECR Docker Builds Based On ECR Image

```
{
  "builders": [
    {
      "type": "docker",
        "commit": true,
        "ecr_login": true,
        "image": "999999999999.dkr.ecr.us-east-1.amazonaws.com/myrepo",
        "login_server": "999999999999.dkr.ecr.us-east-1.amazonaws.com/",
        "privileged_mode": true
    }
  ],
  "post-processors": [
    [
      {
        "type": "docker-tag",
        "repository": "999999999999.dkr.ecr.us-east-1.amazonaws.com/myrepo",
        "tag": "latest"
      },
      {
        "type": "docker-push",
        "ecr_login": true,
        "login_server": "999999999999.dkr.ecr.us-east-1.amazonaws.com/"
      }
    ]
  ]
}
```
