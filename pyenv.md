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
