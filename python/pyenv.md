# PYENV

[GITHUB](https://github.com/pyenv/pyenv)
Install [pyenv-virtualenv](https://github.com/pyenv/pyenv-virtualenv) as well

## ZSHRC

```bash
# PY
if [ -d "$HOME/.pyenv" ]; then
        eval "$(pyenv init -)"
        eval "$(pyenv virtualenv-init -)"
fi
```

## Install Python Versions

```console
pyenv install 2.7.11
```

## Set Up Virtual Env

```console
$ pyenv virtualenv 2.7.11 gcloud
```

## Common Errors

### pyenv install fails

[GH Issue](https://github.com/pyenv/pyenv/issues/1066)

ModuleNotFoundError: No module named 'pyexpat'

on MAC OS 10.14

```console
sudo installer -pkg /Library/Developer/CommandLineTools/Packages/macOS_SDK_headers_for_macOS_10.14.pkg -target /
SDKROOT=/Library/Developer/CommandLineTools/SDKs/MacOSX10.14.sdk/ pyenv install  3.7.5
```
