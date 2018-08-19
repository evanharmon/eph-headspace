# GIT CONFIG

## Set tab space width to four spaces
setting of 5 is to support +/- of git diff
`$ git config --global core.pager 'less -x1,5'`

## See config file objects
```
$ git config --global -l
$ git config --local -l
```

## Set os x to use keychain
`$ git config --global credential.helper osxkeychain`

## save git user/password forever Ubuntu
`$ git config credential.helper store`

## Set username / email git config
```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

## Set Proxy
`$ git config --local http.proxy http://198.202.137.35:80`
