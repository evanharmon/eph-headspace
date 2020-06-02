# AWS CODE DEPLOY APP SPEC

## Example Spec
```
---
version: 0.0
os: linux
files:
  - source: /
    destination: /home/ec2-user/node
permissions:
  - object: /home/ec2-user
    owner: ec2-user
    group: ec2-user
    type:
      - directory
      - file

hooks:
  ApplicationStop:
    - location: deploy/stop.sh
      timeout: 120
      runas: ec2-user
  BeforeInstall:
    - location: deploy/install.sh
      timeout: 300
      runas: ec2-user
  AfterInstall:
    - location: deploy/post_install.sh
      timeout: 600
      runas: ec2-user
  ApplicationStart:
    - location: deploy/run.sh
      timeout: 120
      runas: ec2-user

```
## Example Scripts
deploy/install.sh
```
#!/usr/bin/env bash
set -e
# update instance
sudo yum -y update
```
deploy/post_install.sh
```
#!/usr/bin/env bash
set -e

cd /home/ec2-user/node

npm install
npm run build:dist
```

deploy/run.sh
```
#!/usr/bin/env bash
set -e

source ~/.bash_profile

cd /home/ec2-user/node

sudo pm2 start server.js
```

deploy/stop.sh
```
#!/usr/bin/env bash
set -e

sudo pm2 kill
```
