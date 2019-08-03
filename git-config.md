# GIT CONFIG

## Set tab space width to four spaces

setting of 5 is to support +/- of git diff

```console
git config --global core.pager 'less -x1,5'
```

## See config file objects

```console
git config --global -l
git config --local -l
```

## Set os x to use keychain

```console
git config --global credential.helper osxkeychain
```

## save git user/password forever Ubuntu

```console
git config credential.helper store
```

## Set username / email git config

```console
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

## Set Proxy

```console
git config --local http.proxy http://1.1.1.1:80
```

## Edit Local Config In Editor

```console
git config --local -e
```
