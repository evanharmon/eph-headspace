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
