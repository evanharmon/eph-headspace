# PACKER

## Summary

Notes on using hashicorp packer

## Run Provisioner Script Only On Docker

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
