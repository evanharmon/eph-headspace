# GITHUB

## Pull Requests
Base Branch is where you think the changes should be applied
Compare branch contains the changes

## API
`$ curl -u 'USER' https://api.github.com/user/repos -d '{"name":"REPO"}'`
Remember replace USER with your username and REPO with your
repository/application name!

`$ git remote add origin git@github.com:USER/REPO.git`
`$ git push origin master`

## Clone with API Token
DO NOT USE THIS VERSION
`$ git clone https://<token>@github.com/owner/repo.git`
Safe Version - use token in git push/pull
`$ git pull https://<token>@github.com/username/bar.git`

## Clone Github Repo in to current folder that has files
```
$ git init .
$ git remote add -t \* -f origin <repo>
$ git checkout master
```

## SUDO GIT
NEVER DO SUDO GIT it will mess up ownerships

## Passwords with MFA
Go to github, settings, personal access tokens. Create a new one and use this as
password when requested via git pull, git push, etc
